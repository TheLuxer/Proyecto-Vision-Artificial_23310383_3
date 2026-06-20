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
## Caso de Estudio: Sistema Automatizado de Acceso Vehicular para Grupo Eléctrico
### 1. Problema a Resolver
El registro manual de vehículos en la entrada de las instalaciones y almacenes genera cuellos de botella operativos y vulnerabilidades de seguridad. Se requiere un sistema automatizado que detecte la presencia de vehículos para agilizar el acceso de unidades de servicio, técnicos y proveedores, optimizando la logística de entrada y salida sin intervención manual constante.
### 2. Descripción del Hardware Propuesto
* Cámaras: Una cámara de seguridad tipo bala (o una cámara con lente gran angular tipo AIO) instalada a 3 metros de altura en el pórtico de entrada, orientada hacia el carril de acceso.
* Procesamiento: Una PC Industrial (IPC) ubicada en la caseta de control. Esta computadora ejecuta el modelo YOLO optimizado para inferencia en tiempo real.
* Maquinaria y Control: Una barrera vehicular electromecánica controlada por un PLC (Controlador Lógico Programable).
### 3. Flujo de Funcionamiento
* Captura: La cámara transmite el flujo de video en vivo (RTSP) a la PC Industrial.
* Inferencia: El modelo YOLO analiza los fotogramas en tiempo real. Cuando un vehículo ingresa a la zona de interés (ROI) designada frente a la barrera, el modelo lo detecta y clasifica la caja delimitadora (*bounding box*) con un nivel de confianza superior al 85%.
* Comunicación: Al confirmar la detección válida, un script en Python envía una señal digital a través de la red local (por ejemplo, usando un cliente OPC UA o un protocolo Modbus TCP) directamente al PLC.
* Acción: El PLC, programado previamente en un entorno como CODESYS, procesa la señal de entrada, valida los bloqueos de seguridad (asegurándose de que no haya peatones) y activa la salida a relé que levanta la barrera vehicular automáticamente, permitiendo el paso.
