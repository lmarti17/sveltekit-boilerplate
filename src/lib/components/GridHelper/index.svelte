<script>
	let showGrid = false;

	const toggleGrid = (e) => {
		if (e.keyCode === 71) {
			showGrid = !showGrid;
		}
	};
</script>

<svelte:document on:keydown={(e) => toggleGrid(e)} />

{#if showGrid}
	<div class="gridHelper container">
		{#each Array(12) as column}
			<div class="column" />
		{/each}
	</div>
{/if}

<style lang="scss">
	.gridHelper {
		pointer-events: none;

		position: fixed;
		top: 0;
		left: 50%;
		width: grid(12);
		height: 100vh;
		z-index: 999;

		transform: translate3d(-50%, 0, 0);

		display: grid;
		gap: $gutter;
		grid-template-columns: repeat(12, 1fr);
		grid-template-rows: 100vh;

		opacity: 0.2;
	}

	.column {
		background-color: red;
	}

	@include tablet-portrait {
		.gridHelper {
			width: gridM(8);
			grid-template-columns: repeat(8, 1fr);
			gap: $gutter-m;
		}
	}
</style>
