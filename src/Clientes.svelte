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

<Buscar bind:busqueda={patron} />

<hr />

<Cliente bind:cliente={clienteInsertar}>
    <Boton documento={clienteInsertar} />
</Cliente>
<br />

{#each datosFiltrados as cliente}
    <br />
    <Cliente bind:cliente>
        <Boton tipo="modificar" documento={cliente} />
        <Boton tipo="eliminar" documento={cliente} />
    </Cliente>
    <br />
    <br />
{/each}
