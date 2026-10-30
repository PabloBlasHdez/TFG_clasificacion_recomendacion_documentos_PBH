# Clasificación automática de documentos textuales con IA

Trabajo Fin de Grado · Grado en Gestión de la Información y Contenidos Digitales · Universidad Carlos III de Madrid (curso 2024-2025)

**Autor:** Pablo Blas Hernández

## Descripción

Este repositorio contiene el código del TFG *“El uso de la IA en clasificación automática de documentos textuales”*. El trabajo compara varias técnicas de Procesamiento del Lenguaje Natural y aprendizaje automático no supervisado para agrupar un corpus de 50 documentos en PDF según su temática, y evalúa cuál da los resultados más coherentes. Además, incluye un prototipo de sistema de recomendación que sugiere al usuario documentos relevantes a partir de sus intereses.

## Qué incluye

- **Preprocesamiento:** extracción del texto de los PDF, limpieza, eliminación de *stopwords* y tokenización.
- **Modelos de clasificación (clustering):**
  - K-means con TF-IDF
  - K-means con TF-IDF + LSA
  - DBSCAN
  - GMM (Gaussian Mixture Models)
  - Word Embeddings + PCA + K-means
  - LDA (modelado de tópicos)
- **Sistema de recomendación:** recomendación basada en contenido (TF-IDF + LSA + similitud del coseno), con perfil del usuario por palabras clave o por documentos de interés.
- **Evaluación:** índice de Silhouette, visualizaciones en 2D y análisis de la coherencia temática de los grupos.

## Resultados principales

- La combinación de **K-means con reducción de dimensionalidad mediante LSA** fue la que mejor coherencia temática y segmentación ofreció.
- **LDA** no agrupa los documentos en clústeres tradicionales, pero aporta una visión útil de los tópicos dominantes y su distribución en cada texto.
- **DBSCAN** fue el menos eficaz en este corpus, y **GMM** y **Word Embeddings + PCA + K-means** dieron resultados aceptables pero menos interpretables.

## Estructura del repositorio

Se recomienda organizar el código de los anexos así:

```
├── 01_preprocesamiento.m          # Anexo A
├── 02_kmeans_tfidf.m              # Anexo B
├── 03_kmeans_lsa.m                # Anexo C
├── ...                            # Resto de modelos (DBSCAN, GMM, embeddings, LDA)
├── 09_sistema_recomendacion.m     # Anexo I
├── memoria/
│   └── TFG_PabloBlas.pdf
└── README.md
```

## Requisitos

- MATLAB (versión reciente)
- Text Analytics Toolbox
- Statistics and Machine Learning Toolbox

## Cómo ejecutarlo

1. Coloca los documentos PDF en una carpeta de trabajo.
2. Ejecuta primero el script de preprocesamiento (Anexo A), que genera el archivo `processedDocuments.mat`.
3. Ejecuta el script del modelo que quieras probar.
4. Para el sistema de recomendación, ejecuta `09_sistema_recomendacion.m`: se abrirá una ventana para elegir entre indicar palabras clave o seleccionar documentos que te hayan interesado.

> **Importante:** los scripts usan rutas absolutas de Windows (por ejemplo `C:\processedDocuments.mat` y `C:\docstfg\processed\`). Modifícalas para que apunten a tus carpetas antes de ejecutarlos.

## Memoria del TFG

La memoria completa con el marco teórico, la revisión de la literatura, el caso práctico y las conclusiones está en la carpeta `memoria/`.

## Licencia

La memoria se distribuye bajo licencia Creative Commons Reconocimiento – No Comercial – Sin Obra Derivada (CC BY-NC-ND). Para el código se puede añadir una licencia aparte, por ejemplo MIT.
