<script lang="ts">
	import VegasPopUp from '$lib/components/VegasPopUp.svelte';
	import { overlayStore } from '$lib/overlayStore';
	import Icon from '@iconify/svelte';

	let continuousText = '... Placeholder text for the ticker...';

	function toggleVegasPopUp() {
		if ($overlayStore === 'vegas') {
			overlayStore.set('');
		} else {
			overlayStore.set('vegas');
		}
	}

	function closeVegasPopUp() {
		overlayStore.set('');
	}

	function navigateTo(url) {
		window.location.href = url;
	}
</script>

<!-- Main Menu Links -->
<div class="flex justify-center flex-wrap items-center mb-4 sm:mb-0">
	<button class="nav-link" on:click={() => navigateTo('info')}>
		<Icon icon="carbon:information" class="mr-2" />
		<span class="text-lg">Information</span>
		<!-- Increased text size -->
	</button>

	<!-- New Buttons -->
	{#each [{ icon: 'bi:journal-plus', label: 'Subscribe Now' }, { icon: 'bx:bxs-info-circle', label: 'Brand Info' }, { icon: 'bi:people-fill', label: 'Collaborate with us' }, { icon: 'fluent:mail-inbox-fill', label: 'Join our mailing list' }] as { icon, label }}
		<button class="nav-link" on:click={toggleVegasPopUp}>
			<Icon {icon} class="mr-2" />
			<span class="text-lg">{label}</span>
			<!-- Increased text size -->
		</button>
	{/each}
</div>

<style>
	.nav-link {
		display: inline-flex;
		align-items: center;
		background-color: hsl(81, 80%, 41%);
		color: #070707;
		padding: 8px 10px; /* Adjusted padding */
		margin: 6px; /* Added margin */
		border-radius: 4px;
		font-weight: bold;
		text-decoration: none;
		transition: background-color 0.3s ease;
		font-size: 14px;
	}

	.nav-link:hover {
		background-color: #45a049;
	}

	/* Adjust styles for small screens */
	@media screen and (max-width: 640px) {
		.nav-link {
			padding: 10px 16px; /* Adjusted padding */
			margin: 4px; /* Adjusted margin */
			font-size: 14px; /* Decreased font size */
		}
	}
</style>
