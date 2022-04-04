<script lang="ts">
	import 'verdu/fonts/circular.css';
	import 'verdu/fonts/operator.css';
	import Toolbar from '$lib/components/Toolbar.svelte';
</script>

<main>
	<div class="scroll">
		<Toolbar />
		<slot />
	</div>
</main>

<style lang="scss">
	:global {
		@import 'verdu/_reset.scss';
		@import 'verdu/verdu.scss';
	}

	main {
		background: $white;

		@media (prefers-color-scheme: dark) {
			background: $black;
		}
	}
</style>
