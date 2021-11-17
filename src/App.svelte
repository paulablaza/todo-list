<script>
	//node_modules
	import Cookies from 'js-cookie';
	import "../node_modules/picnic/picnic.min.css";

	//components
	import Form from './components/Form.svelte'
	import List from './components/List.svelte'

	const list = Cookies.get('list')
	if (list === undefined) {
		Cookies.set('list', JSON.stringify(['easter egg']));
	} else {
		console.log('you have the easter egg')
	}
</script>

<div class="center">
	<h1>Todo List</h1>
	<div class="container">

		<Form/>
		<List/>
	
	</div>
</div>




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
</style>