<script lang="ts">
	import Line from '$lib/components/Line.svelte';
	import { lineStore } from '$lib/store';
</script>

<div class="wrapper col xfill">
	{#each $lineStore as line}
		<Line {line} />
	{/each}
</div>

<style lang="scss">
	.wrapper {
		padding: 120px 0;
	}
</style>
