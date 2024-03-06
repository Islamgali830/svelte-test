<main>
    <form on:submit|preventDefault={add}>
    <input bind:value={newItem} placeholder="Enter to-do" />
    <button class="add-todo" on:click={add}><span>+</span></button>
    </form>
    <div class="todos">
{#each todoList as item, index}
<span class="todo text">{item. task}</span>
<div class="todo buttons"></div>
{/each}
    </div>
</main>

<script>
    let newItem = "";
    let todoList = [];
    function add() {
        if (newItem !=="") {
            todoList = [
                ... todoList,
                {
                task: newItem,
                completed: false,
                },
            ];
                
            newItem ="";
        }
    }
</script>


<style>
main {
display: flex;
flex-direction: column;
align-items: center;
min-height: 100%;
padding: 5v min;
box-sizing: border-box;
background: antiquewhite;
}
form {
width: 100%;
max-width: 500px;
display: flex;
align-items: center;
margin-bottom: 1em;
}
input{
flex-grow: 1;
width: 0;
border: none;
border-bottom: 1px solid black;
background: transparent;
box-shadow: none;
font-size: 1.2rem;
margin: 0;
outline: none;
}
.todo {
display: flex;
padding: 20px;
border-radius: 20px;
box-shadow: 0 0 15px rgba(0 0 0 / 20%);
background-color: hsla(0, 0%, 100%, 0.2);
margin-top: 1rem;
font-size: 1.2rem;
justify-content: space-between;
align-items: center;
}
.todo\_\_buttons {
display: flex;
align-items: center;
margin-left: 1em;
}
.todo button {
width: 32px;
height: 32px;
padding: 4px;
margin: 0;
flex-shrink: 0;
}
</style>
