<script>
    export let item;
    export let todoList;
    export let index;

    function removeFromList(index) {
    todoList.splice(index, 1);
    todoList = todoList;
  }
</script>

<li>
    <input class=check-done bind:checked={item.status} type="checkbox" />
    <span class={item.status ? "done" : ""}>{item.text}</span>
    <span on:click={() => removeFromList(index)}>❌</span>
</li>

<style>
    
  li {
    display: flex;
    justify-content: space-between;
    align-items: center;
    list-style: none;
    border-bottom: 1px solid #eee;
    font-size: 18px;
    line-height: 40px;
    padding-left: 20px;
  }

  .check-done {
    height : 32px;
    width: 32px;
    border-radius: 10%;
  }

  li span.done {
    text-decoration: line-through;
    color: #ddd;
  }
</style>