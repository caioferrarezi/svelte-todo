<script>
	import TodoForm from './components/TodoForm.svelte'
	import Todos from './components/Todos.svelte'

	let todos = []
	let todoItem = ''

	$: {
		if (todoItem)
			todos = [todoItem, ...todos]
	}
</script>

<style>
	.c-app {
		position: relative;
		background-color: #ffffff;
		max-width: 99.2rem;
		width: 100%;
		margin: 3rem auto 0;
		padding: 3rem 0 4rem;
	}

	.c-app__title {
		font-size: 6rem;
		font-weight: lighter;
		text-align: center;
		margin-bottom: .5em;
		color: var(--dark-light-color);
	}
</style>

<div class="c-app">
	<h1 class="c-app__title">Todo App</h1>

	<TodoForm bind:todoItem />

	<Todos todos={todos} />
</div>
