<script>
	async function getHsApi() {
		const res = await fetch(`https://us.api.blizzard.com/hearthstone/cards?locale=ru_RU&page=17&access_token=USQzWMJ1j6LnufYJS0QEe8PnlVkBozk4nv`);
		if (res.ok) {
			return await res.json();
		} else {
			throw new Error('lala');
		}
	}

	async function getAllCards() {
        const res = await getHsApi();
		console.log(res.cards)
		return res.cards;
    }

	let promise = getAllCards();
	let randomIndex = randomInteger(0,39);
	function handleClick() {
		promise = getAllCards();
		randomIndex = randomInteger(0,39)
	}

	function randomInteger(min, max) {
  let rand = min - 0.5 + Math.random() * (max - min + 1);
  return Math.round(rand);
}

	</script>

<main>
	<div class="content">
		<div class="image">
			<p>
				{#await promise}
			<p>...подождите</p>
				{:then card}
			<p><img src={card[randomIndex].image} alt="Карта"></p>
				{:catch error}
			<p style="color: red">{error.message}</p>
				{/await}
			</p>
		</div>
		<div class="descr">
			<p>
				{#await promise}
			<p>...подождите</p>
				{:then card}
			<p>{card[randomIndex].flavorText}</p>
				{:catch error}
			<p style="color: red">{error.message}</p>
				{/await}
			</p>
		</div>
	</div>
	<button on:click={handleClick}>
		получить случайную карту
	</button>
</main>

<style>
	.content {
		display: flex;
		align-items: center;
	}
	.descr {
		width: 15rem;
		color:rgb(156, 125, 22);
	}
	img {
		height: 15rem;
	}
	main {display: flex;
	align-items: center;
	justify-content: space-between;
	
}
	button {
	margin-left: 2rem;
    height: 4rem;
    width: 12rem;
    background-color: rgb(156, 125, 22);
    border-color: #f1c40f;
    color: #f7e7a8;
    font-size: 1.25rem;
    background-image: linear-gradient(45deg, #f1c40f 50%, transparent 50%);
    background-position: 100%;
    background-size: 400%;
    transition: background 300ms ease-in-out;
  }
  button:hover {
    background-position: 0;
    color: #aaa;
  }
</style>