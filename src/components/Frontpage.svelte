<script>
    import Menuitem from "./Menuitem.svelte";
    export let activePage 
    


</script>

<main class='page'>
    <h2>Tarot reading</h2>
    <div class="text">
        
   <input type="email" name="" id="" placeholder="Username">
    <input type="password" name="" id="" placeholder="Password">
    <button on:click={()=>activePage='Card Dealing'} id="enter" >enter</button>
</div> 
    <img src="https://cdn.discordapp.com/attachments/828977112047288389/1098178866117353565/kort_2.png" alt="" srcset="">
</main>

<style>

    img{
      height: 20rem;
      width: auto;
    }

</style>