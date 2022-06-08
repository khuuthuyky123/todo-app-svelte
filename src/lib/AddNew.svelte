<script>
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();
  export let todoList;
  let newItem = "";

  function submit(e) {
    if (e.keyCode === 13) {
      addToList();
    }
  }

  function addToList() {
    if (newItem == "") return;
    todoList = [...todoList, { text: newItem, status: false }];
    newItem = "";
    dispatch("add");
  }
</script>

<div>
  <h3>Add Item</h3>
  <div class="fg">
    <input
      bind:value={newItem}
      on:keydown={submit}
      type="text"
      placeholder="new todo item.."
    />
    <button on:click={addToList}>Add</button>
  </div>
</div>

<style>
  button {
    border-radius: 4px;
    color: white;
    min-width: 80px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 10pt;
    cursor: pointer;
    background-color: white;
    color: black;
    border: 2px solid #008cba;
    transition-duration: 0.2s;
  }

  button:hover {
    background-color: #008cba;
    color: white;
  }

  input[type="text"] {
    display: inline-block;
    width: 100%;
    font-size: 11pt;
    -webkit-transition: all 0.3s ease-in-out;
    -moz-transition: all 0.3s ease-in-out;
    -ms-transition: all 0.3s ease-in-out;
    -o-transition: all 0.3s ease-in-out;
    transition: all 0.3s ease-in-out;
    outline: none;
    padding: 7px 0px 7px 7px;
    margin: 5px 1px 3px 0px;
    border: 1px solid #dddddd;
    border-left: none;
    border-right: none;
    border-top: none;
  }

  input[type="text"]:focus {
    box-shadow: 0 0 7px rgba(81, 203, 238, 1);
    border: 1px solid rgba(81, 203, 238, 1);
  }
  .fg {
    display: flex;
    justify-content: space-between;
  }

  .fg input {
    margin-right: 10px;
  }
</style>
