<script>
    import Cards from './Cards.svelte'
    export let savedCards
</script>

<main class='page'>
    <h1>Collection</h1>
    {#each savedCards as gif}
         <!-- content here -->
         <Cards {gif} bind:savedCards={savedCards}/>
    {/each}
</main>

<style>
   
</style>