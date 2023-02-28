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
                        required
                        id="nombre"
                        bind:value={cliente.nombre}
                        class="nombre"
                    />
                </div>
                <div class="col-12 row">
                    <label class="col-form-label" for="apellidos"
                        >Apellidos:
                    </label><input
                        required
                        id="apellidos"
                        bind:value={cliente.apellidos}
                        class="apellidos"
                    />
                </div>
                <div class="col-12 row">
                    <label class="col-form-label" for="direccion"
                        >Dirección:
                    </label><input
                        required
                        id="direccion"
                        bind:value={cliente.direccion}
                        class="direccion"
                    />
                    <label class="col-form-label" for="categoria"
                        >Categoría:
                    </label><input
                        required
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

    input:focus {
        background-color: wheat;
    }

    input:focus:invalid {
        background-color: lightpink;
    }
</style>
