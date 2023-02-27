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
                        id="nombre"
                        bind:value={pieza.nombre}
                        class="nombre"
                    />
                </div>
                <div class="col-12 row">
                    <label class="col-form-label" for="precio"
                        >Precio:
                    </label><input
                        id="precio"
                        bind:value={pieza.precio}
                        class="precio"
                    />
                </div>
                <div class="col-12 row">
                    <label class="col-form-label" for="material"
                        >Material:
                    </label><input
                        id="material"
                        bind:value={pieza.material}
                        class="material"
                    />
                    <label class="col-form-label" for="color"
                        >Color:
                    </label><input
                        id="color"
                        bind:value={pieza.color}
                        class="color"
                    />
                </div>
                <div class="col-12 row">
                    <label class="col-form-label" for="peso"
                        >Peso (g):
                    </label><input
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
    /* .title {
        font-weight: bold;
    }*/
    .card {
        background-color: #fdebc9;
        box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
        border-radius: 5px;
        transition: 0.3s;
        padding: 10px;
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
