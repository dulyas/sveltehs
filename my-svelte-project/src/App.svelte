<script>
	import Header from './Header.svelte';
	const bgImg = 'https://images.blz-contentstack.com/v3/assets/bltc965041283bac56c/blt0c6db71db535f97a/5f8df46861a67a1420846b72/homepage_tavern_background.jpg';
	import RandomCard from './RandomCard.svelte'
</script>

<div class="bg" style="background-image: url({bgImg})">
	<div class="container">
		<Header/>
		<RandomCard/>
	</div>
</div>


<style>
	.bg {
		min-height: 100vh;
	}

	.container { 
		max-width: 1140px;
		margin: auto;
	}

</style>