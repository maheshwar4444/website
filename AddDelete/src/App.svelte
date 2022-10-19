<script>

	let peopleTask=[];
	let personTask;		
	let yes = false;


	const handleInput = ()=> {
		peopleTask=peopleTask.concat(personTask)
		personTask='';
		
		
	}

	const handleClick= (task) => {
		peopleTask=peopleTask.filter((ele)=> ele!=task)
		personTask='';
		
	
		
	}

</script>

	<div>
		<label for="text">Add New Task</label>
		<input type="text" bind:value={personTask}>
		<button on:click={handleInput}>Add</button>
		

	</div>
	
	{#each peopleTask as task}
	
	  {task} <button on:click={ ()=> handleClick (task)} > Delete </button>
	  
	  <br>
	  <label for="yes">{task? "Completed" : "Not Completed"}
		<input type=checkbox bind:checked={yes}>
		{yes}
		
	</label>
	
{/each}







