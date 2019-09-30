<script>
	import { onMount } from 'svelte';
	let todoText = "";
	let inputEle;
	export let onAdd;
	let onClickAdd = (e) => {
		onAdd(todoText);
		todoText = "";
		return false;
	}

	onMount(() => {
    inputEle.focus();
  });
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
		<input bind:this={inputEle} bind:value={todoText} type="text"/>
		<button>Add</button>
	</form>
</div>
