<script>
    import { getContext, onMount } from "svelte";
    import { jsonData } from "./store";
    import Vehiculo from "./Vehiculo.svelte";
    import Buscador from "./Buscador.svelte";
    import Boton from "./Boton.svelte";

    const URL = getContext("URL");
    let busqueda = "";
    let vehiculo = {};

    onMount(async () => {
        const response = await fetch(URL.vehiculos);
        const data = await response.json();
        $jsonData = data;
    });

    $: vehiculos = $jsonData.filter((item) =>
        RegExp(busqueda, "i").test(item.marca)
    );
</script>

<div class="d-flex justify-content-end">
    <Buscador bind:busqueda />
</div>
<h2 class="text-center">Insertar vehículo:</h2>
<div class="card-group row mx-0">
    <div class="col-sm-6 col-md-4 col-lg-3 mx-auto">
        <Vehiculo {vehiculo}>
            <Boton documento={vehiculo} tipo="insertar" coleccion="vehiculos" />
        </Vehiculo>
    </div>
</div>
<h2 class="text-center mt-5">Colección de vehículos:</h2>

<div class="vehiculos-container">
    <div class="card-group row mx-0">
        {#each vehiculos as vehiculo}
            <div class="col-sm-6 col-md-4 col-lg-3 mx-0">
                <Vehiculo {vehiculo}>
                    <div class="row">
                        <Boton
                            documento={vehiculo}
                            tipo="modificar"
                            coleccion="vehiculos"
                        />
                        <Boton
                            documento={vehiculo}
                            tipo="eliminar"
                            coleccion="vehiculos"
                        />
                    </div>
                </Vehiculo>
            </div>
        {/each}
    </div>
</div>
