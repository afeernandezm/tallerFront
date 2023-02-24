<script>
    export let pieza = { nombre: "", precio: 0 };
</script>

<input
    id="nombre"
    type="text"
    placeholder="Nombre"
    bind:value={pieza.nombre}
/><br />
<input
    id="precio"
    type="number"
    placeholder="Precio"
    bind:value={pieza.precio}
/>

<slot />
