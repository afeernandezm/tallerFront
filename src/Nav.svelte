<script>
    import { Link } from "svelte-routing";
</script>

<nav>
    <ul>
        <li><Link to="/">Inicio</Link></li>
        <li><Link to="/piezas">Piezas</Link></li>
        <li><Link to="/clientes">Clientes</Link></li>
    </ul>
</nav>

<style>
    nav {
        background-color: rgb(0, 0, 0);
        padding: 20px;
        color: white;
        text-decoration: none;
    }

    ul {
        display: flex;
        justify-content: space-around;
        list-style-type: none;
    }
</style>
