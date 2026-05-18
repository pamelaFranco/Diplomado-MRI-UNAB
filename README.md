# Diplomado en Resonancia Magnética (MRI) - UNAB
## Módulo: Radiómica y Machine Learning aplicado a Neuroimágenes

Este repositorio contiene el material práctico y los códigos base utilizados para las clases de **Radiómica** y **Machine Learning (ML)** aplicados al análisis de imágenes de Resonancia Magnética, con un enfoque particular en la clasificación de tumores cerebrales (Gliomas).

---

## Estructura del Repositorio

El proyecto cuenta con dos cuadernos de Jupyter (`.ipynb`) principales que guían el flujo de trabajo biomédico:

* **`radiomics.ipynb`**: Código enfocado en la extracción de características radiómicas a partir de secuencias de RM y segmentaciones (ROIs). Incluye análisis de forma, intensidad de píxel y texturas (matrices de co-ocurrencia, etc.).
* **`Glioma_classification.ipynb`**: Código dedicado a la etapa de Machine Learning. Toma las características extraídas (u otras bases de datos) para entrenar, validar y evaluar modelos de clasificación que permitan diferenciar tipos o grados de Gliomas.

---

## Requisitos e Instalación

Para ejecutar estos cuadernos de forma local, se recomienda contar con un entorno de Python (versión 3.8 o superior). 

1. **Clonar o descargar** este repositorio en tu máquina local:
   ```bash
   cd C:\Users\pfran\Desktop\Diplomado MRI - UNAB
   ```

2. Instalar las librerías principales necesarias para el procesamiento médico y el modelado:

```
pip install pyradiomics numpy pandas scikit-learn matplotlib seaborn SimpleITK
```

(Nota: `pyradiomics` es la librería estándar para la extracción de características compatibles con IBSI).

3. Iniciar *Jupyter Lab / Notebook*:
```
jupyter notebook
```

---

## Contenido Académico

**1. Extracción de Características**

* **Cuaderno:** * **Cuaderno:** [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/pamelaFranco/Diplomado-MRI-UNAB/blob/main/radiomics.ipynb)

En esta sección práctica se aborda cómo transformar una imagen médica cualitativa en datos cuantitativos de alto rendimiento:

* Carga de volúmenes médicos (formatos .nii / .nii.gz).

* Configuración del extractor PyRadiomics (normalización de intensidad, remuestreo/resampling).

* Obtención de características de primer orden, forma (Shape) y texturas (GLCM, GLRLM, GLSZM).

**2. Clasificación de Gliomas**

* **Cuaderno:** * **Cuaderno:** [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/pamelaFranco/Diplomado-MRI-UNAB/blob/main/Glioma_classification.ipynb)

Una vez obtenidos los datos, se aplican técnicas de Inteligencia Artificial para la toma de decisiones clínicas:

* Preprocesamiento de datos (limpieza de valores nulos, escalado de variables).

* Selección de características relevantes (reducción de dimensionalidad).

* Entrenamiento de clasificadores (ej. Random Forest).

* Evaluación mediante métricas asistidas por computadora: Curva ROC, AUC, Matriz de Confusión, Sensibilidad y Especificidad.

---


## Institución
Universidad Andrés Bello (UNAB)

Programa: Diplomado en Resonancia Magnética (MRI)

Propósito: Material docente / Laboratorio práctico.

--- 

## License

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)