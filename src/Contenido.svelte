<script>
    import { Route } from "svelte-routing";
    import Piezas from "./Piezas.svelte";
    import Clientes from "./Clientes.svelte";
    import Inicio from "./Inicio.svelte";
</script>

<main>
    <Route path="/" component={Inicio} />
    <Route path="/piezas" component={Piezas} />
    <Route path="/clientes" component={Clientes} />
</main>
