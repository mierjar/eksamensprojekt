<script>
  import Cards from "./Cards.svelte";
  export let savedCards
  export let cardStock
  let newCards = []

  const addCards = () => {
    savedCards = savedCards.concat(newCards)
    console.log(savedCards)
  }

  const drawCards = () => {
    newCards = []
      if(cardStock.length >= 3){
        for (let i = 0; i < 3; i++) {
          let idx = Math.floor(Math.random() * cardStock.length);
          newCards = [...newCards, (cardStock[idx])]
          cardStock.splice(idx, 1);
        }
        console.log(newCards)
      }else{
        //vis fejlmeddelelse
      }
    }
     
</script>

<main class='page'>
  <div class="left">
    <button on:click={drawCards}>Træk kort</button>
    <button on:click={addCards}>Gem kort</button>
  </div>
  <div class="kort">
    {#each newCards as c}
      <Cards {c} />
    {/each}
  </div>
</main>

<style>
  main{
    height:100%;
    grid-template-columns: 1fr 1fr;
  }
</style>