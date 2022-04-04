<script lang="ts">
	import { _op } from '$lib/dictionaries/operators';
	import { _currency } from '$lib/dictionaries/currency';
	import { getCurrency } from '$lib/scripts/utils';
	export let req: string;

	function getRes() {
		let copy = req;

		_op.forEach(({ input, output }) => {
			const regex = new RegExp(input, 'g');
			copy = copy.replace(regex, output);
		});

		/* _currency.forEach((val) => {
			const regex = new RegExp('in', 'g');
			copy = copy.replace(regex, output);
		}); */

		try {
			return new Function(`return ${copy}`)();
		} catch (error) {
			return '--';
		}
	}

	let res = getRes();
	$: if (req) res = getRes();
</script>

<code>{res || '--'}</code>

<style lang="scss">
	code {
		color: $link;
		font-size: 18px;
		padding: 0 60px;
	}
</style>
