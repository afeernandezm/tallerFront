<script>
    export let pieza = { nombre: "", precio: 0 };
</script>

<div class="container-fluid datos mx-3 my-3">
    <div class="row">
        <div class="col-12">
            <div class="row">
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
            </div>
        </div>
    </div>
    <slot />
</div>
