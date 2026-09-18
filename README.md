# 🌿 Proyecto Flask - Naturaleza & Experiencia Web

![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-3.0.0-000000?style=for-the-badge&logo=flask&logoColor=white)
![Render](https://img.shields.io/badge/Render-Deployed-46E3B7?style=for-the-badge&logo=render&logoColor=white)
![Licencia](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

Una aplicación web moderna y elegante construida con **Python** y **Flask**, diseñada con un estilo orgánico inspirado en los colores de la naturaleza, efectos de cristal esmerilado (*glassmorphism*), tipografía sobria y gráficos vectoriales **SVG**.

---

## 🛠️ Tecnologías Utilizadas

- **Backend**: Python 3, Flask, Gunicorn
- **Frontend**: HTML5, Vanilla CSS3 (Variables CSS, Flexbox, CSS Grid, Glassmorphism, Micro-animaciones)
- **Recursos**: SVG Vectorial puro, Google Fonts (*Playfair Display* & *Plus Jakarta Sans*)
- **Despliegue**: Render, Git & GitHub

---

## 🚀 Aprende a Replicar este Proyecto

Guía paso a paso para construir la aplicación en tu propia máquina.

### Paso 1: Instalar Python y Git
Asegúrate de tener Python 3.10+ y Git instalados en tu sistema operativo.

```bash
# Verificar la versión de Python
python --version

# Verificar la versión de Git
git --version
```

---

### Paso 2: Crear la Estructura de Carpetas
Crea la carpeta de tu proyecto y entra en ella:

```bash
mkdir mi_proyecto_python
cd mi_proyecto_python
```

---

### Paso 3: Crear y Activar el Entorno Virtual (`.venv`)
El entorno virtual aísla las librerías de tu proyecto para no afectar tu computadora.

```bash
# Crear entorno virtual
python -m venv .venv

# Activar en Windows (PowerShell)
.\.venv\Scripts\Activate.ps1

# Activar en Mac/Linux
source .venv/bin/activate
```

---

### Paso 4: Crear `requirements.txt` e Instalar Dependencias
Guarda tus dependencias en `requirements.txt` (incluyendo `gunicorn` para el despliegue):

```bash
# Escribir las dependencias
echo Flask>=3.0.0 > requirements.txt
echo gunicorn>=21.2.0 >> requirements.txt

# Instalar dependencias
pip install -r requirements.txt
```

---

### Paso 5: Crear el Servidor Flask (`app.py`)
Crea el archivo `app.py` que controlará las rutas de tu servidor:

```python
from flask import Flask, render_template

app = Flask(__name__)

@app.route('/')
def home():
    return render_template('index.html')

if __name__ == '__main__':
    app.run(debug=True)
```

---


### Paso 7: Ejecutar el Servidor Web Localmente
Corre tu servidor con Python:

```bash
python app.py
```

Abre tu navegador en:  
`http://127.0.0.1:5000/`

---

## 🌐 Despliegue en la Nube (Render)

### ¿Qué es Gunicorn y el archivo `Procfile`?

1. **¿Qué es Gunicorn?**  
   El servidor integrado de Flask (`app.run()`) es solo para pruebas locales. **Gunicorn** es un servidor WSGI de grado de producción diseñado para procesar múltiples peticiones de forma rápida, segura y estable cuando tu aplicación está en producción en internet.

2. **¿Qué es el archivo `Procfile`?**  
   Es un archivo de texto simple sin extensión que indica a plataformas en la nube como Render o Heroku qué comando ejecutar para iniciar la aplicación web. Contiene:
   ```text
   web: gunicorn app:app
   ```
   *(El primer `app` es el archivo `app.py` y el segundo `app` es la variable de la aplicación `app = Flask(__name__)`).*

---

### Pasos para Desplegar en Render con GitHub

1. **Crear el archivo `Procfile` en la raíz del proyecto:**
   ```bash
   echo web: gunicorn app:app > Procfile
   ```

2. **Subir tu proyecto a GitHub:**
   ```bash
   git init
   git add .
   git commit -m "Primer commit: Proyecto Flask Naturaleza"
   git branch -M main
   git remote add origin https://github.com/TU_USUARIO/TU_REPOSITTORIO.git
   git push -u origin main
   ```

3. **Configurar en Render:**
   - Entra a [Render.com](https://render.com) e inicia sesión.
   - Haz clic en **`+ New`** -> **`Web Service`**.
   - Conecta tu cuenta de **GitHub** y selecciona tu repositorio.
   - Llena la configuración con estos valores:
     - **Name**: `mi-proyecto-flask`
     - **Runtime**: `Python 3`
     - **Build Command**: `pip install -r requirements.txt`
     - **Start Command**: `gunicorn app:app`
   - Haz clic en **Create Web Service**. ¡Listo! Render te dará un enlace público HTTPS para acceder a tu sitio web desde cualquier dispositivo.

---

### 👤 Autor
**Juan Pablo Restrepo Alzate**

---

## Evidencias

1. [Evidencia del repositorio de Git](https://github.com/JPablo2004/mi_proyecto_python.git)
2. [Evidencia del pull request al repositorio original](https://github.com/g3in-unilasallista/mi_proyecto_python/pull/16)
3. [Evidencia del despliegue público en Render](https://mi-proyecto-python-j1yw.onrender.com/)
4. [Evidencia de ejecución local 1](pantallazos/WhatsApp%20Image%202026-09-18%20at%2011.31.48%20AM.jpeg)
5. [Evidencia de ejecución local 2](pantallazos/WhatsApp%20Image%202026-09-18%20at%2011.32.24%20AM.jpeg)
