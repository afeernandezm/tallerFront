<script>
    import { getContext } from "svelte";
    import { data } from "./store.js";
    import { onMount } from "svelte";
    import Buscar from "./Buscar.svelte";
    import Pieza from "./Pieza.svelte";
    import Boton from "./Boton.svelte";

    let piezaInsertar = {};

    let datosFiltrados = [];
    let patron = "";

    const URL = getContext("URL");

    let getPiezas = async () => {
        const response = await fetch(URL.piezas);
        $data = await response.json();
    };

    onMount(getPiezas);

    $: datosFiltrados = $data.filter((pieza) =>
        RegExp(patron, "i").test(pieza.nombre)
    );
</script>

<Buscar bind:busqueda={patron} />

<hr />

<Pieza bind:pieza={piezaInsertar}>
    <Boton documento={piezaInsertar} />
</Pieza>
<br />

{#each datosFiltrados as pieza}
    <br />
    <Pieza bind:pieza>
        <Boton tipo="modificar" documento={pieza} />
        <Boton tipo="eliminar" documento={pieza} />
    </Pieza>
    <br />
    <br />
{/each}
