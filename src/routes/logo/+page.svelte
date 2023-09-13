<script lang="ts">
	import { a } from './pos'
	$: b = 800 - $a
	$: r = $a / 2
	$: rr = r * 1.4
	$: d = 0.4 * r
</script>

<div class="container my-4">
	<div class="my-4">
		<input class="form-control" bind:value={$a} type="range" min="0" max="800" />
	</div>
	<div>
		{$a}
		{b}
	</div>
	<div class="d-inline">
		<svg
			viewBox="0 0 800 800"
			fill="white"
			xmlns="http://www.w3.org/2000/svg"
			transform="rotate(0)"
		>
			<rect class="water" width="800" height="800" fill="hsl(194, 100%, 32%)" />
			<polygon class="shan" points="0,800 0,{$a} {800 - (d + rr)},800" />
			<circle class="re" cx={0} cy={r} {r} />
			<circle class="moon" cx={800 - (d + rr)} cy={d + rr} r={rr} />
		</svg>
	</div>
</div>

<style>
	.d-inline {
		font-size: 0;
		width: 400px;
	}
	svg {
		width: auto;
		height: auto;
		width: 400px;
	}
</style>
