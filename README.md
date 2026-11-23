# 🔎 El Detective de Señales

Proyecto de **Telecomunicaciones** para identificar automáticamente cuatro tipos de modulación de señales (**ASK, FSK, PSK y 16-QAM**) usando una red neuronal convolucional **CNN 1D**, desarrollada en **Python** con **TensorFlow/Keras**.

## Contenido

El proyecto está completo en **un solo cuaderno**: [`Detective_Senales_Fases_1_2_3.ipynb`](Detective_Senales_Fases_1_2_3.ipynb).

| Fase | Actividad | Resultado principal |
|---|---|---|
| **1** | Generar señales con AWGN y separar los datos | 4,000 señales: 3,200 para entrenamiento/validación y 800 reservadas para prueba |
| **2** | Diseñar, compilar y entrenar una CNN 1D | Modelo guardado en `modelo_senales.keras` y gráficas de entrenamiento |
| **3** | Evaluar el clasificador ante diferentes niveles de ruido | Matriz de confusión, precisión por SNR, análisis de errores y `Resultados_Fase3.zip` |

## Cómo ejecutarlo en Google Colab

1. Abre [Google Colab](https://colab.research.google.com/).
2. Elige **Archivo → Subir cuaderno** y selecciona `Detective_Senales_Fases_1_2_3.ipynb`.
3. En el menú superior selecciona **Entorno de ejecución → Ejecutar todas**.
4. Revisa los resultados debajo de cada celda y descarga desde el panel de archivos los archivos que necesites.

**No es necesario cargar datos ni el modelo por separado.** El cuaderno genera el dataset en Fase 1, entrena y guarda el modelo en Fase 2 y lo evalúa en Fase 3.

## Tecnologías

- Python 3 y Google Colab / Jupyter Notebook
- NumPy y Pandas
- Matplotlib y SciPy
- Scikit-learn
- TensorFlow / Keras

## Datos del experimento

- Frecuencia de muestreo: **8,000 Hz**
- Frecuencia portadora: **1,600 Hz**
- Tasa de símbolos: **250 símbolos/s**
- **1,024** muestras por señal
- Modulación: 2-ASK (OOK), 2-FSK, BPSK y 16-QAM
- Ruido AWGN con SNR de **−5, 0, 5, 10, 15 y 20 dB**
- **1,000** ejemplos por cada tipo de modulación

## Resultados

La precisión no está fijada: se calcula cada vez que se entrena y evalúa el modelo. En la Fase 2 se reserva una validación independiente del conjunto de prueba; en la Fase 3 se evalúa únicamente con las 800 señales de prueba que se habían separado desde el principio.

## Archivos del repositorio

```text
Detective_Senales_Fases_1_2_3.ipynb
README.md
requirements.txt
.gitignore
```

Los conjuntos de datos, archivos `.keras` y gráficas se **generan al ejecutar el programa** y se excluyen del repositorio con `.gitignore` para mantenerlo ligero.

## Nota

Las señales son **simuladas**, no mediciones de equipos de radio reales. Los resultados de la Fase 3 describen el comportamiento ante los niveles de ruido evaluados y no garantizan rendimiento fuera de estas condiciones.
