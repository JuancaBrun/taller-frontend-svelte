<script>
	import { setContext } from "svelte";
	import { Router } from "svelte-routing";
	import Contenido from "./Contenido.svelte";
	import Footer from "./Footer.svelte";
	import Nav from "./Nav.svelte";

	const URL = {
		piezas: "https://tallermecanico.herokuapp.com/api/piezas",
		vehiculos: "https://tallermecanico.herokuapp.com/api/vehiculos",
		clientes: "https://tallermecanico.herokuapp.com/api/clientes",
	};

	setContext("URL", URL);
</script>

<Router>
	<Nav />
	<Contenido />
	<Footer />
</Router>
<div id="OK">😊</div>
<div id="KO">😟</div>

<style>
	:global(body) {
		margin: 0 auto;
		padding: 0;
		background-color: #1b203e;
		color: white;
	}

	:global(main) {
		padding-bottom: 100px;
		background-color: #1b203e;
		color: white;
	}

	:global(h1) {
		text-align: center;
	}

	:global(a) {
		text-decoration: none;
	}

	:global(div#OK, div#KO) {
		display: none;
		position: fixed;
		top: 60px;
		right: 0px;
		font-size: 60px;
		background-color: transparent;
	}
</style>
