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


from flask import Flask, render_template_string

app = Flask(__name__)

# ==========================================================
# DATOS DEL PROYECTO
# ==========================================================

nombre_empresa = "Ferretería El Constructor"

informacion = {
    "direccion": "Av. Principal y Calle 10",
    "telefono": "0991234567",
    "email": "info@elconstructor.com"
}

productos = [
    {
        "id": 1,
        "nombre": "Martillo",
        "categoria": "Herramientas",
        "precio": 8.50,
        "stock": 10
    },
    {
        "id": 2,
        "nombre": "Taladro",
        "categoria": "Herramientas eléctricas",
        "precio": 75.00,
        "stock": 5
    },
    {
        "id": 3,
        "nombre": "Destornillador",
        "categoria": "Herramientas",
        "precio": 4.50,
        "stock": 0
    },
    {
        "id": 4,
        "nombre": "Cemento",
        "categoria": "Construcción",
        "precio": 7.25,
        "stock": 20
    },
    {
        "id": 5,
        "nombre": "Pintura",
        "categoria": "Pinturas",
        "precio": 18.00,
        "stock": 8
    },
    {
        "id": 6,
        "nombre": "Brocha",
        "categoria": "Pinturas",
        "precio": 3.50,
        "stock": 0
    }
]

clientes = [
    {
        "id": 1,
        "nombre": "Juan Pérez",
        "telefono": "0991234567",
        "ciudad": "Guayaquil"
    },
    {
        "id": 2,
        "nombre": "María López",
        "telefono": "0987654321",
        "ciudad": "Machala"
    },
    {
        "id": 3,
        "nombre": "Carlos Sánchez",
        "telefono": "0974561238",
        "ciudad": "Huaquillas"
    },
    {
        "id": 4,
        "nombre": "Ana Torres",
        "telefono": "0963214567",
        "ciudad": "Guayaquil"
    }
]

proveedores = [
    {
        "id": 1,
        "empresa": "FerreMateriales S.A.",
        "contacto": "Pedro Gómez",
        "telefono": "0991112233",
        "estado": "Activo"
    },
    {
        "id": 2,
        "empresa": "ConstruMarket",
        "contacto": "Laura Ruiz",
        "telefono": "0982223344",
        "estado": "Activo"
    },
    {
        "id": 3,
        "empresa": "Herramientas del Sur",
        "contacto": "Miguel Castro",
        "telefono": "0973334455",
        "estado": "Inactivo"
    }
]

facturas = [
    {
        "numero": "FAC-001",
        "cliente": "Juan Pérez",
        "fecha": "20/08/2026",
        "total": 125.50,
        "estado": "Pagada"
    },
    {
        "numero": "FAC-002",
        "cliente": "María López",
        "fecha": "21/08/2026",
        "total": 85.75,
        "estado": "Pendiente"
    },
    {
        "numero": "FAC-003",
        "cliente": "Carlos Sánchez",
        "fecha": "22/08/2026",
        "total": 210.00,
        "estado": "Pagada"
    },
    {
        "numero": "FAC-004",
        "cliente": "Ana Torres",
        "fecha": "23/08/2026",
        "total": 65.25,
        "estado": "Pendiente"
    }
]


# ==========================================================
# PLANTILLA HTML COMPLETA
# ==========================================================

HTML = """
<!DOCTYPE html>
<html lang="es">

<head>

    <meta charset="UTF-8">

    <meta name="viewport"
          content="width=device-width, initial-scale=1.0">

    <title>{{ titulo }} - Ferretería El Constructor</title>

    <link
        href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css"
        rel="stylesheet">

    <style>

        body {
            background-color: #f4f6f9;
            min-height: 100vh;
        }

        .navbar-brand {
            font-weight: bold;
        }

        .card {
            border: none;
            border-radius: 12px;
        }

        .card:hover {
            transform: translateY(-3px);
            transition: 0.2s;
        }

        footer {
            margin-top: 60px;
        }

    </style>

</head>


<body>


<!-- ======================================================
     NAVBAR
======================================================= -->

<nav class="navbar navbar-expand-lg navbar-dark bg-dark">

    <div class="container">

        <a class="navbar-brand"
           href="/">
            El Constructor
        </a>

        <button
            class="navbar-toggler"
            data-bs-toggle="collapse"
            data-bs-target="#menu">

            <span class="navbar-toggler-icon"></span>

        </button>

        <div
            class="collapse navbar-collapse"
            id="menu">

            <ul class="navbar-nav ms-auto">

                <li class="nav-item">

                    <a class="nav-link"
                       href="/">
                        Inicio
                    </a>

                </li>

                <li class="nav-item">

                    <a class="nav-link"
                       href="/productos">
                        Productos
                    </a>

                </li>

                <li class="nav-item">

                    <a class="nav-link"
                       href="/clientes">
                        Clientes
                    </a>

                </li>

                <li class="nav-item">

                    <a class="nav-link"
                       href="/proveedores">
                        Proveedores
                    </a>

                </li>

                <li class="nav-item">

                    <a class="nav-link"
                       href="/facturacion">
                        Facturación
                    </a>

                </li>

            </ul>

        </div>

    </div>

</nav>


<!-- ======================================================
     CONTENIDO
======================================================= -->

<div class="container py-5">


{% if pagina == "inicio" %}


    <!-- ================= INICIO ================= -->

    <div class="text-center mb-5">

        <h1 class="display-5 fw-bold">

            {{ nombre_empresa }}

        </h1>

        <p class="lead">

            Sistema de gestión comercial

        </p>

        <p>

            Bienvenido a
            <strong>{{ nombre_empresa|upper }}</strong>

        </p>

    </div>


    <div class="row g-4">


        <div class="col-md-3">

            <div class="card shadow text-center">

                <div class="card-body">

                    <h5>Productos</h5>

                    <h2>
                        {{ productos|length }}
                    </h2>

                </div>

            </div>

        </div>


        <div class="col-md-3">

            <div class="card shadow text-center">

                <div class="card-body">

                    <h5>Clientes</h5>

                    <h2>
                        {{ clientes|length }}
                    </h2>

                </div>

            </div>

        </div>


        <div class="col-md-3">

            <div class="card shadow text-center">

                <div class="card-body">

                    <h5>Proveedores</h5>

                    <h2>
                        {{ proveedores|length }}
                    </h2>

                </div>

            </div>

        </div>


        <div class="col-md-3">

            <div class="card shadow text-center">

                <div class="card-body">

                    <h5>Facturas</h5>

                    <h2>
                        {{ facturas|length }}
                    </h2>

                </div>

            </div>

        </div>

    </div>


    <div class="card shadow mt-5">

        <div class="card-body">

            <h3>
                Información de contacto
            </h3>

            <p>
                <strong>Dirección:</strong>
                {{ informacion.direccion }}
            </p>

            <p>
                <strong>Teléfono:</strong>
                {{ informacion.telefono }}
            </p>

            <p>
                <strong>Correo:</strong>
                {{ informacion.email }}
            </p>

        </div>

    </div>


{% elif pagina == "productos" %}


    <!-- ================= PRODUCTOS ================= -->

    <h1 class="mb-4">
        Productos
    </h1>


    <div class="row g-4">


        {% for producto in productos %}


        <div class="col-md-4">


            <div class="card shadow h-100">

                <div class="card-body">


                    <span class="badge bg-secondary">

                        {{ producto.categoria }}

                    </span>


                    <h4 class="mt-3">

                        {{ producto.nombre|upper }}

                    </h4>


                    <p>

                        <strong>Precio:</strong>

                        ${{ "%.2f"|format(producto.precio) }}

                    </p>


                    <p>

                        <strong>Stock:</strong>

                        {{ producto.stock }}

                    </p>


                    {% if producto.stock > 0 %}

                        <span class="badge bg-success">

                            Disponible

                        </span>

                    {% else %}

                        <span class="badge bg-danger">

                            Agotado

                        </span>

                    {% endif %}


                </div>

            </div>


        </div>


        {% endfor %}


    </div>


{% elif pagina == "clientes" %}


    <!-- ================= CLIENTES ================= -->

    <h1 class="mb-4">
        Clientes
    </h1>


    <div class="table-responsive">


        <table class="table table-striped table-hover shadow-sm">


            <thead class="table-dark">

                <tr>

                    <th>ID</th>
                    <th>Nombre</th>
                    <th>Teléfono</th>
                    <th>Ciudad</th>

                </tr>

            </thead>


            <tbody>


                {% for cliente in clientes %}

                <tr>

                    <td>
                        {{ cliente.id }}
                    </td>

                    <td>
                        {{ cliente.nombre }}
                    </td>

                    <td>
                        {{ cliente.telefono }}
                    </td>

                    <td>
                        {{ cliente.ciudad }}
                    </td>

                </tr>

                {% endfor %}


            </tbody>

        </table>


    </div>


    {% if clientes %}

        <div class="alert alert-success">

            Se encontraron
            {{ clientes|length }}
            clientes registrados.

        </div>

    {% else %}

        <div class="alert alert-warning">

            No existen clientes registrados.

        </div>

    {% endif %}


{% elif pagina == "proveedores" %}


    <!-- ================= PROVEEDORES ================= -->

    <h1 class="mb-4">
        Proveedores
    </h1>


    <div class="row g-4">


        {% for proveedor in proveedores %}


        <div class="col-md-4">


            <div class="card shadow h-100">

                <div class="card-body">

                    <h5>

                        {{ proveedor.empresa }}

                    </h5>

                    <hr>

                    <p>

                        <strong>Contacto:</strong>

                        {{ proveedor.contacto }}

                    </p>

                    <p>

                        <strong>Teléfono:</strong>

                        {{ proveedor.telefono }}

                    </p>


                    {% if proveedor.estado == "Activo" %}

                        <span class="badge bg-success">

                            Proveedor activo

                        </span>

                    {% else %}

                        <span class="badge bg-danger">

                            Proveedor inactivo

                        </span>

                    {% endif %}


                </div>

            </div>


        </div>


        {% endfor %}


    </div>


{% elif pagina == "facturacion" %}


    <!-- ================= FACTURACIÓN ================= -->

    <h1 class="mb-4">
        Facturación
    </h1>


    <div class="table-responsive">


        <table class="table table-bordered table-hover shadow-sm">


            <thead class="table-dark">

                <tr>

                    <th>Número</th>
                    <th>Cliente</th>
                    <th>Fecha</th>
                    <th>Total</th>
                    <th>Estado</th>

                </tr>

            </thead>


            <tbody>


                {% for factura in facturas %}


                <tr>

                    <td>

                        {{ factura.numero }}

                    </td>

                    <td>

                        {{ factura.cliente }}

                    </td>

                    <td>

                        {{ factura.fecha }}

                    </td>

                    <td>

                        ${{ "%.2f"|format(factura.total) }}

                    </td>

                    <td>


                        {% if factura.estado == "Pagada" %}

                            <span class="badge bg-success">

                                Pagada

                            </span>

                        {% else %}

                            <span class="badge bg-warning text-dark">

                                Pendiente

                            </span>

                        {% endif %}


                    </td>

                </tr>


                {% endfor %}


            </tbody>


        </table>


    </div>


{% endif %}


</div>


<!-- ======================================================
     FOOTER
======================================================= -->

<footer class="bg-dark text-white text-center py-4">

    <p class="mb-1">

        © 2026 Ferretería El Constructor

    </p>

    <small>

        Proyecto Integrador - Flask y Jinja2

    </small>

</footer>


<script
    src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js">
</script>


</body>

</html>
"""


# ==========================================================
# RUTAS
# ==========================================================

@app.route("/")
def index():

    return render_template_string(
        HTML,
        titulo="Inicio",
        pagina="inicio",
        nombre_empresa=nombre_empresa,
        informacion=informacion,
        productos=productos,
        clientes=clientes,
        proveedores=proveedores,
        facturas=facturas
    )


@app.route("/productos")
def ver_productos():

    return render_template_string(
        HTML,
        titulo="Productos",
        pagina="productos",
        productos=productos
    )


@app.route("/clientes")
def ver_clientes():

    return render_template_string(
        HTML,
        titulo="Clientes",
        pagina="clientes",
        clientes=clientes
    )


@app.route("/proveedores")
def ver_proveedores():

    return render_template_string(
        HTML,
        titulo="Proveedores",
        pagina="proveedores",
        proveedores=proveedores
    )


@app.route("/facturacion")
def ver_facturacion():

    return render_template_string(
        HTML,
        titulo="Facturación",
        pagina="facturacion",
        facturas=facturas
    )


# ==========================================================
# EJECUTAR APLICACIÓN
# ==========================================================

if __name__ == "__main__":
    app.run(debug=True)
