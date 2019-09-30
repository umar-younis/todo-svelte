<script>
	import Input from "./input.svelte";
	let todos = [];
	export let location = "";
	let onAdd = (text) => {
		todos = [...todos, { text: text }];
	}
	let onRemove = (idx) => {
		todos.splice(idx, 1);
		todos = [...todos];
  }
</script>

<style>
	h1 {
		color: purple;
	}
	.main-div {
		margin: auto;
		max-width: 500px;
    text-align: center;
		padding: 10px;
	}
	.todo-holder {
		position: relative;
		padding: 0px;
	}
	.todo-item {
		width: 100%;
		padding: 10px 0px;
		text-align: left;
		border-bottom: 1px solid #aaa;
	}
	h1 {
		margin: 0px;
	}
	.cross {
		position: absolute;
		right: 3px;
		cursor: pointer;
	}
	.cross:hover {
		opacity: 0.7;
	}
</style>

<div class="main-div">
  <p></p>
  {#if todos.length > 0}
		<div class="todo-holder">
			{#each todos as todo, idx}
			<div class="todo-item">
				<h1>
					{todo.text}
					<span on:click={() => onRemove(idx)} class="cross">x</span>
				</h1>
			</div>
			{/each}
		</div>
	{/if}
	<Input onAdd={onAdd}/>
</div>
