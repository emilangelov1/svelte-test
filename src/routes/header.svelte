<script lang="ts">
	let innerHeight = 0;
	$: headerStyles =
		innerHeight == 0
			? 'box-shadow: 0px 0px 0px 0px rgba(0, 0, 0, 0)'
			: 'box-shadow: -0px 30px 50px -10px rgba(0, 0, 0, 0.6); backdrop-filter: blur(10px); background-color: rgba(118, 76, 41, 0.9);';
</script>

<svelte:window bind:scrollY={innerHeight} />

<div class="header" style={headerStyles}>
	<div class="container">
		<p class="headerText">Testing Sveltekit out</p>
		<button class="themeButton" />
	</div>
</div>

<style>
	.header {
		position: fixed;
		height: 100px;
		width: 100%;
		background-color: rgba(118, 76, 41, 1);
		transition: 0.4s all cubic-bezier(0.2, 0.9, 0.3, 1.5);
		display: flex;
		justify-content: center;
		align-items: center;
		position: fixed;
	}
	.headerText {
		font-family: 'AM-JP UD Shin Go NT Pr6N';
		font-style: normal;
		font-weight: 600;
		font-size: 34px;
		line-height: 72px;
		color: white;
	}
	.container {
		width: 60%;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	.themeButton {
		all: unset;
		width: 50px;
		height: 50px;
		background: rgb(211, 96, 96);
		border-radius: 6px;
		padding: 0px 2px;
		transition: 0.5s all cubic-bezier(0.2, 0.9, 0.3, 1.5);
		cursor: pointer;
	}

	.themeButton:hover {
		scale: 1.1;
		box-shadow: 0px 0px 40px -5px rgba(0, 0, 0, 0.3);
	}
</style>
