<script lang="ts">
	import Background from './background.svelte';
	import Header from './header.svelte';
	import viewport from './useViewportAction';

	let visible = false;
</script>

<Background>
	<Header />
	<div
    style="opacity: {visible ? 1 : 0}; scale: {visible ? 1 : 0}; rotate: {visible ? '-20deg' : ''}"
		use:viewport
		on:exitViewport={() => (visible = false)}
		on:enterViewport={() => (visible = true)}
		class="card"
	/>
</Background>

<style>
	.card {
		height: 400px;
		width: 300px;
		background-color: black;
		display: flex;
		align-self: flex-end;
		border-radius: 15px;
		margin: 50px;
		transition: 0.5s all, 1.5s rotate cubic-bezier(0.2, 0.9, 0.2, 1);
	}
</style>
