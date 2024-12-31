<script>
  import db from "./db";
  export let cat = "nouns"
  let rolled = false

  function getRandomElement(array) {
    const randomIndex = Math.floor(Math.random() * array.length); // Generate random index
    return array[randomIndex]; // Return the element at the random index
}

  const roll = () => {
    rolled = getRandomElement(db[cat])
  }
</script>

<controls-group>
  <button on:click={()=> cat = "home"}>Atrás</button>
  {#if rolled}
    <button on:click={roll}>Relanzar</button>
  {/if}
</controls-group>
{#if !rolled}
  Vas a recibir una palabra a frase al oprimir el botón
  <button on:click={roll}>*** Roll ***</button>
{:else}
  <h1 on:click={roll}>{rolled}</h1>
{/if}



<style>
  controls-group{display: flex; gap: 1rem; position: fixed; top: 1rem; left: 1rem}
  controls-group > button{width: auto;padding: .5rem}
  h1::first-letter {
    text-transform: uppercase;  
  }
</style>