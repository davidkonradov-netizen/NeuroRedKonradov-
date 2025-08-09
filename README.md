# NeuroRedKonradov-

neurored-konradov/
├── main.py                # Backend principal
├── requirements.txt       # Dependencias
├── Procfile               # Config para Railway
├── .gitignore            # Ignorar archivos innecesarios
└── README.md             # Instrucciones

from flask import Flask, render_template_string, jsonify

app = Flask(__name__)

@app.route("/")
def home():
    return render_template_string('''
    <!DOCTYPE html>
    <html>
    <head>
        <title>NeuroRed Konradov</title>
        <style>
            body { background: #0d1117; color: #c9d1d9; font-family: monospace; padding: 2rem; }
            h1 { color: #58a6ff; }
            button { background: #238636; color: white; padding: 10px 20px; border: none; cursor: pointer; }
        </style>
    </head>
    <body>
        <h1>NeuroRed Konradov 🚀</h1>
        <p>¡Desplegado en Railway!</p>
        <button onclick="alert('¡Hola desde Flask!')">Saludar</button>
    </body>
    </html>
    ''')

@app.route("/api/status")
def status():
    return jsonify({"status": "active", "nodes": 3})

if __name__ == "__main__":
    app.run(host='0.0.0.0', port=int(os.environ.get('PORT', 8080)))


    flask==2.3.3
gunicorn==21.2.0


web: gunicorn --bind 0.0.0.0:$PORT main:app

__pycache__/
*.pyc
.env


# NeuroRed Konradov

Despliegue en Railway:
1. Conecta este repositorio a [Railway.app](https://railway.app/).
2. Espera a que detecte automáticamente el proyecto.
3. ¡Listo! Tu app estará en `https://[nombre-del-proyecto].railway.app`.

## Endpoints
- `/`: Interfaz web.
- `/api/status`: API de estado.

- 
