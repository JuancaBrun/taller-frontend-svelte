<h1 class="py-5">Inicio</h1>

<div class="categorias-container py-5">
    <div class="card-group col-lg-8 row mx-auto">
        <div class="card col-12 col-lg-4 mx-0 mx-lg-3">
            <div class="card-body">
                <h2>Piezas</h2>
                <p>Gestión de piezas del taller.</p>
                <ul class="list-group">
                    <li class="list-group-item">Lectura de piezas</li>
                    <li class="list-group-item">Inserción de piezas nuevas</li>
                    <li class="list-group-item">Modificación y eliminación</li>
                </ul>
            </div>
        </div>
        <div class="card col-12 col-lg-4 mx-0 mx-lg-3">
            <div class="card-body">
                <h2>Vehículos</h2>
                <p>Gestión de vehículos del taller.</p>
                <ul class="list-group">
                    <li class="list-group-item">Lectura de vehículos</li>
                    <li class="list-group-item">
                        Inserción de vehículos nuevos
                    </li>
                    <li class="list-group-item">Modificación y eliminación</li>
                </ul>
            </div>
        </div>
        <div class="card col-12 col-lg-4 mx-0 mx-lg-3">
            <div class="card-body">
                <h2>Clientes</h2>
                <p>Gestión de clientes del taller.</p>
                <ul class="list-group">
                    <li class="list-group-item">Lectura de clientes</li>
                    <li class="list-group-item">
                        Inserción de clientes nuevos
                    </li>
                    <li class="list-group-item">Modificación y eliminación</li>
                </ul>
            </div>
        </div>
    </div>
</div>

<style>
    .card {
        background-color: transparent;
        border: 2px solid white;
        border-radius: 10px;
        margin: 10px;
        transition: all 0.2s ease-in-out;
    }

    .card:hover {
        transform: scale(1.05);
    }

    .list-group-item {
        background-color: transparent;
        color: white;
    }

    .list-group-item::before {
        content: "✔️ ";
    }
</style>
