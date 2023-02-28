<script>
	import { setContext } from "svelte";
	import Nav from "./Nav.svelte";
	import Contenido from "./Contenido.svelte";
	import { Router } from "svelte-routing";
	import 'bootstrap/dist/js/bootstrap.bundle.min.js';
	const URL = {
		piezas: "https://tallerbackend.onrender.com/api/piezas/",
		clientes: "https://tallerbackend.onrender.com/api/clientes/",
	};

	setContext("URL", URL);
</script>

<Router>
	<Nav />
	<Contenido />
</Router>

<style>
	:global(body) {
		margin: 0;
		padding: 0;
	}

	:global(*) {
		margin: 0;
		padding: 0;
	}
</style>
