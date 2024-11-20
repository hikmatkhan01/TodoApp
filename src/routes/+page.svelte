<script>
	import Nested from '$lib/components/Nested.svelte';
	import Table from '$lib/components/Table.svelte';
	let todos = $state([
		{ id: 1, name: 'fisrt task', date: new Date().toLocaleString(), cond: false },
		{ id: 2, name: 'second task', date: new Date().toLocaleString(), cond: true },
		{ id: 3, name: 'third task', date: new Date().toLocaleString(), cond: false }
	]);


    let filter = $state('all');
	let value = $state("");
	const filteredTodos = $derived(filter === 'all'? todos: todos.filter(todo => (filter === 'active' ? !todo.cond : todo.cond)));

	function changeTodos(todo_name) {
		todos.push({
			id: todos.length + 1,
			name: todo_name,
			date: new Date().toLocaleString(),
			cond: false
		});
	}
</script>

<div class="h-screen w-full">
	<div class="m-auto w-[80%] bg-white p-4 shadow-lg">
		<div class="ali">
			<Nested {filter}  {changeTodos} />
		</div>
		<div class="mt-20">
			<h2 class="mb-4 text-2xl font-semibold text-gray-800">Todos List</h2>

			<Table {filteredTodos} />
		</div>
	</div>
</div>
