# GestionDatosParaIA

Este repositorio contiene la configuración inicial de un entorno de desarrollo y despliegue continuo (CI/CD) diseñado para alojar soluciones basadas en datos e inteligencia artificial.

## 🎯 Objetivo
Configurar una heurística de trabajo reproducible y escalable mediante la contenerización de una API, aplicando buenas prácticas de automatización y preparándola para su integración con bases de datos en la nube.

## 🛠️ Decisiones Tecnológicas y Justificación

Para este proyecto se ha seleccionado el siguiente stack tecnológico:

* **Lenguaje (Python):** Se eligió Python por ser el estándar de la industria para proyectos de Gestión de Datos e Inteligencia Artificial, ofreciendo un ecosistema robusto de librerías.
* **Framework (FastAPI):** Se optó por FastAPI debido a su alto rendimiento, facilidad para construir APIs RESTful modernas y su generación automática de documentación.
* **Contenerización (Docker):** El uso de Docker garantiza que la aplicación se ejecute de manera idéntica en cualquier entorno (desarrollo, pruebas y producción), eliminando el problema de "en mi máquina sí funciona".
* **CI/CD (GitHub Actions):** Se implementó un flujo de Integración Continua para automatizar la revisión del código y la instalación de dependencias en cada `push` a la rama principal, asegurando la trazabilidad del proceso.
* **Base de Datos (Supabase - Próximamente):** Se utilizará PostgreSQL gestionado por Supabase para el almacenamiento estructurado de datos.
* **Despliegue (Render - Próximamente):** La aplicación será desplegada en la nube utilizando Render por su excelente integración con GitHub y Docker.

## 📂 Estructura del Proyecto

* `.github/workflows/`: Contiene el archivo `ci-cd.yml` con las instrucciones de automatización para GitHub Actions.
* `src/`: Directorio principal del código fuente. Contiene `main.py` (la lógica de la API) y `requirements.txt` (las dependencias).
* `Dockerfile`: Receta paso a paso para construir la imagen del contenedor de la aplicación.
* `.env.example`: Plantilla con las variables de entorno necesarias para la ejecución segura del proyecto.
* `.gitignore`: Archivo de exclusión para evitar subir archivos temporales o sensibles al repositorio público.

## 🚀 Cómo ejecutar en local (Desarrollo)

1. Clonar el repositorio.
2. Crear un entorno virtual: `python -m venv venv`
3. Activar el entorno virtual.
4. Instalar dependencias: `pip install -r src/requirements.txt`
5. Ejecutar la aplicación: `uvicorn src.main:app --reload`