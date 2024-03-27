from flask import Flask, jsonify

app = Flask(__name__)

# Datos de ejemplo (reemplaza con datos reales)
clima = {
    "Argentina": {"temperatura": 25, "condiciones": "soleado"},
    "Brasil": {"temperatura": 30, "condiciones": "lluvioso"},
    # ... otros países ...
}

mercado_agricola = {
    "Argentina": {"compradores": ["EE. UU.", "China"], "proveedores": ["Brasil", "Canadá"]},
    # ... otros países ...
}

politica = {
    "Argentina": {"eventos": ["Elecciones presidenciales", "Protestas"], "conflictos": ["Frontera con Chile"]},
    # ... otros países ...
}

demografia = {
    "Argentina": {"poblacion": 45000000, "tendencias": "crecimiento estable"},
    # ... otros países ...
}

@app.route("/clima/<pais>")
def obtener_clima(pais):
    return jsonify(clima.get(pais, "País no encontrado"))

@app.route("/mercado_agricola/<pais>")
def obtener_mercado_agricola(pais):
    return jsonify(mercado_agricola.get(pais, "País no encontrado"))

@app.route("/politica/<pais>")
def obtener_politica(pais):
    return jsonify(politica.get(pais, "País no encontrado"))

@app.route("/demografia/<pais>")
def obtener_demografia(pais):
    return jsonify(demografia.get(pais, "País no encontrado"))

if __name__ == "__main__":
    app.run(debug=True)
    
