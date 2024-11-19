<script>
  let { todos } = $props();
</script>

<!-- {#each todos as todo}
  <li>{todo.name}</li>
{/each} -->

<table class="min-w-full table-auto border-collapse">
  <thead class="bg-gray-200">
    <tr>
      <th class="px-4 py-2 text-left text-sm font-medium text-gray-700">ID</th>
      <th class="px-4 py-2 text-left text-sm font-medium text-gray-700">Name</th
      >
      <th class="px-4 py-2 text-left text-sm font-medium text-gray-700"
      >Date</th
    >
      <th class="px-4 py-2 text-left text-sm font-medium text-gray-700"
        >Completed</th
      >
      <th class="px-4 py-2 text-left text-sm font-medium text-gray-700"
        >Actions</th
      >
    </tr>
  </thead>
  <tbody>
    {#each todos as todo}
      <tr class="border-b">
        <td class="px-4 py-2 text-base text-black">{todo.id}</td>
        <td
          class="px-4 py-2 text-base text-black {todo.cond
            ? 'line-through'
            : ''}">{todo.name}  
       </td>
        <td><span class="text-gray-500 text-sm">{todo.date}</span></td>
        <td><input bind:checked={todo.cond} type="checkbox" class=" ml-10" />
        </td>
        <td class="px-4 py-2 text-sm">
          <!-- <button
            class="text-red-500 hover:text-red-700"
            onclick={() => handelDelete(todo.id)}
          > -->
            <button class="text-red-500 hover:text-red-700"   onclick={() => todos = todos.filter(t => t.id !== todo.id)}>

            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="w-5 h-5"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M6 18L18 6M6 6l12 12"
              />2
            </svg>
          </button>
        </td>
      </tr>
    {/each}
  </tbody>
</table>
