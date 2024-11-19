<script>
  let { changeTodos } = $props();
  let value = $state("");


</script>

<input type="text" bind:value placeholder="enter new task"/>
<button disabled={!value} onclick={() => {changeTodos(value); value='';}} class="{!value?'bg-gray-500':'bg-blue-700'} p-2 rounded-md">click me</button>

<!-- <script>
  let { todos, changeTodos } = $props();
</script>

{JSON.stringify(todos)}
<button onclick={() => changeTodos("do it now")}>click me</button> -->
