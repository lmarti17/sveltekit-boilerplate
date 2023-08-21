<script>
	import Navigation from '$lib/layout/Navigation/index.svelte';
	import GridHelper from '$lib/components/GridHelper/index.svelte';
</script>

<GridHelper />
<Navigation />

<main>
	<slot />
</main>

<style global lang="scss">
	@import './../styles/custom-reset.scss';

	:root {
		//layout
		--vw: 100vw;
		--vh: 100vh;
		--rem: 1px;

		// base layout
		--layout-max-width: #{$width-reference};
		--layout-margin: #{$margin-reference};

		--layout-min-max-width: min(var(--vw), var(--layout-max-width));

		// fonts
		--font-name: #{$font-name};

		// colors

		--color-white: #fff;
		--color-black: #000;
	}

	html {
		// global
		font-family: var(--font-name);
		font-size: var(--rem);
	}
</style>
