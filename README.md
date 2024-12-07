
# 🛠️ Guía de Instalación y Ejecución

Este proyecto es una aplicación Flask que muestra datos procesados desde un archivo CSV y utiliza plantillas HTML para renderizar las vistas.

## 📋 Requisitos

Antes de comenzar, asegúrate de tener lo siguiente instalado en tu sistema:

- **Python 3.10 o superior**
- **pip** (Administrador de paquetes de Python)
- **Git** (opcional, para clonar el repositorio)

## 🚀 Instalación

Sigue estos pasos para instalar y configurar el proyecto en tu máquina local:

1. **Clona el repositorio**:
   ```bash
   git clone <URL_DEL_REPOSITORIO>
   cd <NOMBRE_DEL_PROYECTO>
   ```

2. **Crea un entorno virtual** (opcional, pero recomendado):
   ```bash
   python -m venv venv
   source venv/bin/activate  # En Windows: venv\Scripts\activate
   ```

3. **Instala las dependencias**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Asegúrate de que el archivo CSV requerido exista**:
   Coloca el archivo `Enaho01-2020-100.csv` en la raíz del proyecto. Este archivo es necesario para que la aplicación funcione correctamente.

## ▶️ Ejecución en Local

Para ejecutar la aplicación localmente, sigue estos pasos:

1. **Ejecuta la aplicación Flask**:
   ```bash
   flask run
   ```

   O utiliza **gunicorn** para un entorno más cercano a producción:
   ```bash
   gunicorn -w 4 -b 0.0.0.0:5000 app:app
   ```

2. **Accede a la aplicación**:  
   Abre tu navegador web y dirígete a [http://127.0.0.1:5000](http://127.0.0.1:5000).

## 🌐 Despliegue en Render

Sigue estos pasos para desplegar tu aplicación en **Render**:

1. **Configura el archivo `Procfile`**:
   Asegúrate de que el archivo `Procfile` esté correctamente configurado:
   ```plaintext
   web: gunicorn -w 4 -b 0.0.0.0:${PORT} app:app
   ```

2. **Sube tu repositorio**:  
   En el panel de Render, crea un nuevo servicio web y enlaza tu repositorio.

3. **Define el comando de inicio**:  
   En el campo **Start Command**, ingresa:
   ```bash
   gunicorn -w 4 -b 0.0.0.0:${PORT} app:app
   ```

4. Render detectará automáticamente las dependencias desde `requirements.txt` y desplegará tu aplicación.

## 📂 Estructura del Proyecto

```plaintext
/
├── templates/        # Archivos HTML para las vistas
│   ├── index.html    # Página principal
│   ├── graficos.html # Página de gráficos
│   └── graficos2.html
├── app.py            # Código principal de la aplicación Flask
├── limpieza.py       # Módulo para la limpieza y lectura de datos CSV
├── requirements.txt  # Lista de dependencias
└── Procfile          # Archivo de configuración para despliegue
```

## 🛠️ Tecnologías Utilizadas

- **Flask**: Framework para construir aplicaciones web.
- **Gunicorn**: Servidor WSGI para entornos de producción.
- **Jinja2**: Motor de plantillas para Flask.
- **Pandas**: Procesamiento de datos desde el archivo CSV.

## ❓ Problemas Comunes

1. **El archivo CSV no existe**:  
   Asegúrate de que el archivo `Enaho01-2020-100.csv` esté en la raíz del proyecto.

2. **Puerto ocupado**:  
   Si el puerto `5000` está en uso, especifica otro al ejecutar:
   ```bash
   flask run --port=8000
   ```

3. **Error en Render**:  
   Verifica que `requirements.txt` incluya todas las dependencias necesarias.

## 📧 Contacto

Si tienes preguntas o problemas, no dudes en contactarme.
