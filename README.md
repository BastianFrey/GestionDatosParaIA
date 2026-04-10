🚀 Gestión de Datos para IA - Sistema de Auditoría Fintech1. Descripción del ProyectoEste repositorio contiene el código base y la infraestructura de un nuevo sistema de procesamiento y almacenamiento de transacciones de pago para una empresa de tecnología financiera (Fintech). El sistema está diseñado bajo estrictos requerimientos regulatorios, garantizando la total inmutabilidad de los registros, el cumplimiento de transacciones ACID y la capacidad de realizar auditorías exactas sobre datos históricos para la generación de reportes regulatorios fijos mensuales.2. Arquitectura SeleccionadaEl sistema utiliza una arquitectura Lakehouse. Se proyecta el uso de Delta Lake como capa de almacenamiento principal para garantizar características transaccionales (ACID) y control de versiones de datos ("Time Travel"). El procesamiento por lotes para la limpieza y consolidación de las auditorías se estructura mediante Apache Spark siguiendo un modelo de capas Medallion (Bronce, Plata, Oro).3. Requisitos y Configuración del Entorno TécnicoPara levantar la base de esta API en un entorno de desarrollo local, se requieren las siguientes herramientas:Control de Versiones: Git Contenedores: Docker Lenguaje: Python 3.11 Framework API: FastAPI / UvicornCI/CD: GitHub Actions y Render (Despliegue Continuo)

4. Instrucciones de Instalación
Siga estos pasos para levantar el entorno de desarrollo localmente:

Clonar el repositorio: 
git clone https://github.com/BastianFrey/GestionDatosParaIA.git

Navegar a la carpeta del proyecto: 
cd GestionDatosParaIA

Crear y activar el entorno virtual:
python -m venv venv
source venv/bin/activate  # En Linux/Mac
.\venv\Scripts\activate   # En Windows

Instalar dependencias locales (opcional para pruebas sin Docker):
pip install -r src/requirements.txt

Construir la imagen de Docker utilizando el archivo proporcionado:
docker build -t fintech-auditoria-api .

Levantar el contenedor exponiendo el puerto 8000:
docker run -p 8000:8000 fintech-auditoria-api

Estructura del Repositorio
El proyecto se organiza bajo las siguientes carpetas y archivos, estableciendo la base técnica colaborativa:

.github/workflows/: Contiene el archivo ci-cd.yml con los flujos automatizados de Integración Continua (CI).

src/: Carpeta principal con el código fuente.

main.py: Lógica central de la API construida en FastAPI.

requirements.txt: Listado de dependencias del entorno.

Dockerfile: Receta con las instrucciones para construir el contenedor.

.env.example: Plantilla de variables de entorno de forma segura.

.gitignore: Exclusión de archivos temporales y entornos locales.

docs/: Carpeta de evidencias técnicas, despliegues y diagramas de arquitectura.
