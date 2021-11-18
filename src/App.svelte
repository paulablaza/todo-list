<script>
  //node_modules
  import Cookies from 'js-cookie';
  import '../node_modules/picnic/picnic.min.css';

  //components
  import Form from './components/Form.svelte';
  import List from './components/List.svelte';

  const list = Cookies.get('list');
  if (list === undefined) {
    Cookies.set('list', JSON.stringify(['easter egg']));
  } else {
    console.log('you have the easter egg');
  }
</script>

<main>
  <div class="center">
    <h1 style="color: #885A5A;">Todo List</h1>
    <div class="container">
      <Form />
      <List />
    </div>
  </div>
</main>

<style>
  .center {
    display: flex;
    align-items: center;
    flex-direction: column;
  }

  .container {
    width: 100vw;
    max-width: 400px;
  }

  main {
    width: 100%;
    height: 100%;
    background-color: #f7c1bb;
  }
</style>
