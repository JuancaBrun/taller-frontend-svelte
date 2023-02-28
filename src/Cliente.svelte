<script>
    export let cliente = {
        nombre: "",
        apellidos: "",
        direccion: "",
        categoria: "",
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
                        bind:value={cliente.nombre}
                        class="nombre"
                    />
                </div>
                <div class="col-12 row">
                    <label class="col-form-label" for="apellidos"
                        >Apellidos:
                    </label><input
                        id="apellidos"
                        bind:value={cliente.apellidos}
                        class="apellidos"
                    />
                </div>
                <div class="col-12 row">
                    <label class="col-form-label" for="direccion"
                        >Dirección:
                    </label><input
                        id="direccion"
                        bind:value={cliente.direccion}
                        class="direccion"
                    />
                    <label class="col-form-label" for="categoria"
                        >Categoría:
                    </label><input
                        id="categoria"
                        bind:value={cliente.categoria}
                        class="categoria"
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
