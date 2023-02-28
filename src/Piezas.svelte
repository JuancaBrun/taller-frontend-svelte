<script>
    import { getContext, onMount } from "svelte";
    import { jsonData } from "./store";
    import Pieza from "./Pieza.svelte";
    import Buscador from "./Buscador.svelte";
    import Boton from "./Boton.svelte";

    const URL = getContext("URL");
    let busqueda = "";
    let pieza = {};

    onMount(async () => {
        const response = await fetch(URL.piezas);
        const data = await response.json();
        $jsonData = data;
    });

    $: regex = new RegExp(busqueda, "i");
    $: piezas = busqueda
        ? $jsonData.filter((item) => regex.test(item.nombre))
        : $jsonData;
</script>

<div class="d-flex justify-content-end">
    <Buscador bind:busqueda />
</div>
<h2 class="text-center">Insertar pieza:</h2>
<div class="card-group row mx-0">
    <div class="col-sm-6 col-md-4 col-lg-3 mx-auto">
        <Pieza {pieza}>
            <Boton documento={pieza} tipo="insertar" coleccion="piezas" />
        </Pieza>
    </div>
</div>
<h2 class="text-center mt-5">Colección de piezas:</h2>

<div class="piezas-container">
    <div class="card-group row mx-0">
        {#each piezas as pieza}
            <div class="col-sm-6 col-md-4 col-lg-3 mx-0">
                <Pieza {pieza}>
                    <div class="row">
                        <Boton
                            documento={pieza}
                            tipo="modificar"
                            coleccion="piezas"
                        />
                        <Boton
                            documento={pieza}
                            tipo="eliminar"
                            coleccion="piezas"
                        />
                    </div>
                </Pieza>
            </div>
        {/each}
    </div>
</div>
