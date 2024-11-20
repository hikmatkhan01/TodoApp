<script>
  let {filter, changeTodos } = $props();
  let value = $state("");
</script>


<form>
	<input type="text" bind:value={value} placeholder="enter new task"/>
	
	<select name="" id="" bind:value={filter}>                      
	   <option value="all">ALL</option>
		<option value="active">ACTIVE</option>
		<option value="completed">COMPLETED</option>
	</select>
	<button disabled={!value} onclick={() => {changeTodos(value);value=''}} class="{!value?'bg-gray-500':'bg-blue-700'} p-2 rounded-md">click me</button>
  </form>



<!-- <script>
  let { todos, changeTodos } = $props();
</script>

{JSON.stringify(todos)}
<button onclick={() => changeTodos("do it now")}>click me</button> -->
