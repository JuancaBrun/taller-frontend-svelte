<script>
    import { Route } from "svelte-routing";
    import Clientes from "./Clientes.svelte";
    import Inicio from "./Inicio.svelte";
    import Piezas from "./Piezas.svelte";
    import Vehiculos from "./Vehiculos.svelte";
</script>

<main>
    <Route path="/" component={Inicio} />
    <Route path="/piezas" component={Piezas} />
    <Route path="/vehiculos" component={Vehiculos} />
    <Route path="/clientes" component={Clientes} />
</main>
