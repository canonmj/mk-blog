<script>
	import '../app.css';
	import { onMount } from 'svelte';
	import { fade, fly } from 'svelte/transition';
	import { add_attribute } from 'svelte/internal';

	let display = false;
	let itemObj;

	onMount(() => {
		display = true;
		let arr = new Array(20).fill({ width: '', size: '' });

		itemObj = arr.map(() => {
			let obj = {};
			obj['width'] = Math.random() * 5 + 0.2;
			obj['size'] = Math.floor(Math.random() * window.innerWidth);
			return obj;
		});
	});

	// Math.random() * 5 + 0.2
	// Math.floor(Math.random() * window.innerWidth)
	$: console.log(itemObj);
</script>

<div class="container">
	{#if display}
		{#each itemObj as item}
			<div
				class="i"
				style="
			width: {item.width + 'px'};
			left: {item.size + 'px'}
		"
				transition:fly={{ y: Math.random() * -1000, duration: 5000 }}
			/>
		{/each}
	{/if}
</div>
