<script>
let todoText = "";
export let onAdd;
let onClickAdd = (e) => {
	onAdd(todoText);
	todoText = "";
	return false;
}
</script>

<style>
input {
	width: 90%;
}
div {
	margin-top: 15px;
}
</style>

<div>
	<form on:submit|preventDefault={onClickAdd}>
		<input bind:value={todoText} type="text"/>
		<button>Add</button>
	</form>
</div>
