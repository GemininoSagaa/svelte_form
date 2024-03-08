<script>
  let name = "";
  let names = [];

  const addName = () => {
    if (name.trim()) {
      names = [...names, name];
      name = "";
    }
  };

  const clearNames = () => {
    names = [];
  };
</script>

<main>
  <h1>Formulario de Nombres</h1>

  <form on:submit|preventDefault={addName}>
    <label>
      Nombre:
      <input bind:value={name} />
    </label>
    <button class="buttom1" type="submit">Agregar Nombre</button>
  </form>

  {#if names.length > 0}
    <div>
      <h2>Nombres ingresados:</h2>
      <ul>
        {#each names as n (n)}
          <li>{n}</li>
        {/each}
      </ul>
      <button class="buttom2" on:click={clearNames}>Limpiar Nombres</button>
    </div>
  {/if}
</main>

<style>
  h1 {
      color: white;
      font-size: 60px;
      font-family: system-ui, sans-serif;
      width: 100%;
      padding-top: 30px;
      padding-bottom: 30px;
      border-top: 1px solid violet;
      border-bottom: 1px solid violet;
  }

  h2 {
      color: white;
      font-family: system-ui, sans-serif;
  }

  main {
    text-align: center;
    margin: 15px;
  }

  form {
    margin-bottom: 10px;
  }

  .buttom1, .buttom2 {
      background-color: violet;
      border: 3px solid violet;
      border-radius: 8px;
  }

  ul {
    list-style: none;
    padding: 0;
  }

  li {
    margin-bottom: 5px;
  }
</style>
  