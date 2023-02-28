<script>
    export let cliente = { nombre: "", apellidos: "" };
</script>

<div class="container-fluid datos mx-3 my-3">
    <div class="row">
        <div class="col-12">
            <div class="row">
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
                />
            </div>
        </div>
    </div>
    <br />

    <slot />
</div>
