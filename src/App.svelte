<script>
	let name = 'John Doe';
	let points = 30;
	let showContainer = false;
	let comment = "More Endurence is needed!";

	const changeContainer = () => {
		if(showContainer) {
			showContainer = false;
		}
		else {
			showContainer = true;
		}
	}

	const commentChanger = (points) => {
		if(points < 50) {
			comment = "More Endurence is needed!";
		}
		else {
			comment = "Congret! You are up to the goal!";
		}
		return comment;
	}

	const addPoint = () => points += 1;
	const removePoint = () => points -= 1;
</script>

<style>
	h1 {
		color: red;
	}

	p {
		color: blue;
	}
</style>

<div class="container">
	<div class="card">
		<h1>
			{name}
			<button class="btn btn-sm" on:click={changeContainer}>edit</button>
		</h1>
		<h3>{points}</h3>
		{#if showContainer}
			<button class="btn" on:click={addPoint}>+1</button>
			<button class="btn dark" on:click={removePoint}>-1</button>
			<input type="number" bind:value={points} />
		{/if}
		<p>{commentChanger(points)}</p>
	</div>
</div>