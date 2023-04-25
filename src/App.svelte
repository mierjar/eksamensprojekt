<script>
	import Menuitem from './components/Menuitem.svelte'
	import Frontpage from './components/Frontpage.svelte'
	import CardDealing from './components/CardDealing.svelte'
	import Collection from './components/Collection.svelte'
	import Notes from './components/Notes.svelte';
	let menu = ['Frontpage', 'Card Dealing', 'Notes', 'Collection']
	let activePage = menu[1]
	let savedCards = []
	let cardStock

	fetch("./assets/tarot-images.json")
    .then( res => res.json())
    .then(json => {
      console.log(json)
      if(json.cards) cardStock = json.cards      
    })
    .catch(function (error) {
      // handle what went wrong
      console.log(error)
    });

</script>

<header>
	{#each menu as item}
		<Menuitem bind:activePage={activePage} title={item} />
	{/each}
</header>
<main>
	{#if activePage == menu[0]}
	<Frontpage bind:activePage={activePage}/>
	{:else if  activePage == menu[1]}
	<CardDealing bind:savedCards={savedCards} {cardStock}/>
	{:else if  activePage == menu[2]}
	<Notes bind:savedCards={savedCards}/>
	{:else if activePage == menu[3]}
	<Collection bind:savedCards={savedCards}/>
	{/if}
</main>
	<footer>
		<img src="https://cdn.discordapp.com/attachments/544280783448440837/1096972314052132924/crystal.png" alt="">
	</footer>

<style>
	:global(*, body){
		box-sizing: border-box;
		margin:0;
		padding:0;
		overflow: hidden;
		position: relative;
	}
	:global(.page){
		display:grid;
		place-items:center;
		height: 75vh;
	}
	header{
		display:grid;
		height:10vh;
		width: 100%;
		grid-auto-flow:column;
		place-items:center;
		background:white;
		color: black;
	}
	footer{
		position: absolute;
		height: 5.5rem;
		width: 100vw;
		bottom: 0;
		z-index: -1;
	}
	img{
		width: 100vw;
		height: auto;
	}
</style>