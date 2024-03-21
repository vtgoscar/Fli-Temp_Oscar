<script lang="ts">
  import { supabase } from '../supabaseClient';
  import { fly } from 'svelte/transition';
  import authStore from '../lib/AuthStore';

  let loading = false;
  let email = '';
  let password = '';
  let formType = ''; // Can be 'register' or 'login'

  authStore.subscribe((state) => {
    formType = state.formType;
  });

  const handleCloseModal = () => {
    authStore.set({ formType: null });
    email = '';
    password = '';
  };

  const handleSignUp = async () => {
    try {
      loading = true;
      const { user, error: signUpError } = await supabase.auth.signUp({
        email: email,
        password: password
      });
      if (signUpError) throw signUpError;
      if (user) {
        const { error: updateError } = await supabase.from('profiles').upsert([
          {
            id: user.id,
            role: 'Participant'
          }
        ]);
        if (updateError) throw updateError;
      }
      alert('Check your email for the confirmation link!');
    } catch (error) {
      alert(error.message);
    } finally {
      loading = false;
    }
  };

  const handleLogin = async () => {
    try {
      loading = true;
      const { user, error } = await supabase.auth.signIn({
        email: email, // use the email variable
        password: password // use the password variable
      });
      if (error) throw error;
    } catch (error) {
      if (error instanceof Error) {
        alert(error.message);
      }
    } finally {
      loading = false;
    }
  };

  const signOut = async () => {
    try {
      await supabase.auth.signOut();
      // add navigation to login or home page if needed
    } catch (error) {
      console.error('Error signing out: ', error);
    }
  };
</script>

<div in:fly={{ x: -600, duration: 800 }} out:fly={{ x: 600, duration: 800 }}>
  <div class="fixed inset-0 z-50 flex items-center justify-center bg-black bg-opacity-50">
    <div class="bg-white p-6 rounded-lg shadow-lg max-w-md relative">
      <!-- Close button -->
      <button
        class="absolute top-2 right-2 z-10 text-gray-600 hover:text-red-500 focus:outline-none"
        on:click={handleCloseModal}
      >
        <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
        </svg>
      </button>

      <!-- Tabs -->
      <div class="flex justify-between mb-4 z-10">
        <button
          class="px-4 py-2 text-blue-500 font-semibold focus:outline-none"
          class:selected={formType === 'register'}
          on:click={() => authStore.set({ formType: 'register' })}
        >
          Register
        </button>
        <button
          class="px-4 py-2 text-blue-500 font-semibold focus:outline-none"
          class:selected={formType === 'login'}
          on:click={() => authStore.set({ formType: 'login' })}
        >
          Login
        </button>
      </div>
<!-- Registration form -->
{#if formType === 'register'}
  <form on:submit|preventDefault={handleSignUp}>
    <div>
      <label for="email">Email</label>
      <input
        id="email"
        class="inputField text-black"
        type="email"
        placeholder="Register email"
        bind:value={email}
      />
    </div>
    <div>
      <label for="password">Password</label>
      <input
        id="password"
        class="inputField text-black"
        type="password"
        placeholder="Your password"
        bind:value={password}
      />
    </div>
    <div>
      <button
        type="submit"
        class="mt-4 bg-green-500 hover:bg-green-800 text-white font-bold py-2 px-4 rounded focus:outline-none"
        disabled={loading}
      >
        <span>{loading ? 'Loading' : 'Register'}</span>
      </button>
    </div>
  </form>
{/if}

<!-- Login form -->
{#if formType === 'login'}
  <form on:submit|preventDefault={handleLogin}>
    <div>
      <label for="email">Email</label>
      <input
        id="email"
        class="inputField text-black"
        type="email"
        placeholder="Your email"
        bind:value={email}
      />
    </div>
    <div>
      <label for="password">Password</label>
      <input
        id="password"
        class="inputField text-black"
        type="password"
        placeholder="Your password"
        bind:value={password}
      />
    </div>
    <div>
      <button
        type="submit"
        class="mt-4 bg-green-500 hover:bg-green-800 text-white font-bold py-2 px-4 rounded focus:outline-none"
        disabled={loading}
      >
        <span>{loading ? 'Loading' : 'Login'}</span>
      </button>
    </div>
  </form>
{/if}
    </div>
  </div>
</div>
