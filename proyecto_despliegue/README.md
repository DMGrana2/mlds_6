# API de Predicción de Deslizamientos con Deep Learning
---

Este proyecto implementa una **API REST con FastAPI** para predecir la *susceptibilidad a deslizamientos* utilizando un modelo de **red neuronal convolucional (CNN)** previamente entrenado con datos geoespaciales.

La solución fue desarrollada en el contexto de una *hackathon de inteligencia artificial* orientada a la mitigación del riesgo por deslizamientos en la zona cafetera de Colombia.

URL: "https://web-production-8a55.up.railway.app/docs#/default/predecir_predict_post"

---

## Objetivo

Proveer un servicio web que permita predecir, a partir de un cubo de datos multibanda (13x13x7), la probabilidad de ocurrencia de un deslizamiento en una zona específica.

---

## Modelo

- Arquitectura: CNN profunda con 3 capas convolucionales y una capa densa final.
- Entrenado con: 851 cubos extraídos de un stack multibanda de 7 variables.
- Precisión validación: **~76%**
- Entrada esperada: tensor de tamaño `(13, 13, 7)` (listado anidado en JSON).
- Salida: `0` (no susceptible) o `1` (susceptible).

---

## Despliegue

El modelo se despliega como una API utilizando **FastAPI** y **Uvicorn**. Fue diseñado para ser desplegado fácilmente en plataformas como **Railway** o **Render**.

### Archivos clave:

- `main.py`: código de la API.
- `modelo_deslizamientos.h5`: modelo entrenado.
- `requirements.txt`: dependencias necesarias.
- `Procfile`: especificaciones para el servidor de producción.

---

## Uso de la API

### Endpoint principal: `/predict` (POST)
