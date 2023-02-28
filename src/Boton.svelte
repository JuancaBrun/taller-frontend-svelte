<script>
    import { getContext } from "svelte";
    import { onMount } from "svelte";
    import { jsonData } from "./store";

    export let tipo = "insertar";
    export let coleccion = "piezas";
    export let documento = {};

    let handler = () => {};
    let clase = "";
    let url = "";

    const URL = getContext("URL");

    onMount(() => {
        switch (tipo) {
            case "insertar":
                handler = insertar;
                break;
            case "modificar":
                handler = modificar;
                break;
            case "eliminar":
                handler = eliminar;
                break;
            default:
        }

        switch (tipo) {
            case "insertar":
                clase = "btn btn-insertar btn-success col-6";
                break;
            case "modificar":
                clase = "btn btn-modificar btn-warning col-6";
                break;
            case "eliminar":
                clase = "btn btn-eliminar btn-danger col-6";
                break;
            default:
        }

        switch (coleccion) {
            case "piezas":
                url = URL.piezas;
                break;
            case "vehiculos":
                url = URL.vehiculos;
                break;
            case "clientes":
                url = URL.clientes;
                break;
            default:
                break;
        }
    });

    function insertar() {
        if (validar(documento)) {
            const opciones = {
                method: "POST",
                headers: {
                    "Content-Type": "application/json",
                },
                body: JSON.stringify(documento),
            };
            fetch(url, opciones)
                .then((res) => res.json())
                .then((data) => {
                    $jsonData = [...$jsonData, data];
                    ok();
                })
                .catch((err) => ko());
        } else {
            ko();
        }
    }

    function modificar() {
        const opciones = {
            method: "PUT",
            headers: {
                "Content-Type": "application/json",
            },
            body: JSON.stringify(documento),
        };
        fetch(url + "/" + documento._id, opciones)
            .then((res) => res.json())
            .then((data) => ok())
            .catch((err) => ko());
    }

    function eliminar() {
        const opciones = {
            method: "DELETE",
            headers: {
                "Content-Type": "application/json",
            },
            body: JSON.stringify(documento),
        };
        fetch(url + "/" + documento._id, opciones)
            .then((res) => res.json())
            .then((data) => {
                $jsonData = $jsonData.filter((x) => x._id !== data._id);
                ok();
            })
            .catch((err) => ko());
    }

    let validar = (documento) => {
        let isValid = false;
        if (
            Object.keys(documento).length > 1 &&
            Object.values(documento).every((x) => x !== undefined && x != "")
        ) {
            isValid = true;
        }
        return isValid;
    };

    let ok = () => {
        OK.style.display = "block";
        setTimeout(() => (OK.style.display = "none"), 1500);
    };

    let ko = () => {
        KO.style.display = "block";
        setTimeout(() => (KO.style.display = "none"), 1500);
    };
</script>

<button class={clase} on:click={handler} />

<style>
    .btn {
        cursor: pointer;
        border-radius: 3px;
        font-size: 15px;
        transition: all 0.3s ease-in-out;
    }
    .btn:hover {
        box-shadow: 0 2px 6px 0 rgba(0, 0, 0, 0.2),
            0 3px 10px 0 rgba(0, 0, 0, 0.19);
    }

    .btn-insertar::before {
        content: "✏️";
    }

    .btn-insertar::after {
        content: " Insertar";
    }

    .btn-modificar::before {
        content: "💱";
    }

    .btn-modificar::after {
        content: " Modificar";
    }

    .btn-eliminar::before {
        content: "❌";
    }

    .btn-eliminar::after {
        content: " Eliminar";
    }
</style>
