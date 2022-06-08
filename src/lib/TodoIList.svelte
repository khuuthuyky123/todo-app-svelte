<script>
  import TodoItem from "./TodoItem.svelte";
  export let todoList;
</script>

<h3>Todo List</h3>
<ul>
  {#each todoList as item, index}
    <TodoItem bind:todoList {item} {index} />
  {/each}
</ul>

<style>
  ul {
    margin: 0;
    padding: 0;
  }
</style>
