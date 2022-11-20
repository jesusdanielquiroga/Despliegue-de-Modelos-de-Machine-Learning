 <p align="left">
   <img src="https://img.shields.io/badge/status-en%20desarrollo-green"> 
   <img src="https://img.shields.io/github/issues/jesusdanielquiroga/Despliegue-de-Modelos-de-Machine-Learning">
   <img src="https://img.shields.io/github/forks/jesusdanielquiroga/Despliegue-de-Modelos-de-Machine-Learning">
   <img src="https://img.shields.io/github/forks/jesusdanielquiroga/Despliegue-de-Modelos-de-Machine-Learning">
   <img src="https://img.shields.io/github/license/jesusdanielquiroga/Despliegue-de-Modelos-de-Machine-Learning">
<a href="https://twitter.com/intent/tweet?text=Wow:&url=https%3A%2F%2Fgithub.com%2Fjesusdanielquiroga%2FIntroduccion-Base-de-Datos"><img alt="Twitter" src="https://img.shields.io/twitter/url?style=social&url=https%3A%2F%2Ftwitter.com%2Fjdquiroga2410"></a>
   <img src="https://img.shields.io/github/stars/camilafernanda?style=social">
   <img src="https://img.shields.io/badge/topic-machinelearning-red">
  </p>

# Despliegue de Modelos de Machine Learning

# Índice

* [Índice](#índice)

* [¿Qué es el despliegue de modelos?](#¿qué-es-el-despliegue-de-modelos?)

* [Historia de los MLOps](#historia-de-los-MLOps)

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
