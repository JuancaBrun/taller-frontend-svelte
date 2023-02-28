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

<h1>Piezas</h1>
<Buscador bind:busqueda />
<p>Insertar pieza:</p>
<Pieza {pieza}>
    <Boton documento={pieza} tipo="insertar" coleccion="piezas" />
</Pieza>
<p>Listado todas</p>

<div class="piezas-container">
    <div class="card-group row">
        {#each piezas as pieza}
            <div class="col-sm-6 col-md-4 col-lg-3">
                <Pieza {pieza}>
                    <div style="text-align: right">
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
