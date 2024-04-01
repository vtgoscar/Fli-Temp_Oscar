<!-- Modal.svelte -->
<script lang="ts">
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

		// Remove the overlay and modal elements
		const overlay = document.querySelector('.modal-overlay');
		const modal = document.querySelector('.modal');

		if (overlay) overlay.remove();
		if (modal) modal.remove();

		// Refresh the page
		location.reload(); // Refresh the page
		console.log('refresh');
	}
</script>

{#if showModal}
	<div class="fixed inset-0 z-50 flex items-center justify-center bg-black bg-opacity-50">
		{#if activeTab === 'register'}
			<!-- Render register form -->
			<Auth formType="register" on:close={closeModal} />
		{:else if activeTab === 'login'}
			<!-- Render login form -->
			<Auth formType="login" on:close={closeModal} />
		{/if}
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

	/* Update button styling */
	button {
		background-color: #4caf50; /* Green */
		border: none;
		color: white;
		padding: 10px 20px;
		text-align: center;
		text-decoration: none;
		display: inline-block;
		font-size: 16px;
		margin: 4px 2px;
		cursor: pointer;
		border-radius: 5px;
	}
</style>
