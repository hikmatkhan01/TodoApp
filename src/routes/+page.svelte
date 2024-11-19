<script>
    import Nested from "$lib/components/Nested.svelte";
    import Table from "$lib/components/Table.svelte";
    let todos = $state([
      { id: 1, name: "fisrt task",  date: new Date().toLocaleString(), cond: false },
      { id: 2, name: "second task", date: new Date().toLocaleString(), cond: true },
      { id: 3, name: "third task",  date: new Date().toLocaleString(), cond: false },
    ]);
  
    function changeTodos(todo_name) {
      todos.push({ id: todos.length + 1, name: todo_name, date: new Date().toLocaleString(), cond: false });
    }
  </script>
  
  <div class="h-screen w-full">
    <div class="w-[80%] bg-white shadow-lg m-auto p-4">
      <div class="ali">
        <Nested {todos} {changeTodos} />
      </div>
      <div class="mt-20">
        <h2 class="text-2xl font-semibold text-gray-800 mb-4">Todos List</h2>
  
        <Table {todos} />
      </div>
    </div>
  </div>
  