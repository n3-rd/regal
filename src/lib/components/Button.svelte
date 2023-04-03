<script>
	export let content = '';
	export let radius = '0';
	export let color = 'blue';
	export let textColor = 'white';
	export let rounded = false;
	export let size = 'md';
	export let manualSize = null;

	// Define an object to map the predefined size options to their corresponding pixel values
	const sizeMap = {
		xs: '10px',
		sm: '20px',
		md: '30px',
		lg: '40px',
		xl: '50px'
	};
</script>

<button
	style="
		background-color: {color};
        color: {textColor};
		border-radius: {rounded ? '50%' : radius + 'px'};
        font-size: {manualSize ? manualSize + 'px' : sizeMap[size]};
	"
>
	{content}
</button>

<style>
	button {
		/* make aesthetic and fancy */
		border: none;
		padding: 10px;
		cursor: pointer;
		transition: filter 0.2s;
	}
	button:hover {
		filter: brightness(1.3);
	}
</style>
