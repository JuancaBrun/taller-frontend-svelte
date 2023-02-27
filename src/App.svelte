<script>
	import { Router } from "svelte-routing";
	import Contenido from "./Contenido.svelte";
	import Footer from "./Footer.svelte";
	import Nav from "./Nav.svelte";
</script>

<Router>
	<Nav />
	<Contenido />
	<Footer />
</Router>

<style>
	:global(body) {
		margin: 0 auto;
		padding: 0;
		font-family: "Aclonica";
		background-color: #1b203e;
		color: white;
	}

	:global(h1) {
		text-align: center;
	}

	:global(a) {
		text-decoration: none;
	}
</style>
