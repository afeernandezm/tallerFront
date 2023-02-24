<script>
    export let cliente = { nombre: "", apellidos: "" };
</script>

<input
    id="nombre"
    type="text"
    placeholder="Nombre"
    bind:value={cliente.nombre}
/><br />
<input
    id="apellido"
    type="text"
    placeholder="Apellidos"
    bind:value={cliente.apellidos}
/><br />

<slot />
