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
    for (let i = 0; i < 3; i++) {
      let idx = Math.floor(Math.random() * cardStock.length);
      newCards = [...newCards, (cardStock[idx])]
      cardStock.splice(idx, 1);
    }
    console.log(newCards)
  }
     
</script>

<main class='page'>
  <button on:click={drawCards}>Træk kort</button>
  <div class="kort">
    {#each newCards as c}
      <Cards {c} />
    {/each}
  </div>
  <button on:click={addCards}>Gem kort</button>
</main>

<style>

</style>