<script>
    export let vehiculo = {
        marca: "",
        modelo: "",
        version: "",
        color: "",
        anyo: 0,
    };
</script>

<div class="card">
    <div class="card-body">
        <div class="row py-3">
            <form>
                <div class="col-12 row">
                    <label class="col-form-label" for="marca"
                        >Marca:
                    </label><input
                        required
                        id="marca"
                        bind:value={vehiculo.marca}
                        class="marca"
                    />
                </div>
                <div class="col-12 row">
                    <label class="col-form-label" for="modelo"
                        >Modelo:
                    </label><input
                        required
                        id="modelo"
                        bind:value={vehiculo.modelo}
                        class="modelo"
                    />
                </div>
                <div class="col-12 row">
                    <label class="col-form-label" for="version"
                        >Versión:
                    </label><input
                        required
                        id="version"
                        bind:value={vehiculo.version}
                        class="version"
                    />
                    <label class="col-form-label" for="color"
                        >Color:
                    </label><input
                        required
                        id="color"
                        bind:value={vehiculo.color}
                        class="color"
                    />
                </div>
                <div class="col-12 row">
                    <label class="col-form-label" for="anyo">Año: </label><input
                        required
                        type="number"
                        id="anyo"
                        bind:value={vehiculo.anyo}
                        class="anyo"
                    />
                </div>
            </form>
        </div>
        <slot />
    </div>
</div>

<style>
    .card {
        background-color: transparent;
        border: 2px solid white;
        border-radius: 10px;
        margin: 10px;
    }

    input:focus {
        background-color: wheat;
    }

    input:focus:invalid {
        background-color: lightpink;
    }
</style>
