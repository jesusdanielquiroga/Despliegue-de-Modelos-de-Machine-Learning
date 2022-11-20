 <p align="left">
   <img src="https://img.shields.io/badge/status-en%20desarrollo-green"> 
   <img src="https://img.shields.io/github/issues/jesusdanielquiroga/Despliegue-de-Modelos-de-Machine-Learning">
   <img src="https://img.shields.io/github/forks/jesusdanielquiroga/Despliegue-de-Modelos-de-Machine-Learning">
   <img src="https://img.shields.io/github/forks/jesusdanielquiroga/Despliegue-de-Modelos-de-Machine-Learning">
   <img src="https://img.shields.io/github/license/jesusdanielquiroga/Despliegue-de-Modelos-de-Machine-Learning">
<a href="https://twitter.com/intent/tweet?text=Wow:&url=https%3A%2F%2Fgithub.com%2Fjesusdanielquiroga%2FDespliegue-de-Modelos-de-Machine-Learning"><img alt="Twitter" src="https://img.shields.io/twitter/url?style=social&url=https%3A%2F%2Ftwitter.com%2Fjdquiroga2410"></a>
   <img src="https://img.shields.io/github/stars/camilafernanda?style=social">
   <img src="https://img.shields.io/badge/topic-machinelearning-red">
  </p>

# Despliegue de Modelos de Machine Learning

# Índice

* [Índice](#índice)

* [¿Qué es el despliegue de modelos?](#¿qué-es-el-despliegue-de-modelos?)

* [Historia de los MLOps](#historia-de-los-MLOps)

* [Flujo de vida de un modelo en producción](#flujo-de-vida-de-un-modelo-en-producción)

* [Requerimientos para poder hacer MLOps](#requerimientos-para-poder-hacer-MLOps)

* [Patrones de diseño para model serving](#patrones-de-diseño-para-model-serving)

# ¿Qué es el despliegue de modelos?

Definiremos el despliegue de modelos como la transformación de un modelo en producto que puede ser utilizado como servicio por un tercero.

El término MLOps se define como "la extensión de la metodología DevOps para incluir activos de Machine Learning y Data Science como ciudadanos de primera clase dentro de la ecología DevOps" Fuente: <a href="roadmap/2020/MLOpsRoadmap2020.md">MLOps SIG</a>.

![ThreeLevelsOfChange](https://user-images.githubusercontent.com/87950040/202930212-c6c17990-ac82-4b38-a103-a3a3dc70b55e.jpg)
Fuente: <a href="https://ml-ops.org/content/motivation">MLOps</a>

```
La ingeniería de aprendizaje automático es el uso de principios científicos, herramientas y técnicas de aprendizaje automático
e ingeniería de software para diseñar y construir sistemas complejos para que estén disponibles como productos.

-Andriy Burkov
```
# Historia de los MLOps

A principios de la década de 2000, cuando las empresas necesitaban implementar soluciones de aprendizaje automático, usaban el software con licencia de los proveedores, como SAS, SPSS y FICO. Con el auge del software de código abierto y la disponibilidad de datos, más profesionales de software comenzaron a usar bibliotecas Python o R para entrenar modelos ML. Sin embargo, el uso de los modelos en producción seguía siendo un problema. A medida que iba surgiendo la tecnología de contenerización, se resolvió el despliegue del modelo de forma escalable mediante el uso de contenedores Docker y Kubernetes. Recientemente, vemos la evolución de esas soluciones hacia plataformas de implementación de ML que cubren toda la iteración de experimentación, capacitación, implementación y monitoreo de modelos. La siguiente Figura visualiza la evolución de los MLOps.

![mlops-evolution](https://user-images.githubusercontent.com/87950040/202930485-46580050-e940-49e9-836b-e8358475a991.jpg)

# Flujo de vida de un modelo en producción

Una descripción general del flujo de trabajo de aprendizaje automático de extremo a extremo, <a href="https://ml-ops.org/content/end-to-end-ml-workflow">más información...</a>

![ml-engineering](https://user-images.githubusercontent.com/87950040/202930891-acbc3c1d-ee76-429c-9a3c-ecdb2ea00a00.jpg)

El framework <a href="https://github.com/aws-solutions/mlops-workload-orchestrator">aws-mlops</a> puede usarse para trabajar también este tipo de operaciones:

![architecture-option-1](https://user-images.githubusercontent.com/87950040/202930964-1f7a0f58-f2a2-47d3-9225-ef053db6c9d7.png)

# Requerimientos para poder hacer MLOps

* Ingeniería de datos
  * Ingesta de datos
  * Manejo de datos
* Machine Learning Pipelines
  * Entrenamiento de modelo
  * Evaluación de modelo
  * Empaquetado y serialización de modelo
* Deployment Pipelines
  * Servicio de modelo
  * Monitoreo del rendimiento del modelo

# Patrones de diseño para model serving

<img width="592" alt="Captura de pantalla 2022-11-20 180723" src="https://user-images.githubusercontent.com/87950040/202931560-a6fdf77f-f803-4543-85e2-17661f205bfc.png">

* Model-as-Service (será el que implementaremos en el curso): El modelo es un servicio que puede ser visitado por una request (por ejemplo vía protocolo http)

* Model-as-Depenency: El modelo está incrustado dentro de la dependencia que se está utilizando en la aplicación. Por lo que podría ser consumido llamando al atributo predict() y tener la inferencia

* Precompute Serving Pattern: El modelo ya existe y hace predicciones. Esas predicciones serán guardadas en bases de datos que serán visitadas con posterioridad

* Model-on-Demand: Se utiliza para arquitecturas en streaming. Tenemos el message broker que es el encargado del flujo entre envía los inputs para las predicciones desde los datos, y envía las predicciones hechas por el modelo al servicio que lo requiera.

* Federated Learning (o Hybrid Learning): Es un grupo de modelos. Se asigna un modelo por cada usuario que utilicé la aplicación, y sus datos son los que entrenarán al modelo que luego hará predicciones.


