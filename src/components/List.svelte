<script>
    import Cookies from 'js-cookie'

    let list = Cookies.get('list');

    setInterval(function(){ 
    list = Cookies.get('list');
}, 1);

    $: todoData = JSON.parse(list);
    $: arrayList = JSON.parse(list);
    $: arrayList.splice(0, 1)
   


    const remove = (todo) => {
        let todoPosition = arrayList.indexOf(todo) + 1;
        todoData.splice(todoPosition ,1);
        Cookies.set('list', JSON.stringify(todoData))
    };
</script>

<div class="container">

{#each arrayList as todoList}
<article class="card">
    <li>
        <header>
            <h3>{todoList}</h3> <button class="" on:click={remove(todoList)}>Remove</button>
        </header>
        
    </li>
</article>
{/each}

</div>

<style>
    .container {
        display: flex;
        flex-direction: column-reverse;
    }

    li {
        list-style-type: none;
    }

    header {
        display: flex;
        align-items: center;
    }

    button {
        margin-left: auto;
    }


</style>

