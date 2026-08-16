# marlon
from flask import Flask, render_template

app = Flask(__name__)


@app.route("/")
def inicio():
    return render_template("index.html")


@app.route("/productos")
def productos():
    return render_template("productos.html")


@app.route("/clientes")
def clientes():
    return render_template("clientes.html")


@app.route("/proveedores")
def proveedores():
    return render_template("proveedores.html")


@app.route("/facturacion")
def facturacion():
    return render_template("facturacion.html")


if __name__ == "__main__":
    app.run(debug=True)
    <!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>{% block title %}Proyecto Integrador{% endblock %}</title>

    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css"
          rel="stylesheet">

    <link rel="stylesheet"
          href="{{ url_for('static', filename='css/style.css') }}">
</head>

<body>

    <nav class="navbar navbar-expand-lg navbar-dark bg-primary">
        <div class="container">
            <a class="navbar-brand" href="{{ url_for('inicio') }}">
                Mi Proyecto
            </a>

            <button class="navbar-toggler"
                    type="button"
                    data-bs-toggle="collapse"
                    data-bs-target="#menu">
                <span class="navbar-toggler-icon"></span>
            </button>

            <div class="collapse navbar-collapse" id="menu">
                <ul class="navbar-nav ms-auto">

                    <li class="nav-item">
                        <a class="nav-link" href="{{ url_for('inicio') }}">
                            Inicio
                        </a>
                    </li>

                    <li class="nav-item">
                        <a class="nav-link" href="{{ url_for('productos') }}">
                            Productos
                        </a>
                    </li>

                    <li class="nav-item">
                        <a class="nav-link" href="{{ url_for('clientes') }}">
                            Clientes
                        </a>
                    </li>

                    <li class="nav-item">
                        <a class="nav-link" href="{{ url_for('proveedores') }}">
                            Proveedores
                        </a>
                    </li>

                    <li class="nav-item">
                        <a class="nav-link" href="{{ url_for('facturacion') }}">
                            Facturación
                        </a>
                    </li>

                </ul>
            </div>
        </div>
    </nav>

    <main class="container py-4">

        {% block content %}
        {% endblock %}

    </main>

    <footer class="bg-dark text-white text-center py-3 mt-5">
        <p class="mb-0">
            Proyecto Integrador &copy; 2026
        </p>
    </footer>

    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js">
    </script>

    <script src="{{ url_for('static', filename='js/script.js') }}">
    </script>

</body>
</html>
{% extends "base.html" %}

{% block title %}Inicio{% endblock %}

{% block content %}

<div class="p-5 mb-4 bg-light rounded-3">
    <div class="container-fluid py-4">
        <h1 class="display-5 fw-bold">
            Bienvenidos a nuestro proyecto
        </h1>

        <p class="fs-5">
            Sistema web desarrollado como parte del Proyecto Integrador.
        </p>

        <a href="{{ url_for('productos') }}" class="btn btn-primary">
            Ver productos
        </a>
    </div>
</div>

<div class="row">

    <div class="col-md-4 mb-3">
        <div class="card h-100">
            <div class="card-body">
                <h5 class="card-title">Productos</h5>
                <p class="card-text">
                    Consulta los productos disponibles.
                </p>
                <a href="{{ url_for('productos') }}"
                   class="btn btn-primary">
                    Ver productos
                </a>
            </div>
        </div>
    </div>

    <div class="col-md-4 mb-3">
        <div class="card h-100">
            <div class="card-body">
                <h5 class="card-title">Clientes</h5>
                <p class="card-text">
                    Información de los clientes registrados.
                </p>
                <a href="{{ url_for('clientes') }}"
                   class="btn btn-primary">
                    Ver clientes
                </a>
            </div>
        </div>
    </div>

    <div class="col-md-4 mb-3">
        <div class="card h-100">
            <div class="card-body">
                <h5 class="card-title">Facturación</h5>
                <p class="card-text">
                    Consulta las facturas del sistema.
                </p>
                <a href="{{ url_for('facturacion') }}"
                   class="btn btn-primary">
                    Ver facturación
                </a>
            </div>
        </div>
    </div>

</div>

{% endblock %}
{% extends "base.html" %}

{% block title %}Productos{% endblock %}

{% block content %}

<h1 class="mb-4">Productos</h1>

<div class="row">

    <div class="col-md-4 mb-4">
        <div class="card h-100">
            <div class="card-body">
                <h5 class="card-title">Producto 1</h5>
                <p class="card-text">Producto de demostración.</p>
                <p><strong>Precio:</strong> $25.00</p>
                <button class="btn btn-success">
                    Ver producto
                </button>
            </div>
        </div>
    </div>

    <div class="col-md-4 mb-4">
        <div class="card h-100">
            <div class="card-body">
                <h5 class="card-title">Producto 2</h5>
                <p class="card-text">Producto de demostración.</p>
                <p><strong>Precio:</strong> $35.00</p>
                <button class="btn btn-success">
                    Ver producto
                </button>
            </div>
        </div>
    </div>

</div>

{% endblock %}
body {
    background-color: #f5f6f8;
}

.card {
    transition: transform 0.2s;
}

.card:hover {
    transform: translateY(-5px);
}

footer {
    margin-top: 50px;
}
console.log("Aplicación Flask cargada correctamente.");

document.addEventListener("DOMContentLoaded", function () {
    console.log("Documento cargado.");
});
