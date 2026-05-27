# Diplomado en Resonancia Magnética (MRI) - UNAB
## Módulo: Radiómica y *Machine Learning*

<p align="center">
  <img src="Figures/Imagen1.png" alt="Panel de Diagnóstico Interactivo y Gráfico SHAP" width="80%">
</p>

Este repositorio contiene el material práctico y los códigos base utilizados para las clases de **Radiómica** y **Machine Learning (ML)** aplicados al análisis de imágenes de Resonancia Magnética (MRI), con un enfoque particular en la clasificación de tumores cerebrales (Gliomas).

---

## Estructura del Repositorio

El proyecto está organizado de la siguiente manera:

```text
├── Codes/
│   ├── radiomics.ipynb               # Extracción de características con PyRadiomics
│   └── ML.ipynb                      # Pipeline de Radiómica avanzada en la selección de características y clasificación automatizada de gliomas
│   └── Glioma_classification.ipynb   # Modelado predictivo, SHAP e interfaz interactiva
├── Clase/
│   ├── ML_UNAB.pdf                   # Clase en formato PDF
├── Figures/                          # Imágenes que conforman el laboratorio virtual
├── Dataset/                          # Extracción de radiómica en imágenes T1 para la clasificación de gliomas
└── README.md                         # Documentación del laboratorio
```

* **`radiomics.ipynb`**: Código enfocado en la extracción de características radiómicas a partir de secuencias de RM y segmentaciones (ROIs). Incluye análisis de forma, intensidad de píxel y texturas (matrices de co-ocurrencia, etc.).
* **`ML.ipynb`**: Código enfocado en el procesamiento de datos radiómicos previamente extraídos de secuencias T1. Incluye la estandarización de las variables, un filtrado estadístico mediante el método ANOVA (`SelectKBest`) para identificar las características más significativas, la visualización de la separación de clases en un espacio bidimensional utilizando el algoritmo no lineal t-SNE, y concluye con el entrenamiento de una regresión logística evaluada mediante una matriz de confusión para clasificar gliomas en bajo (LGG) y alto grado (HGG).
* **`Glioma_classification.ipynb`**: Código dedicado a la etapa de **Machine Learning**. Toma las características extraídas (u otras bases de datos) para entrenar, validar y evaluar modelos de clasificación que permitan diferenciar tipos o grados de Gliomas.

---

## Requisitos e Instalación

Puedes ejecutar este laboratorio de dos maneras:

* **Opción A: Ejecución Local (Recomendado)** 
Se requiere contar con un entorno de Python (versión 3.8 o superior).

1. **Clonar o descargar** este repositorio en tu máquina local:
   ```bash
   git clone [https://github.com/pamelaFranco/Diplomado MRI - UNAB.git](https://github.com/pamelaFranco/Diplomado MRI - UNAB.git)
   ```

2. **Crear e instalar las librerías** necesarias en tu entorno:
  
   ```bash
   pip install pyradiomics numpy pandas scikit-learn matplotlib seaborn SimpleITK notebook
   ```

(Nota: `pyradiomics` es la librería estándar para la extracción de características compatibles con IBSI).

3. **Iniciar Jupyter Notebook**:
   ```bash
   jupyter notebook
   ```

* **Opción B: Descarga Directa**
  Si no utilizas Git, puedes descargar el proyecto completo en un archivo comprimido haciendo **[clic aquí para descargar el ZIP](https://github.com/pamelaFranco/Diplomado%20MRI%20-%20UNAB/archive/refs/heads/main.zip)** (o desde el botón verde **"Code" > "Download ZIP"** en la parte superior de esta página de GitHub).

---

## Contenido Académico

**1. Extracción de Características**

**Cuaderno:** [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/pamelaFranco/Diplomado-MRI-UNAB/blob/main/Codes/radiomics.ipynb)

En esta sección práctica se aborda cómo transformar una imagen médica cualitativa en datos cuantitativos de alto rendimiento:

* Carga de volúmenes médicos (formatos .nii / .nii.gz).

* Configuración del extractor PyRadiomics (normalización de intensidad, remuestreo/resampling).

* Obtención de características de textura (GLCM).

**2. Selección de Características y Modelado**

**Cuaderno:** [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/pamelaFranco/Diplomado-MRI-UNAB/blob/main/Codes/ML.ipynb)

En esta sección práctica se aborda cómo procesar la matriz de datos radiómicos para filtrar el ruido informático y construir un modelo predictivo:

* Normalización estadística de las variables mediante un escalamiento Z-score.

* Selección de las características más discriminantes usando un filtro ANOVA estadístico.

* Diagnóstico visual de la separación de clases en un plano 2D mediante el algoritmo no lineal t-SNE.

* Entrenamiento de un clasificador de regresión logística para diferenciar LGG de HGG, evaluado mediante una matriz de confusión.


**3. Interpretabilidad en la clasificación de Gliomas**

**Cuaderno:** [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/pamelaFranco/Diplomado-MRI-UNAB/blob/main/Codes/Glioma_classification.ipynb)

A través de este cuaderno se introduce a los alumnos en el flujo de modelado predictivo, destacando el uso de **Inteligencia Artificial Explicable (XAI)** en medicina para la interpretación biofísica de los resultados:

* **Preprocesamiento y Curación de Datos:** Preparación y normalización estadística de la base de datos radiómica, simulando la carga diagnóstica y asegurando la consistencia antes del modelado.
* **Entrenamiento del Clasificador:** Implementación de un algoritmo basado en **Random Forest** (Bosques Aleatorios), ideal para la toma de decisiones complejas a partir de múltiples variables de textura e intensidad extraídas.
* **Panel de Diagnóstico Médico Interactivo:** Diseño de una interfaz dinámica (mediante *widgets*) que simula un entorno clínico real. Permite seleccionar diferentes pacientes de estudio (ej. *Paciente46*) para contrastar el diagnóstico predictivo de la IA con la referencia histológica real, reportando un nivel de confianza probabilístico.
* **Explicabilidad Médica con Valores SHAP (SHapley Additive exPlanations):** El núcleo analítico del código utiliza teoría de juegos cooperativos para calcular la contribución exacta de cada característica radiómica en la predicción final. Esto permite realizar un **Análisis Biofísico** visualizando qué descriptores de textura o forma específicos inclinaron la balanza hacia un diagnóstico de "Grado 2" o mayor.
* **Sección Académica de Discusión Metodológica:** Para finalizar el laboratorio, se guía a los estudiantes a reflexionar críticamente sobre los desafíos técnicos que impiden el uso inmediato de un modelo en la clínica real:
  1. El problema del desbalance de datos en bases de datos biomédicas.
  2. El impacto de los procesos estocásticos y el control de semillas aleatorias (`random_state`) para la reproducibilidad científica.
  3. El rol de la **Nested Cross-Validation (Validación Anidada)** como el estándar de oro para eliminar el *sesgo de selección* en la optimización de parámetros.

---


## Información Institucional
* **Institución:** Universidad Andrés Bello (UNAB)

* **Programa:** Diplomado en Resonancia Magnética (MRI)

* **Propósito:** Material docente / Laboratorio práctico de uso académico.

--- 

## License

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)