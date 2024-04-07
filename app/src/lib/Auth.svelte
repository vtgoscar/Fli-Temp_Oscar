<!-- Auth.svelte -->
<script lang="ts">
	import { supabase } from '../supabaseClient';
	import { fly } from 'svelte/transition';
	import authStore from '../lib/AuthStore';
	import { onMount } from 'svelte';

	let loading = false;
	let email = '';
	let password = '';
	let activeTab = 'register'; // Set the default activeTab to 'register'
	export let formType; // Define formType prop

	onMount(() => {
		authStore.set({ activeTab: 'register' });
	});

	authStore.subscribe((state) => {
		activeTab = state.activeTab;
	});

	const handleCloseModal = () => {
		authStore.set({ activeTab: null });
		email = '';
		password = '';
		// Hide the current modal
		const currentModal = document.querySelector('.modal-overlay:last-child');
		if (currentModal) {
			currentModal.addEventListener(
				'transitionend',
				() => {
					currentModal.style.display = 'none';
				},
				{ once: true }
			);
		}

		// Hide the modal with class 's-tMJDz8oylI8M'
		const unwantedModal1 = document.querySelector('.s-tMJDz8oylI8M');
		if (unwantedModal1) {
			unwantedModal1.style.display = 'none';
		}

		// Hide the modal with class 's-a65M7ZidXhwb'
		const unwantedModal2 = document.querySelector('.s-a65M7ZidXhwb');
		if (unwantedModal2) {
			unwantedModal2.style.display = 'none';
		}

		// Hide the modal associated with the provided button
		const unwantedModal3 = document.querySelector('.modal-associated-with-button');
		if (unwantedModal3) {
			unwantedModal3.style.display = 'none';
		}
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
			const { user, error } = await supabase.auth.signInWithPassword({
				email: email,
				password: password
			});
			if (error) throw error;
			alert('Logged in successfully!');
			// Reload the page after successful login
			window.location.reload();
		} catch (error) {
			console.error('Error signing in:', error);
			// Handle sign-in errors, e.g., display error message to the user
			alert(error.message);
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
				aria-label="Close Modal"
			>
				<svg
					xmlns="http://www.w3.org/2000/svg"
					class="h-6 w-6"
					fill="none"
					viewBox="0 0 24 24"
					stroke="currentColor"
				>
					<path
						stroke-linecap="round"
						stroke-linejoin="round"
						stroke-width="2"
						d="M6 18L18 6M6 6l12 12"
					/>
				</svg>
			</button>

			<!-- Tabs -->
			<div class="flex justify-between mb-4 z-10">
				<button
					class="px-4 py-2 text-blue-500 font-semibold focus:outline-none"
					class:selected={activeTab === 'register'}
					on:click={() => authStore.set({ activeTab: 'register' })}
				>
					Register
				</button>
				<button
					class="px-4 py-2 text-blue-500 font-semibold focus:outline-none"
					class:selected={activeTab === 'login'}
					on:click={() => authStore.set({ activeTab: 'login' })}
				>
					Login
				</button>
			</div>

			<!-- Registration form -->
			{#if activeTab === 'register'}
				<form on:submit|preventDefault={handleSignUp}>
					<div>
						<label for="register-email">Email</label>
						<input
							id="register-email"
							class="inputField text-black"
							type="email"
							placeholder="Register email"
							bind:value={email}
						/>
					</div>
					<div>
						<label for="register-password">Password</label>
						<input
							id="register-password"
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
			{#if activeTab === 'login'}
				<form on:submit|preventDefault={handleLogin}>
					<div>
						<label for="login-email">Email</label>
						<input
							id="login-email"
							class="inputField text-black"
							type="email"
							placeholder="Your email"
							bind:value={email}
						/>
					</div>
					<div>
						<label for="login-password">Password</label>
						<input
							id="login-password"
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

<!-- Add the following CSS styles to ensure the submit button is always visible -->
<style>
	/* Remove any styles that might hide the submit button */
	.submit-btn {
		visibility: visible;
	}

	/* Adjust the styles of the submit button to ensure it's always visible */
	.bg-green-500 {
		background-color: #10b981; /* Change the background color to green */
	}

	.bg-green-500:hover {
		background-color: #10b981; /* Remove the hover effect */
	}
</style>
