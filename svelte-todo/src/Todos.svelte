<script>
    import {fly} from 'svelte/transition'
    let todoItem='';
    let todoList=[];

    function addToList() {
        if (!todoItem) return;
        todoList = [...todoList, {
            text: todoItem
        }];
        todoItem='';
    }

    function removeFromList(index) {
        todoList.splice(index, 1);
        todoList = todoList;
    }
</script>


<form on:submit|preventDefault={addToList}>
    <input class= "input is-rounded input is-small" bind:value={todoItem}>
</form>

<ol class="todo-list">
    {#each todoList as item, index}
        <li transition:fly= "{{ y: 20, duration: 200 }}">
            <input bind:checked={item.status} class="checkbox" type="checkbox">
            <span>{item.text}</span>
            <button class= "delete is-small" on:click={() => removeFromList(index)}></button>
        </li>
    {/each}
</ol>


<style>
    .todo-list {
        display:contents;
        list-style: none;
    }

</style>