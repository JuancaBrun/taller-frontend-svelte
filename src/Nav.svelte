<script>
    import { Link } from "svelte-routing";
</script>

<nav>
    <ul>
        <li class="menu-item">
            <Link to="/"
                ><span id="inicio-link" class="menu-link"
                    ><img src="../favicon.ico" alt="" /></span
                ></Link
            >
        </li>
        <li class="menu-item">
            <Link to="/piezas"
                ><span id="piezas-link" class="menu-link">🔩</span></Link
            >
        </li>
        <li class="menu-item">
            <Link to="/vehiculos"
                ><span id="vehiculos-link" class="menu-link">🚗</span></Link
            >
        </li>
        <li class="menu-item">
            <Link to="/clientes"
                ><span id="clientes-link" class="menu-link">👥</span></Link
            >
        </li>
    </ul>
</nav>

<style>
    nav {
        background-color: #111426;
        font-family: "Aclonica";
        padding: 10px;
    }
    ul {
        display: flex;
        justify-content: space-around;
        list-style-type: none;
        align-items: center;
    }
    .menu-item {
        font-size: 20px;
    }
    .menu-item img {
        width: 50px;
    }
    .menu-link {
        text-decoration: none;
        color: white;
    }

    @media all and (min-width: 600px) {
        /* #inicio-link::after {
            content: "Inicio";
        } */

        #piezas-link::after {
            content: "Piezas";
        }

        #vehiculos-link::after {
            content: "Vehículos";
        }

        #clientes-link::after {
            content: "Clientes";
        }
    }
</style>
