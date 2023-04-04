<script>
	export let size = 50;
	export let color = '#333';
</script>

<div
	class="heart"
	style="
    --size:{size}px;
    --color:{color};
"
/>

<style>
	.heart {
		/* Modify size here: */
		--size: 50px;
		--color: #333;

		position: relative;
		width: var(--size);
		height: calc(var(--size) * 0.3);
	}

	.heart:before,
	.heart:after {
		position: absolute;
		content: '';
		left: calc(var(--size) * 0.55);
		top: 0;
		width: calc(var(--size) * 0.55);
		height: calc(var(--size) * 0.85);
		background: var(--color);
		border-radius: calc(var(--size) * 0.55) calc(var(--size) * 0.55) 0 0;
		transform: rotate(-45deg);
		transform-origin: 0 100%;
	}

	.heart:after {
		left: 0;
		transform: rotate(45deg);
		transform-origin: 100% 100%;
	}
</style>
