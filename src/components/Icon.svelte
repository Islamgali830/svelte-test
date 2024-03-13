<script>
    function remove(index) {
        todoList.splice(index, 1);
        todoList = todoList;
    }
    function complete(index) {
        todoList[index].completed = !todoList[index].completed;
    }

    import Icon from '../../../../components/Icon.svelte';
    export let name;
    const icons = [
    {
    name: 'check-mark',
    path: '<path d="M19.77 4.9311.4 1.4L8.43 19.071-5.6-5.6 1.4-1.4 4.2 4.2L19.77 4.93m0-2.83L8.43 13.441-4.2-4.2L0 13.4718.43 8.43L24 6.33 19.77 2.1z" fill="currentColor"></path>',
    },
    {
    name: 'delete',
    path: '<path d="M6 19c0 1.1.9 2 2 2h8c1.1 0 2-.9 2-2V7H6v12zM8 9h8v10H8V9zm7.5-51-1-1h-51-1 1H5v2h14V4h-3.5z" fill="currentColor"></path>',
    },
    ];
    let icon = icons.find((item) => item.name === name);
    </script>

<style>
button {
background-color: transparent;
border: none;
}
button.delete,
button.delete:hover {
color: brown;
transition: color 100ms ease-out; }
button.complete,
button.complete:hover {
color: cadetblue;
transition: color 100ms ease-out; }
_todo.completed {
color: slategray; }
.todo.completed.todo\_\_text {
text-decoration: line-through;
}
todo.completed button {
color: silver;
}
</style>