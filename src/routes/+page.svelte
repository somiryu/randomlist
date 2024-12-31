<script>
    import Game from "$lib/Game.svelte";

  let gameView = "home"
</script>


<playground-area>
  {#if gameView === "home"}
    <h1>Escoge un juego</h1>
    <p>Te lanzaremos una palabra o frase aleatoria</p>
    <button on:click={()=> gameView = "nouns"}>Sustantivos</button>
    <button on:click={()=> gameView = "stats"}>Estadístico</button>
  {:else}
    <Game bind:cat={gameView}/>
  {/if}
</playground-area>

<style>
  :global(html){background-color: black; color: white}
  playground-area{
    height: 100dvh; width: 100vw; padding: 2rem;
    display: flex; text-align: center; justify-content: center;
    flex-direction: column;
    box-sizing: border-box;
  }

  :global(button){
    background-color: black; color: white; border: 2px solid white;
    cursor: pointer; transition: .5s; width: 30rem; margin: 1rem auto; padding: 2rem; 
    font-size: 1rem;
  }

  :global(button):hover{scale: 1.1}
</style>