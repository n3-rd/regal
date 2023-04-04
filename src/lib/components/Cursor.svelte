<script>
	import { onMount } from 'svelte';

	export let size = 20;
	export let color = 'black';
	export let shape = 'circle';
	export let mixBlendMode = 'none';

	let x = -100;
	let y = -100;

	const cx = size / 2;
	const cy = size / 2;

	onMount(() => {
		document.addEventListener('mousemove', (e) => {
			x = e.clientX;
			y = e.clientY;
		});
		const hoverables = document.querySelectorAll('.hoverable');
		const links = document.querySelectorAll('a');
		hoverables &&
			links.forEach((hoverable) => {
				hoverable.addEventListener('mouseenter', () => {
					// increase size relative to the current size
					size = size * 1.5;
				});
				hoverable.addEventListener('mouseleave', () => {
					// decrease size relative to the current size
					size = size / 1.5;
				});
			});
	});
</script>

<div
	class="custom-cursor {shape}"
	style="left: {x - cx}px; top: {y -
		cy}px; width: {size}px; height: {size}px; background-color: {color}; mix-blend-mode: {mixBlendMode};"
/>

<style>
	.custom-cursor {
		position: fixed;
		border-radius: 50%;
		pointer-events: none;
		z-index: 99999;
		/* Customize your cursor styles here */
		transition: all 0.2s cubic-bezier(0.28, 0.8, 0.36, 1);
	}

	.custom-cursor.square {
		border-radius: 0;
	}
</style>
