<script>
    export let pieza = {
        nombre: "",
        precio: 0,
        material: "",
        color: "",
        peso: 0,
    };
</script>

<div class="card">
    <div class="card-body">
        <div class="row py-3">
            <form>
                <div class="col-12 row">
                    <label class="col-form-label" for="nombre"
                        >Nombre:
                    </label><input
                        required
                        id="nombre"
                        bind:value={pieza.nombre}
                        class="nombre"
                    />
                </div>
                <div class="col-12 row">
                    <label class="col-form-label" for="precio"
                        >Precio:
                    </label><input
                        type="number"
                        required
                        id="precio"
                        bind:value={pieza.precio}
                        class="precio"
                    />
                </div>
                <div class="col-12 row">
                    <label class="col-form-label" for="material"
                        >Material:
                    </label><input
                        required
                        id="material"
                        bind:value={pieza.material}
                        class="material"
                    />
                    <label class="col-form-label" for="color"
                        >Color:
                    </label><input
                        required
                        id="color"
                        bind:value={pieza.color}
                        class="color"
                    />
                </div>
                <div class="col-12 row">
                    <label class="col-form-label" for="peso"
                        >Peso (g):
                    </label><input
                        type="number"
                        required
                        id="peso"
                        bind:value={pieza.peso}
                        class="peso"
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
