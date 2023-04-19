<script>
    import Cards from "./Cards.svelte";
    export let savedCards

  
    
    fetch("./assets/tarot-images.json")
    .then( res => res.json())
    .then(json => {
      console.log(json)
      if(json.cards) savedCards = json.cards
      console.log(savedCards)
    })
    .catch(function (error) {
      // handle what went wrong
      console.log(error)
    });
       
</script>

<main class='page'>
    <div class="kort">
      {#each savedCards as c}
        <Cards {c} bind:savedCards={savedCards}/>
      {/each}
    </div>
</main>

<style></style>