<script>
    export let busqueda;
</script>

<form>
    <input
        id="buscador"
        bind:value={busqueda}
        type="search"
        placeholder="Buscar"
    />
</form>

<style>
    #buscador {
        background-color: transparent;
        border: 2px solid white;
        border-radius: 10px;
        color: white;
        margin: 20px 15px 5px;
    }
</style>
