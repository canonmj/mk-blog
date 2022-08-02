<script>
	import '../app.css';
	import { onMount } from 'svelte';

	let container;

	onMount(() => {
		let amount = 20;
		let i = 0;
		while (i < amount) {
			const drop = document.createElement('i');

			let size = Math.random() * 5;
			let posX = Math.floor(Math.random() * window.innerWidth);

			drop.style.width = 0.2 + size + 'px';
			drop.style.left = posX + 'px';

			container.appendChild(drop);
			i++;
		}
	});
</script>

<div bind:this={container} class="container" />

<style>
	/* @keyframes -global-animate {
		0% {
			transform: translateY(-200px);
		}
	} */
</style>
