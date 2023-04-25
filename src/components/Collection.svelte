<script>
    import Cards from './Cards.svelte'
    export let savedCards
</script>

<main class='page'>
    
    
    {#if savedCards.length > 0}
        <div class="cards">
            {#each savedCards as c}
                <Cards {c} bind:savedCards={savedCards}/>
            {/each}
        </div>
    {:else}
        <h1>Collection</h1>
    {/if}

    
    
</main>

<style>
    main{
        overflow: scroll;
        position: relative;
    }
    .cards{
        margin-top: 10rem;
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
        justify-content: center;
        align-items: center;
        grid-gap:3rem 0.5rem;
        width:100vw;
        padding: .4rem;
    }
    
</style>