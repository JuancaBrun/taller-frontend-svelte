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
                        id="marca"
                        bind:value={vehiculo.marca}
                        class="marca"
                    />
                </div>
                <div class="col-12 row">
                    <label class="col-form-label" for="modelo"
                        >Modelo:
                    </label><input
                        id="modelo"
                        bind:value={vehiculo.modelo}
                        class="modelo"
                    />
                </div>
                <div class="col-12 row">
                    <label class="col-form-label" for="version"
                        >Versión:
                    </label><input
                        id="version"
                        bind:value={vehiculo.version}
                        class="version"
                    />
                    <label class="col-form-label" for="color"
                        >Color:
                    </label><input
                        id="color"
                        bind:value={vehiculo.color}
                        class="color"
                    />
                </div>
                <div class="col-12 row">
                    <label class="col-form-label" for="anyo">Año: </label><input
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
    /*
    .card:hover {
        box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.4);
    }

    input {
        background-color: inherit;
        padding: 10px;
        font-size: 14px;
        color: black;
        border: 0;
        outline: none;
        margin-left: 5px;
        margin-bottom: 4px;
        max-width: 140px;
    } */

    /* input:focus {
        background-color: wheat;
    }

    input:required:invalid,
    input:focus:invalid {
        background-color: lightpink;
    } */
</style>
