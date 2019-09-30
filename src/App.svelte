<script>
	import { Router, Link, Route } from "svelte-routing";
	import AppRouter from "./Router.svelte";
</script>

<style>

</style>

<div>
	<Router>
		<Link to="/">Home</Link>
		<Link to="/todo">Todo</Link>
	</Router>
	<AppRouter/>
</div>