<script>
    import { getContext } from "svelte";
    import { data } from "./store.js";
    import { onMount } from "svelte";
    import Buscar from "./Buscar.svelte";
    import Cliente from "./Cliente.svelte";
    import Boton from "./BotonCliente.svelte";
    let clienteInsertar = {};

    let datosFiltrados = [];
    let patron = "";

    const URL = getContext("URL");

    let getClientes = async () => {
        const response = await fetch(URL.clientes);
        $data = await response.json();
    };

    onMount(getClientes);

    $: datosFiltrados = $data.filter((cliente) =>
        RegExp(patron, "i").test(cliente.nombre)
    );
</script>

<div class="container-fluid p-4 p-md-3">
    <div style="text-align: center; border: 1px solid black;" class="mt-4">
        <strong>Buscar por nombre</strong>
        <Buscar bind:busqueda={patron} />
    </div>
</div>

<hr />

<Cliente bind:cliente={clienteInsertar}>
    <Boton documento={clienteInsertar} />
</Cliente>
<br />
<div class="row row-cols row-cols-md-2 row-cols-lg-3">
    {#each datosFiltrados as cliente}
        <br />
        <Cliente bind:cliente>
            <Boton tipo="modificar" documento={cliente} />
            <Boton tipo="eliminar" documento={cliente} />
        </Cliente>
        <br />
        <br />
    {/each}
</div>
