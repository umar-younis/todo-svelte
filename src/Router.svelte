<script>
  import { Router, Link, Route } from "svelte-routing";
  import Home from "./Home.svelte";
  import Todo from "./Todo.svelte";
  export let url = "";
</script>

<style>

</style>

<div class="nav-div">
  <Router url={url}>
    <Route path="/" component={Home} />
    <Route path="/todo" component={Todo} />
  </Router>
</div>
