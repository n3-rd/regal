<script>
	export let size = 50;
	export let topColor = '#333';
	export let bottomColor = '#333';
</script>

<div
	class="diamond"
	style="
    --size:{size}px;
    --topColor:{topColor};
    --bottomColor:{bottomColor}
"
/>

<style>
	.diamond {
		/* Modify size here: */
		--size: 50px;
		--quarter-size: calc(var(--size) / 4);
		--topColor: #333;
		--bottomColor: #333;

		border-style: solid;
		border-color: transparent transparent var(--topColor) transparent;
		border-width: 0 var(--quarter-size) var(--quarter-size) var(--quarter-size);
		height: 0;
		width: calc(var(--size) / 2);
		box-sizing: content-box;
		position: relative;
		margin: 0 0 calc(var(--size) / 2) 0;
	}
	.diamond:after {
		content: '';
		position: absolute;
		top: var(--quarter-size);
		left: calc(var(--quarter-size) * -1);
		width: 0;
		height: 0;
		border-style: solid;
		border-color: var(--bottomColor) transparent transparent transparent;
		border-width: calc(var(--size) * 0.7) calc(var(--size) / 2) 0 calc(var(--size) / 2);
	}
</style>
