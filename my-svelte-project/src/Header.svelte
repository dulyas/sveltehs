<script>
let current = 'choseCard';
</script>

<header class="header__wrap">
    <div class="header__descr">Hearthstone DB</div>
    <div class="headers__ref">
        <span 
        class:active="{current ===  'choseCard'}"
        on:click="{() => current = 'choseCard'}"
        >Карты</span>/
        <span 
        class:active="{current ===  'choseDeck'}"
        on:click="{() => current = 'choseDeck'}"
        >Колоды</span>
    </div>
</header>


<style>
    .header__wrap {
        display: flex;
        padding-top: 5rem;
        align-items: center;
        justify-content: space-between;
    }
    .header__descr {
        font-size: 3rem;
        color: transparent;    
	    -webkit-background-clip: text;
	    background-clip: text;
	    background-image: linear-gradient(to right, rgb(255, 174, 0), rgb(221, 151, 1));
    }
    .headers__ref {
        font-size: 1.5rem;
        color: transparent;    
	    -webkit-background-clip: text;
	    background-clip: text;
        background-image: linear-gradient(to right, rgb(255, 174, 0), rgb(221, 151, 1));
        cursor: pointer;
    }
    .active {
        font-size: 1.8rem;
    }
    span {
        transition: 1s all;
    }
</style>