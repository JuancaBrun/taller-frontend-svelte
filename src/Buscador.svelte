<script>
    export let busqueda;
</script>

<form>
    <label for="buscador">Buscar: </label>
    <input id="buscador" bind:value={busqueda} type="search" />
</form>
