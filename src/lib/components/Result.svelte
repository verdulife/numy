<script lang="ts">
	import { _nums } from '$lib/dictionaries/numbers';
	export let req: string;

	let res: string = req;
	$: parsed = res;

	$: if (req) {
		console.log(req);

		_nums.forEach((num) => {
			const regex = new RegExp(num.t, 'g');
			res = res.replace(regex, num.n);
		});

		parsed = eval(res);
	}
</script>

<code>{res}</code>

<style lang="scss">
	code {
		color: $link;
		font-size: 18px;
		padding: 0 60px;
	}
</style>
