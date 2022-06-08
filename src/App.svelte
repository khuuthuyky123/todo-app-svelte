<script>
  import AddNew from "./lib/AddNew.svelte";
  import TodoIList from "./lib/TodoIList.svelte";

  let todoList = [
    { text: "Write my first post", status: true },
    { text: "Upload the post to the blog", status: false },
    { text: "Publish the post at Facebook", status: false },
  ];
  function handleAddItem() {
    console.log(todoList);
  }
</script>

<div class="container">
  <TodoIList bind:todoList />
  <AddNew bind:todoList on:add={handleAddItem} />
</div>

<style>
  .container {
    width: 400px;
    margin: 0 auto;
    margin-top: 100px;
  }
  :global(h3) {
    color: #333;
    font-weight: bold;
    font-size: 25px;
    border-bottom: 2px solid #333;
    padding: 30px 0 3px 0;
    margin: 0 0 20px;
    text-transform: uppercase;
  }
</style>
