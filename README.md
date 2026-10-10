# Comparación de modelos preentrenados de Hugging Face para análisis de sentimientos

## 1. Descripción del proyecto

Este proyecto compara tres modelos preentrenados de Hugging Face para clasificar el sentimiento de publicaciones de Twitter relacionadas con experiencias de clientes de aerolíneas. El análisis considera las categorías negativo, neutral y positivo.

El objetivo es evaluar el desempeño de los modelos mediante métricas de clasificación y tiempo de inferencia, para identificar sus ventajas y limitaciones.

## 2. Conjunto de datos

Se utiliza el conjunto de datos `Tweets.csv`, que contiene publicaciones relacionadas con aerolíneas y etiquetas de sentimiento. La distribución original presenta un predominio de comentarios negativos, por lo que se evalúan tanto los datos de prueba originales como un conjunto balanceado para complementar la comparación.

**Importante:** los datos corresponden al sector aeronáutico, no al sector bancario. Los resultados no representan una validación directa para clasificar reclamaciones bancarias.

## 3. Modelos evaluados

- `cardiffnlp/twitter-roberta-base-sentiment`
- `finiteautomata/bertweet-base-sentiment-analysis`
- `lxyuan/distilbert-base-multilingual-cased-sentiments-student`

Los modelos se utilizan en su versión preentrenada, sin ajuste fino (*fine-tuning*).

## 4. Metodología de evaluación

La comparación considera:

- Exactitud (*accuracy*).
- Precisión, exhaustividad (*recall*) y F1 por clase.
- F1 macro para comparar el desempeño entre las categorías.
- Tiempo promedio de inferencia y rendimiento de procesamiento.
- Evaluación con la distribución original y con datos balanceados.

## 5. Resultados principales

En las pruebas realizadas, BERTweet obtuvo el mejor F1 macro entre los tres modelos, tanto en el conjunto de prueba original como en el balanceado. Twitter-RoBERTa también mostró un desempeño competitivo, mientras que el modelo multilingüe DistilBERT presentó mayores dificultades para distinguir algunas categorías, especialmente la neutral.

Las métricas detalladas se encuentran en el reporte técnico y en los archivos de resultados.

## 6. Estructura del repositorio

- `notebooks/`: documentación relacionada con los notebooks.
- `results/`: archivos de resultados de la evaluación.
- `docs/`: reporte técnico del proyecto.
- `Comparacion_HuggingFace_Sentimientos_VF.ipynb`: notebook principal del análisis.

## 7. Reproducción del proyecto

1. Abrir el notebook principal en Google Colab.
2. Seleccionar un entorno con GPU cuando esté disponible.
3. Instalar o verificar las bibliotecas requeridas.
4. Obtener el conjunto de datos y colocarlo en la ruta indicada en el notebook.
5. Ejecutar las celdas en orden para reproducir las evaluaciones y generar los resultados.

Los resultados pueden variar según el entorno de ejecución, las versiones de las bibliotecas y la disponibilidad de recursos.

## 8. Limitaciones

El análisis utiliza publicaciones relacionadas con aerolíneas y modelos preentrenados, por lo que no garantiza el mismo desempeño en otros dominios. Para una aplicación en reclamaciones bancarias sería necesario evaluar datos del sector, revisar las etiquetas y validar el comportamiento de los modelos antes de utilizarlos en un proceso operativo.

## 9. Documentación

El reporte técnico incluye la metodología, las métricas, la comparación de resultados, las limitaciones y las conclusiones del experimento.
