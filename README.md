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
# EJECUTAR APLICAC

# =========================
# ARCHIVO: app.py
# =========================

from flask import Flask, render_template, redirect, url_for, flash

from forms.producto_form import ProductoForm
from forms.cliente_form import ClienteForm
from forms.proveedor_form import ProveedorForm
from forms.facturacion_form import FacturacionForm

app = Flask(__name__)

# Clave necesaria para Flask-WTF y protección CSRF
app.config["SECRET_KEY"] = "clave-secreta-proyecto-integrador-2026"

# Datos temporales. No se utiliza base de datos en esta semana.
productos = []
clientes = []
proveedores = []
facturas = []


# =========================
# INICIO
# =========================

@app.route("/")
def index():
    return render_template(
        "index.html",
        productos=productos,
        clientes=clientes,
        proveedores=proveedores,
        facturas=facturas
    )


# =========================
# PRODUCTOS
# =========================

@app.route("/productos")
def productos_lista():
    return render_template(
        "productos.html",
        productos=productos
    )


@app.route("/productos/nuevo", methods=["GET", "POST"])
def nuevo_producto():

    form = ProductoForm()

    if form.validate_on_submit():

        producto = {
            "nombre": form.nombre.data,
            "descripcion": form.descripcion.data,
            "precio": form.precio.data,
            "stock": form.stock.data
        }

        productos.append(producto)

        flash(
            "Producto registrado correctamente.",
            "success"
        )

        return redirect(url_for("productos_lista"))

    return render_template(
        "formulario_producto.html",
        form=form
    )


# =========================
# CLIENTES
# =========================

@app.route("/clientes")
def clientes_lista():
    return render_template(
        "clientes.html",
        clientes=clientes
    )


@app.route("/clientes/nuevo", methods=["GET", "POST"])
def nuevo_cliente():

    form = ClienteForm()

    if form.validate_on_submit():

        cliente = {
            "nombre": form.nombre.data,
            "email": form.email.data,
            "telefono": form.telefono.data,
            "direccion": form.direccion.data
        }

        clientes.append(cliente)

        flash(
            "Cliente registrado correctamente.",
            "success"
        )

        return redirect(url_for("clientes_lista"))

    return render_template(
        "formulario_cliente.html",
        form=form
    )


# =========================
# PROVEEDORES
# =========================

@app.route("/proveedores")
def proveedores_lista():
    return render_template(
        "proveedores.html",
        proveedores=proveedores
    )


@app.route("/proveedores/nuevo", methods=["GET", "POST"])
def nuevo_proveedor():

    form = ProveedorForm()

    if form.validate_on_submit():

        proveedor = {
            "empresa": form.empresa.data,
            "contacto": form.contacto.data,
            "email": form.email.data,
            "telefono": form.telefono.data,
            "direccion": form.direccion.data
        }

        proveedores.append(proveedor)

        flash(
            "Proveedor registrado correctamente.",
            "success"
        )

        return redirect(url_for("proveedores_lista"))

    return render_template(
        "formulario_proveedor.html",
        form=form
    )


# =========================
# FACTURACIÓN
# =========================

@app.route("/facturacion")
def facturacion_lista():
    return render_template(
        "facturacion.html",
        facturas=facturas
    )


@app.route("/facturacion/nueva", methods=["GET", "POST"])
def nueva_factura():

    form = FacturacionForm()

    if form.validate_on_submit():

        total = form.cantidad.data * form.precio.data

        factura = {
            "cliente": form.cliente.data,
            "producto": form.producto.data,
            "cantidad": form.cantidad.data,
            "precio": form.precio.data,
            "total": total
        }

        facturas.append(factura)

        flash(
            "Factura registrada correctamente.",
            "success"
        )

        return redirect(url_for("facturacion_lista"))

    return render_template(
        "formulario_facturacion.html",
        form=form
    )


# =========================
# EJECUTAR APLICACIÓN
# =========================

if __name__ == "__main__":
    app.run(debug=True)


# ============================================================
# ARCHIVO: forms/__init__.py
# ============================================================

# Formularios del Proyecto Integrador


# ============================================================
# ARCHIVO: forms/producto_form.py
# ============================================================

from flask_wtf import FlaskForm
from wtforms import StringField, FloatField, IntegerField, SubmitField
from wtforms.validators import DataRequired, Length, NumberRange


class ProductoForm(FlaskForm):

    nombre = StringField(
        "Nombre del producto",
        validators=[
            DataRequired(
                message="El nombre del producto es obligatorio."
            ),
            Length(
                min=3,
                max=100,
                message="El nombre debe tener entre 3 y 100 caracteres."
            )
        ]
    )

    descripcion = StringField(
        "Descripción",
        validators=[
            DataRequired(
                message="La descripción es obligatoria."
            ),
            Length(
                min=5,
                max=200,
                message="La descripción debe tener entre 5 y 200 caracteres."
            )
        ]
    )

    precio = FloatField(
        "Precio",
        validators=[
            DataRequired(
                message="El precio es obligatorio."
            ),
            NumberRange(
                min=0.01,
                message="El precio debe ser mayor que 0."
            )
        ]
    )

    stock = IntegerField(
        "Stock",
        validators=[
            DataRequired(
                message="El stock es obligatorio."
            ),
            NumberRange(
                min=0,
                message="El stock no puede ser negativo."
            )
        ]
    )

    submit = SubmitField("Guardar producto")


# ============================================================
# ARCHIVO: forms/cliente_form.py
# ============================================================

from flask_wtf import FlaskForm
from wtforms import StringField, EmailField, TelField, SubmitField
from wtforms.validators import DataRequired, Length, Email


class ClienteForm(FlaskForm):

    nombre = StringField(
        "Nombre completo",
        validators=[
            DataRequired(
                message="El nombre es obligatorio."
            ),
            Length(
                min=3,
                max=100,
                message="El nombre debe tener entre 3 y 100 caracteres."
            )
        ]
    )

    email = EmailField(
        "Correo electrónico",
        validators=[
            DataRequired(
                message="El correo electrónico es obligatorio."
            ),
            Email(
                message="Ingrese un correo electrónico válido."
            )
        ]
    )

    telefono = TelField(
        "Teléfono",
        validators=[
            DataRequired(
                message="El teléfono es obligatorio."
            ),
            Length(
                min=7,
                max=15,
                message="El teléfono debe tener entre 7 y 15 caracteres."
            )
        ]
    )

    direccion = StringField(
        "Dirección",
        validators=[
            DataRequired(
                message="La dirección es obligatoria."
            ),
            Length(
                min=5,
                max=150,
                message="La dirección debe tener entre 5 y 150 caracteres."
            )
        ]
    )

    submit = SubmitField("Guardar cliente")


# ============================================================
# ARCHIVO: forms/proveedor_form.py
# ============================================================

from flask_wtf import FlaskForm
from wtforms import StringField, EmailField, TelField, SubmitField
from wtforms.validators import DataRequired, Length, Email


class ProveedorForm(FlaskForm):

    empresa = StringField(
        "Empresa",
        validators=[
            DataRequired(
                message="El nombre de la empresa es obligatorio."
            ),
            Length(
                min=3,
                max=100,
                message="La empresa debe tener entre 3 y 100 caracteres."
            )
        ]
    )

    contacto = StringField(
        "Persona de contacto",
        validators=[
            DataRequired(
                message="El contacto es obligatorio."
            ),
            Length(
                min=3,
                max=100,
                message="Ingrese un nombre válido."
            )
        ]
    )

    email = EmailField(
        "Correo electrónico",
        validators=[
            DataRequired(
                message="El correo electrónico es obligatorio."
            ),
            Email(
                message="Ingrese un correo electrónico válido."
            )
        ]
    )

    telefono = TelField(
        "Teléfono",
        validators=[
            DataRequired(
                message="El teléfono es obligatorio."
            ),
            Length(
                min=7,
                max=15,
                message="El teléfono debe tener entre 7 y 15 caracteres."
            )
        ]
    )

    direccion = StringField(
        "Dirección",
        validators=[
            DataRequired(
                message="La dirección es obligatoria."
            ),
            Length(
                min=5,
                max=150,
                message="La dirección debe tener entre 5 y 150 caracteres."
            )
        ]
    )

    submit = SubmitField("Guardar proveedor")


# ============================================================
# ARCHIVO: forms/facturacion_form.py
# ============================================================

from flask_wtf import FlaskForm
from wtforms import StringField, FloatField, IntegerField, SubmitField
from wtforms.validators import DataRequired, NumberRange


class FacturacionForm(FlaskForm):

    cliente = StringField(
        "Cliente",
        validators=[
            DataRequired(
                message="El cliente es obligatorio."
            )
        ]
    )

    producto = StringField(
        "Producto",
        validators=[
            DataRequired(
                message="El producto es obligatorio."
            )
        ]
    )

    cantidad = IntegerField(
        "Cantidad",
        validators=[
            DataRequired(
                message="La cantidad es obligatoria."
            ),
            NumberRange(
                min=1,
                message="La cantidad debe ser mayor o igual a 1."
            )
        ]
    )

    precio = FloatField(
        "Precio unitario",
        validators=[
            DataRequired(
                message="El precio es obligatorio."
            ),
            NumberRange(
                min=0.01,
                message="El precio debe ser mayor que 0."
            )
        ]
    )

    submit = SubmitField("Generar factura")


# ============================================================
# ARCHIVO: templates/base.html
# ============================================================

<!DOCTYPE html>
<html lang="es">

<head>

    <meta charset="UTF-8">

    <meta name="viewport"
          content="width=device-width, initial-scale=1.0">

    <title>Proyecto Integrador</title>

    <link
        href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css"
        rel="stylesheet">

    <link
        rel="stylesheet"
        href="{{ url_for('static', filename='css/style.css') }}">

</head>

<body>

    {% include "components/navbar.html" %}

    {% with messages = get_flashed_messages(with_categories=true) %}

        {% if messages %}

            <div class="container mt-3">

                {% for category, message in messages %}

                    <div class="alert alert-{{ category }}">
                        {{ message }}
                    </div>

                {% endfor %}

            </div>

        {% endif %}

    {% endwith %}

    <main>
        {% block content %}
        {% endblock %}
    </main>

    {% include "components/footer.html" %}

    <script
        src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js">
    </script>

</body>

</html>


# ============================================================
# ARCHIVO: templates/components/navbar.html
# ============================================================

<nav class="navbar navbar-expand-lg navbar-dark bg-dark">

    <div class="container">

        <a class="navbar-brand"
           href="{{ url_for('index') }}">
            Proyecto Integrador
        </a>

        <button
            class="navbar-toggler"
            type="button"
            data-bs-toggle="collapse"
            data-bs-target="#menu">

            <span class="navbar-toggler-icon"></span>

        </button>

        <div class="collapse navbar-collapse" id="menu">

            <ul class="navbar-nav ms-auto">

                <li class="nav-item">
                    <a class="nav-link"
                       href="{{ url_for('index') }}">
                        Inicio
                    </a>
                </li>

                <li class="nav-item">
                    <a class="nav-link"
                       href="{{ url_for('productos_lista') }}">
                        Productos
                    </a>
                </li>

                <li class="nav-item">
                    <a class="nav-link"
                       href="{{ url_for('clientes_lista') }}">
                        Clientes
                    </a>
                </li>

                <li class="nav-item">
                    <a class="nav-link"
                       href="{{ url_for('proveedores_lista') }}">
                        Proveedores
                    </a>
                </li>

                <li class="nav-item">
                    <a class="nav-link"
                       href="{{ url_for('facturacion_lista') }}">
                        Facturación
                    </a>
                </li>

            </ul>

        </div>

    </div>

</nav>


# ============================================================
# ARCHIVO: templates/components/footer.html
# ============================================================

<footer class="bg-dark text-white text-center p-3 mt-5">

    <p class="mb-0">
        Proyecto Integrador - Desarrollo de Aplicaciones Web
    </p>

    <p class="mb-0">
        Avance 11/16 - Flask-WTF y WTForms
    </p>

</footer>


# ============================================================
# ARCHIVO: templates/index.html
# ============================================================

{% extends "base.html" %}

{% block content %}

<div class="container mt-5">

    <div class="text-center">

        <h1>Proyecto Integrador</h1>

        <p class="lead">
            Sistema de gestión desarrollado con Flask,
            Jinja2, Flask-WTF y WTForms.
        </p>

    </div>

    <div class="row mt-5">

        <div class="col-md-3">
            <div class="card text-center shadow">
                <div class="card-body">

                    <h5>Productos</h5>

                    <h2>{{ productos|length }}</h2>

                    <a
                        href="{{ url_for('productos_lista') }}"
                        class="btn btn-primary">
                        Ver productos
                    </a>

                </div>
            </div>
        </div>


        <div class="col-md-3">

            <div class="card text-center shadow">

                <div class="card-body">

                    <h5>Clientes</h5>

                    <h2>{{ clientes|length }}</h2>

                    <a
                        href="{{ url_for('clientes_lista') }}"
                        class="btn btn-primary">
                        Ver clientes
                    </a>

                </div>

            </div>

        </div>


        <div class="col-md-3">

            <div class="card text-center shadow">

                <div class="card-body">

                    <h5>Proveedores</h5>

                    <h2>{{ proveedores|length }}</h2>

                    <a
                        href="{{ url_for('proveedores_lista') }}"
                        class="btn btn-primary">
                        Ver proveedores
                    </a>

                </div>

            </div>

        </div>


        <div class="col-md-3">

            <div class="card text-center shadow">

                <div class="card-body">

                    <h5>Facturas</h5>

                    <h2>{{ facturas|length }}</h2>

                    <a
                        href="{{ url_for('facturacion_lista') }}"
                        class="btn btn-primary">
                        Ver facturas
                    </a>

                </div>

            </div>

        </div>

    </div>

</div>

{% endblock %}


# ============================================================
# ARCHIVO: templates/formulario_producto.html
# ============================================================

{% extends "base.html" %}

{% block content %}

<div class="container mt-5">

    <div class="card shadow">

        <div class="card-header bg-primary text-white">

            <h2 class="mb-0">
                Registrar producto
            </h2>

        </div>

        <div class="card-body">

            <form method="POST">

                {{ form.hidden_tag() }}

                <div class="mb-3">

                    {{ form.nombre.label(
                        class="form-label"
                    ) }}

                    {{ form.nombre(
                        class="form-control"
                    ) }}

                    {% for error in form.nombre.errors %}

                        <div class="text-danger">
                            {{ error }}
                        </div>

                    {% endfor %}

                </div>


                <div class="mb-3">

                    {{ form.descripcion.label(
                        class="form-label"
                    ) }}

                    {{ form.descripcion(
                        class="form-control"
                    ) }}

                    {% for error in form.descripcion.errors %}

                        <div class="text-danger">
                            {{ error }}
                        </div>

                    {% endfor %}

                </div>


                <div class="mb-3">

                    {{ form.precio.label(
                        class="form-label"
                    ) }}

                    {{ form.precio(
                        class="form-control"
                    ) }}

                    {% for error in form.precio.errors %}

                        <div class="text-danger">
                            {{ error }}
                        </div>

                    {% endfor %}

                </div>


                <div class="mb-3">

                    {{ form.stock.label(
                        class="form-label"
                    ) }}

                    {{ form.stock(
                        class="form-control"
                    ) }}

                    {% for error in form.stock.errors %}

                        <div class="text-danger">
                            {{ error }}
                        </div>

                    {% endfor %}

                </div>


                {{ form.submit(
                    class="btn btn-primary"
                ) }}

                <a
                    href="{{ url_for('productos_lista') }}"
                    class="btn btn-secondary">
                    Cancelar
                </a>

            </form>

        </div>

    </div>

</div>

{% endblock %}


# ============================================================
# ARCHIVO: templates/productos.html
# ============================================================

{% extends "base.html" %}

{% block content %}

<div class="container mt-5">

    <div class="d-flex justify-content-between">

        <h1>Productos</h1>

        <a
            href="{{ url_for('nuevo_producto') }}"
            class="btn btn-primary">
            Nuevo producto
        </a>

    </div>

    <hr>

    {% if productos %}

    <div class="table-responsive">

        <table class="table table-striped table-bordered">

            <thead class="table-dark">

                <tr>
                    <th>Nombre</th>
                    <th>Descripción</th>
                    <th>Precio</th>
                    <th>Stock</th>
                </tr>

            </thead>

            <tbody>

                {% for producto in productos %}

                <tr>

                    <td>{{ producto.nombre }}</td>

                    <td>{{ producto.descripcion }}</td>

                    <td>
                        ${{ "%.2f"|format(producto.precio) }}
                    </td>

                    <td>{{ producto.stock }}</td>

                </tr>

                {% endfor %}

            </tbody>

        </table>

    </div>

    {% else %}

    <div class="alert alert-info">
        No existen productos registrados.
    </div>

    {% endif %}

</div>

{% endblock %}


# ============================================================
# ARCHIVO: templates/formulario_cliente.html
# ============================================================

{% extends "base.html" %}

{% block content %}

<div class="container mt-5">

    <div class="card shadow">

        <div class="card-header bg-primary text-white">

            <h2>Registrar cliente</h2>

        </div>

        <div class="card-body">

            <form method="POST">

                {{ form.hidden_tag() }}

                <div class="mb-3">

                    {{ form.nombre.label(
                        class="form-label"
                    ) }}

                    {{ form.nombre(
                        class="form-control"
                    ) }}

                    {% for error in form.nombre.errors %}

                    <div class="text-danger">
                        {{ error }}
                    </div>

                    {% endfor %}

                </div>


                <div class="mb-3">

                    {{ form.email.label(
                        class="form-label"
                    ) }}

                    {{ form.email(
                        class="form-control"
                    ) }}

                    {% for error in form.email.errors %}

                    <div class="text-danger">
                        {{ error }}
                    </div>

                    {% endfor %}

                </div>


                <div class="mb-3">

                    {{ form.telefono.label(
                        class="form-label"
                    ) }}

                    {{ form.telefono(
                        class="form-control"
                    ) }}

                    {% for error in form.telefono.errors %}

                    <div class="text-danger">
                        {{ error }}
                    </div>

                    {% endfor %}

                </div>


                <div class="mb-3">

                    {{ form.direccion.label(
                        class="form-label"
                    ) }}

                    {{ form.direccion(
                        class="form-control"
                    ) }}

                    {% for error in form.direccion.errors %}

                    <div class="text-danger">
                        {{ error }}
                    </div>

                    {% endfor %}

                </div>


                {{ form.submit(
                    class="btn btn-primary"
                ) }}

                <a
                    href="{{ url_for('clientes_lista') }}"
                    class="btn btn-secondary">
                    Cancelar
                </a>

            </form>

        </div>

    </div>

</div>

{% endblock %}


# ============================================================
# ARCHIVO: templates/clientes.html
# ============================================================

{% extends "base.html" %}

{% block content %}

<div class="container mt-5">

    <div class="d-flex justify-content-between">

        <h1>Clientes</h1>

        <a
            href="{{ url_for('nuevo_cliente') }}"
            class="btn btn-primary">
            Nuevo cliente
        </a>

    </div>

    <hr>

    {% if clientes %}

    <table class="table table-striped table-bordered">

        <thead class="table-dark">

            <tr>
                <th>Nombre</th>
                <th>Email</th>
                <th>Teléfono</th>
                <th>Dirección</th>
            </tr>

        </thead>

        <tbody>

            {% for cliente in clientes %}

            <tr>

                <td>{{ cliente.nombre }}</td>
                <td>{{ cliente.email }}</td>
                <td>{{ cliente.telefono }}</td>
                <td>{{ cliente.direccion }}</td>

            </tr>

            {% endfor %}

        </tbody>

    </table>

    {% else %}

    <div class="alert alert-info">
        No existen clientes registrados.
    </div>

    {% endif %}

</div>

{% endblock %}


# ============================================================
# ARCHIVO: templates/formulario_proveedor.html
# ============================================================

{% extends "base.html" %}

{% block content %}

<div class="container mt-5">

    <div class="card shadow">

        <div class="card-header bg-primary text-white">

            <h2>Registrar proveedor</h2>

        </div>

        <div class="card-body">

            <form method="POST">

                {{ form.hidden_tag() }}

                <div class="mb-3">

                    {{ form.empresa.label(
                        class="form-label"
                    ) }}

                    {{ form.empresa(
                        class="form-control"
                    ) }}

                    {% for error in form.empresa.errors %}

                    <div class="text-danger">
                        {{ error }}
                    </div>

                    {% endfor %}

                </div>


                <div class="mb-3">

                    {{ form.contacto.label(
                        class="form-label"
                    ) }}

                    {{ form.contacto(
                        class="form-control"
                    ) }}

                    {% for error in form.contacto.errors %}

                    <div class="text-danger">
                        {{ error }}
                    </div>

                    {% endfor %}

                </div>


                <div class="mb-3">

                    {{ form.email.label(
                        class="form-label"
                    ) }}

                    {{ form.email(
                        class="form-control"
                    ) }}

                    {% for error in form.email.errors %}

                    <div class="text-danger">
                        {{ error }}
                    </div>

                    {% endfor %}

                </div>


                <div class="mb-3">

                    {{ form.telefono.label(
                        class="form-label"
                    ) }}

                    {{ form.telefono(
                        class="form-control"
                    ) }}

                    {% for error in form.telefono.errors %}

                    <div class="text-danger">
                        {{ error }}
                    </div>

                    {% endfor %}

                </div>


                <div class="mb-3">

                    {{ form.direccion.label(
                        class="form-label"
                    ) }}

                    {{ form.direccion(
                        class="form-control"
                    ) }}

                    {% for error in form.direccion.errors %}

                    <div class="text-danger">
                        {{ error }}
                    </div>

                    {% endfor %}

                </div>


                {{ form.submit(
                    class="btn btn-primary"
                ) }}

                <a
                    href="{{ url_for('proveedores_lista') }}"
                    class="btn btn-secondary">
                    Cancelar
                </a>

            </form>

        </div>

    </div>

</div>

{% endblock %}


# ============================================================
# ARCHIVO: templates/proveedores.html
# ============================================================

{% extends "base.html" %}

{% block content %}

<div class="container mt-5">

    <div class="d-flex justify-content-between">

        <h1>Proveedores</h1>

        <a
            href="{{ url_for('nuevo_proveedor') }}"
            class="btn btn-primary">
            Nuevo proveedor
        </a>

    </div>

    <hr>

    {% if proveedores %}

    <table class="table table-striped table-bordered">

        <thead class="table-dark">

            <tr>
                <th>Empresa</th>
                <th>Contacto</th>
                <th>Email</th>
                <th>Teléfono</th>
                <th>Dirección</th>
            </tr>

        </thead>

        <tbody>

            {% for proveedor in proveedores %}

            <tr>

                <td>{{ proveedor.empresa }}</td>
                <td>{{ proveedor.contacto }}</td>
                <td>{{ proveedor.email }}</td>
                <td>{{ proveedor.telefono }}</td>
                <td>{{ proveedor.direccion }}</td>

            </tr>

            {% endfor %}

        </tbody>

    </table>

    {% else %}

    <div class="alert alert-info">
        No existen proveedores registrados.
    </div>

    {% endif %}

</div>

{% endblock %}


# ============================================================
# ARCHIVO: templates/formulario_facturacion.html
# ============================================================

{% extends "base.html" %}

{% block content %}

<div class="container mt-5">

    <div class="card shadow">

        <div class="card-header bg-success text-white">

            <h2>Nueva factura</h2>

        </div>

        <div class="card-body">

            <form method="POST">

                {{ form.hidden_tag() }}

                <div class="mb-3">

                    {{ form.cliente.label(
                        class="form-label"
                    ) }}

                    {{ form.cliente(
                        class="form-control"
                    ) }}

                    {% for error in form.cliente.errors %}

                    <div class="text-danger">
                        {{ error }}
                    </div>

                    {% endfor %}

                </div>


                <div class="mb-3">

                    {{ form.producto.label(
                        class="form-label"
                    ) }}

                    {{ form.producto(
                        class="form-control"
                    ) }}

                    {% for error in form.producto.errors %}

                    <div class="text-danger">
                        {{ error }}
                    </div>

                    {% endfor %}

                </div>


                <div class="mb-3">

                    {{ form.cantidad.label(
                        class="form-label"
                    ) }}

                    {{ form.cantidad(
                        class="form-control"
                    ) }}

                    {% for error in form.cantidad.errors %}

                    <div class="text-danger">
                        {{ error }}
                    </div>

                    {% endfor %}

                </div>


                <div class="mb-3">

                    {{ form.precio.label(
                        class="form-label"
                    ) }}

                    {{ form.precio(
                        class="form-control"
                    ) }}

                    {% for error in form.precio.errors %}

                    <div class="text-danger">
                        {{ error }}
                    </div>

                    {% endfor %}

                </div>


                {{ form.submit(
                    class="btn btn-success"
                ) }}

                <a
                    href="{{ url_for('facturacion_lista') }}"
                    class="btn btn-secondary">
                    Cancelar
                </a>

            </form>

        </div>

    </div>

</div>

{% endblock %}


# ============================================================
# ARCHIVO: templates/facturacion.html
# ============================================================

{% extends "base.html" %}

{% block content %}

<div class="container mt-5">

    <div class="d-flex justify-content-between">

        <h1>Facturación</h1>

        <a
            href="{{ url_for('nueva_factura') }}"
            class="btn btn-success">
            Nueva factura
        </a>

    </div>

    <hr>

    {% if facturas %}

    <table class="table table-striped table-bordered">

        <thead class="table-dark">

            <tr>
                <th>Cliente</th>
                <th>Producto</th>
                <th>Cantidad</th>
                <th>Precio unitario</th>
                <th>Total</th>
            </tr>

        </thead>

        <tbody>

            {% for factura in facturas %}

            <tr>

                <td>{{ factura.cliente }}</td>

                <td>{{ factura.producto }}</td>

                <td>{{ factura.cantidad }}</td>

                <td>
                    ${{ "%.2f"|format(factura.precio) }}
                </td>

                <td>
                    ${{ "%.2f"|format(factura.total) }}
                </td>

            </tr>

            {% endfor %}

        </tbody>

    </table>

    {% else %}

    <div class="alert alert-info">
        No existen facturas registradas.
    </div>

    {% endif %}

</div>

{% endblock %}


# ============================================================
# ARCHIVO: static/css/style.css
# ============================================================

body {
    background-color: #f5f5f5;
}

.card {
    border-radius: 10px;
}

h1, h2 {
    font-weight: 600;
}

.text-danger {
    font-size: 0.9rem;
    margin-top: 5px;
}
# ==========================================================

T
