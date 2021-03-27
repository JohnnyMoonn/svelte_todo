<script>
	import Todos from './Todos.svelte';
</script>

<main>
	<h1>My To Do-List</h1>
	<Todos />
</main>

<style>
	main {
		text-align: center;
		text-transform: uppercase;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
		font-family: 'New Tegomin', serif;
	}

	h1 {
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>