# Análisis de Cancelaciones y Comportamiento de Clientes en Hoteles

**Autor:** Natalia Zárate Yara

---

## Descripción del proyecto

Este proyecto tiene como objetivo analizar el comportamiento de las reservas hoteleras. Se enfoca en factores como la cancelación de reservas, el tiempo de anticipación (*lead_time*), el tipo de cliente y la tarifa diaria promedio (*ADR*). A partir de un análisis exploratorio de datos (EDA), se busca identificar patrones, relaciones y variables clave que influyen en la toma de decisiones de los clientes.

El análisis se desarrolla utilizando PySpark dentro de un entorno controlado con Docker, lo que permite trabajar con grandes volúmenes de datos de manera eficiente y reproducible. Además, se hace uso de JupyterLab, el cuál facilita la visualización, interpretación y documentación del análisis.

Este proyecto tiene un enfoque aplicado, ya que permite entender problemáticas reales del sector hotelero como la alta tasa de cancelaciones.

---

## Instrucciones para ejecutar con Docker

```bash
# Clonar el repositorio
git clone https://github.com/nataliazarate1/parcial1-pyspark--nataliazarate1-.git
cd parcial1-pyspark--nataliazarate1-

# Descargar los datos
# Dataset de reservas hoteleras: https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand

# Construir y ejecutar el contenedor
docker-compose up

# Abrir Jupyter en el navegador
http://localhost:8888
```

---

## Estructura de carpetas

```bash
parcial1-pyspark--nataliazarate1-/
│
├── data/hotel_bookings.csv                # Dataset de reservas hoteleras
├── notebooks/analisis_exploratorio.ipynb  # Análisis
├── docker-compose.yml                     # Configuración de Docker
└── README.md                              # Documentación del proyecto
```

---

## Fuentes de datos

* Hotel Booking Demand Dataset (Kaggle): https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand

---

## Principales hallazgos

* Existe una relación positiva entre el lead_time y la cancelación, lo que indica que reservas con mayor anticipación tienden a cancelarse más.

* El tipo de cliente Transient es el más frecuente.

* Las reservas sin depósito (No Deposit) presentan mayor probabilidad de cancelación.

* Los City Hotel tienen mayor cantidad de reservas y presentan un mayor precio promedio (ADR) en comparación con los Resort Hotel.

* Se identificaron valores atípicos en variables como ADR y lead_time, lo que puede afectar el análisis.

---

## Explicación del archivo `docker-compose.yml`

### ¿Qué es `version` y para qué sirve?

Define la versión del formato de Docker Compose. Es importante para asegurar que el archivo funcione correctamente con la versión de Docker instalada.

### ¿Qué hace la sección `services`?

Define los contenedores que se ejecutarán. En este proyecto, se configura un servicio que ejecuta JupyterLab con PySpark para realizar el análisis de datos.

### ¿De dónde viene la imagen `jupyter/pyspark-notebook`?

Proviene de Docker Hub, específicamente del proyecto Jupyter Docker Stacks, el cual ofrece imágenes listas para usar con Python, Spark y Jupyter preinstalados.

### ¿Qué significa el mapeo de puertos `8888:8888`?

Permite conectar el puerto del contenedor con el del computador, haciendo posible acceder a Jupyter desde:

[http://localhost:8888](http://localhost:8888)

### ¿Qué hacen los `volumes` y por qué son importantes?

Permiten compartir archivos entre el contenedor y el computador.

* Evitan pérdida de datos
* Guardan cambios de forma persistente
* Facilitan trabajar con archivos locales

### ¿Para qué sirve la variable `JUPYTER_ENABLE_LAB`?

Activa JupyterLab, una versión más moderna de Jupyter Notebook que permite trabajar con múltiples archivos, pestañas y herramientas avanzadas.

---

## Referencias

* Kaggle (2024). *Hotel Booking Demand Dataset*.
  [https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand](https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand)

* Docker Inc. (2024). *Docker Documentation*.
  [https://docs.docker.com](https://docs.docker.com)

* Jupyter Project (2024). *Jupyter Docker Stacks*.
  [https://jupyter-docker-stacks.readthedocs.io](https://jupyter-docker-stacks.readthedocs.io)

* Apache Software Foundation (2024). *Apache Spark Documentation*.
  [https://spark.apache.org/docs/latest](https://spark.apache.org/docs/latest)

---

## Conclusión

Este proyecto permite comprender el comportamiento de los clientes en el sector hotelero mediante el uso de herramientas modernas como PySpark y Docker. Los resultados obtenidos evidencian patrones en la cancelación de reservas y en la generación de ingresos, aportando información valiosa para la toma de decisiones en la industria.

