<script lang="ts">
	import type { lineType } from '$lib/types';
	import Result from '$lib/components/Result.svelte';

	export let line: lineType;
</script>

<div class="line row nowrap xfill">
	<code class="grow" contenteditable="true" bind:textContent={line.value} />
	<Result bind:req={line.value} />
</div>

<style lang="scss">
	code {
		color: turquoise;
		font-size: 18px;
		padding: 0 60px;

		&:focus {
			background: rgba($white, 0.1);
		}
	}
</style>
