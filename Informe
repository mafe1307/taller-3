# Taller 3: Medallón Spark & Arquitectura  
**Módulo 3: Spark**

# *Presentado por: Maria Fernanda Torres, Ingrid Melissa Céspedes Díaz

## 1. Introducción
El Taller 3 forma parte del **Módulo 3: Spark** y se basa en la implementación del  
**Capítulo 11: Arquitectura Medallion**.

El objetivo principal fue simular un flujo de datos real bajo el enfoque **Lakehouse**,
resolviendo un reto clave de la ingeniería de datos: la implementación de una
**Puerta de Calidad (Quality Gate)** que permita detectar datos corruptos y
gestionarlos de forma controlada, sin perder trazabilidad.

---

## 2. Objetivos del Taller

### Objetivo general
Diseñar e implementar un pipeline de datos en Spark utilizando la arquitectura
Medallion, incorporando controles de calidad y una zona de cuarentena.

### Objetivos específicos
- Desplegar un clúster completo de Spark (**Master, Worker y Jupyter**) usando **Docker**.
- Construir un pipeline de datos con capas **Bronze, Silver y Gold**.
- Implementar un **Quality Gate** para la validación de datos.
- Redirigir los registros corruptos a una **zona de Cuarentena**, en lugar de eliminarlos.

---

## 3. Infraestructura Implementada
La infraestructura fue desplegada mediante contenedores Docker y está compuesta por:

- **Spark Master:** coordinación y administración del clúster.
- **Spark Worker:** ejecución de tareas de procesamiento distribuido.
- **Jupyter Notebook:** entorno interactivo para el desarrollo, ejecución y validación del pipeline.

Este entorno permitió simular un escenario real de procesamiento de datos a escala.

---

## 4. Arquitectura de Datos (Medallion Architecture)

La solución se implementó bajo el enfoque de **Arquitectura Medallion**, incorporando
una capa adicional de **Cuarentena** para el manejo de datos inválidos.

### Flujo de la Arquitectura

```mermaid
flowchart LR
    Bronze[Bronze<br/>(Crudo)]
    Silver[Silver<br/>(Limpio)]
    Quarantine[Quarantine<br/>(Datos inválidos)]
    Gold[Gold<br/>(Agregado)]

    Bronze --> Silver
    Silver -->|inválidos| Quarantine
    Silver -->|válidos| Gold

    style Quarantine fill:#ffe6e6,stroke:#cc0000,stroke-width:2px
