# Sistema Automatizado de Detección de Vehículos con YOLOv8

## Integrantes
* Cruz Maldonado Héctor Joel - Reg.23310383

## Descripción del Proyecto
Este proyecto consiste en el desarrollo y entrenamiento de un modelo de visión artificial basado en la arquitectura **YOLOv8** (You Only Look Once) para la detección automatizada de automóviles en tiempo real. 

El conjunto de datos (dataset) fue generado y procesado utilizando la plataforma **Roboflow**, optimizando las imágenes para el entrenamiento de un modelo compacto (YOLOv8n), ideal para aplicaciones de alto rendimiento y baja latencia.

---

## Estructura del Repositorio
* `codigo_fuente/`: Contiene el Jupyter Notebook (`.ipynb`) con todo el proceso de instalación, descarga del dataset, configuración e inicio del entrenamiento.
* `evidencias/`: Muestras de imágenes de prueba con las cajas delimitadoras (*bounding boxes*) generadas por el modelo entrenado.
* `requirements.txt`: Archivo de dependencias necesarias para la ejecución del entorno.

---

## Instrucciones para Ejecutar el Código
1. Descargue el archivo de la carpeta `codigo_fuente/` y ábralo en **Google Colab** o en un entorno local con Jupyter.
2. Asegúrese de activar el entorno de ejecución con **GPU** (ej. NVIDIA T4 en Colab).
3. Instale las dependencias ejecutando:
   ```bash
   pip install -r requirements.txt
