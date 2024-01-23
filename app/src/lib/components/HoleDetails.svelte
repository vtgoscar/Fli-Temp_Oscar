<script lang="ts">
	//... other code ...

	interface Hole {
		hole_name: string;
		hole_number: string;
		par: number;
		distance: number;
		not_using: boolean;
		Description: string; // General description
		// You might add more properties here if your description is more structured
		// back9Change: string; // For example, a specific field for Back 9 changes
		//... other properties ...
	}

	export let holeData: Hole;
</script>

<div class="hole-details">
	<h2>{holeData.hole_name}</h2>
	<p><strong>Length:</strong> {holeData.distance} feet</p>
	{#if holeData.Description}
		<div class="description">
			<p>{holeData.Description}</p>
			<!-- If you have structured data, you can add another condition for back9Change -->
			<!-- {#if holeData.back9Change}
                <p><strong>Back 9 Change:</strong> {holeData.back9Change}</p>
            {/if} -->
		</div>
	{/if}
	<!-- Additional hole details here... -->
</div>

<style>
	.hole-details {
		/* Styles for your hole details */
		padding: 1rem;
		border: 1px solid #ccc;
		border-radius: 8px;
		margin-bottom: 1rem;
	}
	.hole-details h2 {
		margin-top: 0;
	}
	.description {
		margin-top: 0.5rem;
	}
</style>
