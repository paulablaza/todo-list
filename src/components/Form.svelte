<script>
  //node_modules
  import Cookies from 'js-cookie';

  //components

  let name = '';

  const addTodo = (input) => {
    let list = Cookies.get('list');
    if (list !== undefined) {
      let jsonList = JSON.parse(list);
      let stringList = JSON.stringify([...jsonList, input]);
      Cookies.set('list', stringList);
    }
  };

  const submit = () => {
    if (name !== '') {
      if (JSON.parse(Cookies.get('list')).includes(name)) {
        alert('Already added');
      } else {
        addTodo(name);
      }
    } else {
      alert('Add something');
    }
  };
</script>

<form on:submit|preventDefault={submit}>
  <input maxlength="20" bind:value={name} />
  <span style="color: red;">max char: 20</span>
</form>

<style>
  form {
    margin-left: 15px;
    margin-right: 15px;
    margin-bottom: 10px;
  }

  input {
    background-color: #f5cece;
    color: #885a5a;
  }
</style>
