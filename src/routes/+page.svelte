<script>
  /** @type {string[]} */
  let todos = []

  /** @type {string} */
  let description = ''

  function addTodoAction() {
    if (description.length) {
      todos = [...todos, description]
    }
  }
</script>

<h1>Boring Todos</h1>
<p>Todo app coded with svelte</p>

<div>
  <form action="">
    <label for="desc">Add a Todo: </label>
    <input
      type="text"
      required
      placeholder="...your todo here"
      id="desc"
      bind:value={description}
    />
    <button on:click={addTodoAction}>+</button>
  </form>
  <ul>
    {#each todos as todo}
      <li>{todo}</li>
    {/each}
  </ul>
</div>
