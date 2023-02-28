<script>
    import { getContext, onMount } from "svelte";
    import { jsonData } from "./store";
    import Cliente from "./Cliente.svelte";
    import Buscador from "./Buscador.svelte";
    import Boton from "./Boton.svelte";

    const URL = getContext("URL");
    let busqueda = "";
    let cliente = {};

    onMount(async () => {
        const response = await fetch(URL.clientes);
        const data = await response.json();
        $jsonData = data;
    });

    $: clientes = $jsonData.filter((item) =>
        RegExp(busqueda, "i").test(item.nombre)
    );
</script>

<div class="d-flex justify-content-end">
    <Buscador bind:busqueda />
</div>
<h2 class="text-center">Insertar cliente:</h2>
<div class="card-group row mx-0">
    <div class="col-sm-6 col-md-4 col-lg-3 mx-auto">
        <Cliente {cliente}>
            <Boton documento={cliente} tipo="insertar" coleccion="clientes" />
        </Cliente>
    </div>
</div>
<h2 class="text-center mt-5">Colección de clientes:</h2>

<div class="clientes-container">
    <div class="card-group row mx-0">
        {#each clientes as cliente}
            <div class="col-sm-6 col-md-4 col-lg-3 mx-0">
                <Cliente {cliente}>
                    <div class="row">
                        <Boton
                            documento={cliente}
                            tipo="modificar"
                            coleccion="clientes"
                        />
                        <Boton
                            documento={cliente}
                            tipo="eliminar"
                            coleccion="clientes"
                        />
                    </div>
                </Cliente>
            </div>
        {/each}
    </div>
</div>
