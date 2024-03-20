<!-- Modal.svelte -->
<script>
  import Auth from '$lib/Auth.svelte'; // Import Auth component

  export let modalTypeToShow; // Declare modalTypeToShow prop

  let showModal = false;
  let activeTab = 'register';

  // Watch for changes in modalTypeToShow prop
  $: {
    if (modalTypeToShow) {
      showModal = true;
      if (modalTypeToShow === 'login') {
        activeTab = 'login';
      } else {
        activeTab = 'register';
      }
    }
  }

  export function closeModal() {
    showModal = false;
    activeTab = 'register'; // Reset active tab when closing the modal
    modalTypeToShow = null; // Reset modalTypeToShow prop
  }
</script>

{#if showModal}
  <div class="fixed inset-0 z-50 flex items-center justify-center bg-black bg-opacity-50">
    <div class="bg-white p-6 rounded-lg shadow-lg max-w-md relative">
      <button on:click={closeModal} class="absolute top-0 right-0 m-4 text-gray-700 hover:text-black focus:outline-none">
        <svg class="h-6 w-6 fill-current" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20">
          <path fill-rule="evenodd" d="M2.293 2.293a1 1 0 011.414 0L10 8.586l6.293-6.293a1 1 0 111.414 1.414L11.414 10l6.293 6.293a1 1 0 01-1.414 1.414L10 11.414l-6.293 6.293a1 1 0 01-1.414-1.414L8.586 10 2.293 3.707a1 1 0 010-1.414z" clip-rule="evenodd"/>
        </svg>
      </button>
      <div class="tabs">
        <button class="tab" class:selected={activeTab === 'register'} on:click={() => activeTab = 'register'}>Register</button>
        <button class="tab" class:selected={activeTab === 'login'} on:click={() => activeTab = 'login'}>Login</button>
      </div>
      {#if activeTab === 'register'}
        <!-- Render register form -->
        <Auth formType="register" on:close={closeModal} />
      {:else if activeTab === 'login'}
        <!-- Render login form -->
        <Auth formType="login" on:close={closeModal} />
      {/if}
    </div>
  </div>
{/if}

<style>
  /* Modal styles */
  .modal-overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.5);
    z-index: 9999;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .modal {
    background-color: white;
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  }

  .tabs {
    display: flex;
    margin-bottom: 1rem;
  }

  .tab {
    cursor: pointer;
    padding: 0.5rem 1rem;
    border: none;
    background-color: transparent;
    color: #333;
    font-size: 1rem;
    border-radius: 0.25rem 0.25rem 0 0;
  }

  .tab:selected {
    background-color: #e2e8f0;
  }
</style>
