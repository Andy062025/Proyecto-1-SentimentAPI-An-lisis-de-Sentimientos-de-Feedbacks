# Proyecto-1-SentimentAPI-Análisis-de-Sentimientos-de-Feedbacks
Repositorio para evidenciar los avances del proyecto
# Primer Avance - DataScience🔎

## Primera Versión de trabajo con la base de datos📊
Se eligio un **Dataset de Amazon con aproximadamente 210.000 registros o datos**. La base de datos cuenta con la cantidad de información adecuada para entrenar el modelo de predicción de sentimiento. Adicionalmente las columnas del dataset ya vienen organizadas con los datos de interés. Por ejemplo: **Estrellas** (*Calificación de los usuarios*) | **Longitud de caracterés de cada comentario** | **Cuerpo del comentario** (*Contenido del comentario*).
## 📁Desarrollo del proyecto
1. Se cargo el documento al ambiente de **Google Colab**
2. Se importaron las **librerias** que se van a utilizar en primera instancia. 
### Librerias
* Pandas
* Matplotlib
* Numpy

 3. Se guardo el dataset como un dataframe.
 4. Se Imprimienron los primeros 5 elementos del dataframe.
 ### Imagen 1
 ![Primeros 5 elementos del DataFrame.](https://github.com/Andy062025/Proyecto-1-SentimentAPI-An-lisis-de-Sentimientos-de-Feedbacks/blob/main/Imagen%201%20-%20Dataframe%205%20registros.png)

5. Visualización y extraccíon los datos de interés

- En este apartado se procedió a guardar la columna de **longitud de caracteres de cada comentario**. El propósito es para trabajar particularmente con esta columna y proceder a establecer un promedio de la longitud de caracterés de cada comentario **(151)**, tambien conocer cuáles eran los valores de caracterés mínimos **(16)** y máximos **(3086)**
### Imagen 2
![Tabla cantidad de caracteres.](https://github.com/Andy062025/Proyecto-1-SentimentAPI-An-lisis-de-Sentimientos-de-Feedbacks/blob/main/Imagen%202%20-%20Dataframe%20tabla%20cantidad%20de%20caracteres.png)

6. Función histograma
- Se realizo la función **histograma** el cual es un tipo de gráfico de barras que muestra la distribución de datos numéricos, agrupando valores intervalos Eje X,Y y mostrando la frecuencia de datos. En este caso la gráfica representará la variación de la longitud de los caracterés. 
### Imagen 3
![Primer histograma](https://github.com/Andy062025/Proyecto-1-SentimentAPI-An-lisis-de-Sentimientos-de-Feedbacks/blob/main/Imagen%203%20-%20Primer%20histograma.png)

- Adicionalmente se realizó un cálculo de la cantidad de comentarios con longitudes mayor a 500 caracterés. Lo que arrojo una respuesta **La cantidad de comentarios con longitud mayor a 500 es 2.44 %**.
- Se pudo evidenciar que la mayor cantidad de datos está distribuida mayormente hacia los comentarios que tienen **longitudes de menores de 250 caracteres** aproximadamente.

- Por lo anterior, se pudo llegar a una primera **conclusión:** A pesar de que hay comentarios que superan los 3.000 caracteres, se reflejo que estos comentarios tan extensos no son frecuentes y por tanto carecen de peso para el análisis. Esto quiere decir que el enfoque de segmentar o seleccionar los datos será principalmente hacia comentarios con una longitud menor de **500 caracterés** en los cuales se concentra la mayor cantidad y frecuencia de los mismos. 

7. Datos de interés
- Los datos están organizados según el **sentimento del comentario que se evalua por la cantidad de estrellas**. teniendo en cuenta esto, se realizó un análisis para observar como es la distribución de estos sentimientos y así seleccionar los datos más convenientes para la prueba.
    * 1. Se Seleccionaron datos con longitud menor de 500 caracteres por comentario.
    * 2. La función filtra el DataFrame df y selecciona únicamente las filas donde la columna 'stars' es igual a n = 1,2,3,4,5
    * 3. Finalmente se obtuvo la clasificación de cuantos comentarios menores de 500 caracteres habia por número de estrellas **(1-5)**
### Imagen 4
![DataFrame comentarios por estrellas.](https://github.com/Andy062025/Proyecto-1-SentimentAPI-An-lisis-de-Sentimientos-de-Feedbacks/blob/main/Imagen%204%20-%20Dataframe%20tabla%20cantidad%20de%20comentarios%20por%20estrellas.png)
- A continuación los datos obtenidos fueron guardados en el DataFrame de calificación por estrellas
     *  Número de⭐
         * 1⭐
         * 2⭐⭐
         * 3⭐⭐⭐
         * 4⭐⭐⭐⭐
         * 5⭐⭐⭐⭐⭐
           
![DataFrame guardado comentarios por estrellas.](https://github.com/Andy062025/Proyecto-1-SentimentAPI-An-lisis-de-Sentimientos-de-Feedbacks/blob/main/Imagen%205%20-%20Dataframe%20tabla%20por%20cantidad%20de%20estrellas.png)           

- Se crearon 5 gráficas de histogramas por cantidad de estrellas para comentarios de menos de 500 caracteres.
### Imagen 5
![Histograma 1 estrella.](https://github.com/Andy062025/Proyecto-1-SentimentAPI-An-lisis-de-Sentimientos-de-Feedbacks/blob/main/Imagen%206.%20-%20Histogramas%20variaci%C3%B3n%20de%20longitud%20de%20caracteres%201%20estrella.png)
![Histograma 2 estrella.](https://github.com/Andy062025/Proyecto-1-SentimentAPI-An-lisis-de-Sentimientos-de-Feedbacks/blob/main/Imagen%206.1%20-%20Histogramas%20variaci%C3%B3n%20de%20longitud%20de%20caracteres%202%20estrellas.png)
![Histograma 3 estrella.](https://github.com/Andy062025/Proyecto-1-SentimentAPI-An-lisis-de-Sentimientos-de-Feedbacks/blob/main/Imagen%206.2%20-%20Histogramas%20variaci%C3%B3n%20de%20longitud%20de%20caracteres%203%20estrellas.png)
![Histograma 4 estrella.](https://github.com/Andy062025/Proyecto-1-SentimentAPI-An-lisis-de-Sentimientos-de-Feedbacks/blob/main/Imagen%206.3%20-%20Histogramas%20variaci%C3%B3n%20de%20longitud%20de%20caracteres%204%20estrellas.png)
![Histograma 5 estrella.](https://github.com/Andy062025/Proyecto-1-SentimentAPI-An-lisis-de-Sentimientos-de-Feedbacks/blob/main/Imagen%206.4%20-%20Histogramas%20variaci%C3%B3n%20de%20longitud%20de%20caracteres%205%20estrellas.png)

- Como **conclusión** se evidenció que, aunque se redujo la cantidad de comentarios por su longitud, la **mayor cantidad de comentarios se agrupan entre los que tienen alrededor de 200 caracterés**.
- Por consiguiente se procedió filtrar la **cantidad de comentarios con longitud menor a 200 caracterés**
- El resultado arrojo la cifra de **155.512** que representa el **79.91%** de los datos. A partir de lo anterior se llegó a la **conclusión** Los datos que representan la mayor población son aquellos que tienen una **longitud menor a 200 caracterés**. Esto permite enfocarse en este intervalo de comentarios y lo que se propone, para probar o entrenar el modelo, es tomar aleatoriamente entre 500 y 1000 cometarios de cada subcontunjo, respecto a la cantidad de estrellas y así poder compararlos.
- A continuación se procedio a seleccionar datos con longitud menor de 200 caracterés por comentario y guardarlos en el DataFrame.
8. Selección aleatoria de los 5000 datos con longitud menor a 200.
- Se realiza una muestra (Sample) = Selecciona 1.000 filas aleatorias del DataFrame df_1Star. El muestreo es sin reemplazo por defecto.
- **random_state** fija la aleatoriedad. Permite repetir resultados exactamente. Esto es esencial para experimentos confiables y comparables.
No afecta la calidad del muestreo, solo su reproducibilidad.
- Se creó el DataFrame de selección aleatoría.
### Imagen 6
![DataFrame selección aleatoría.](https://github.com/Andy062025/Proyecto-1-SentimentAPI-An-lisis-de-Sentimientos-de-Feedbacks/blob/main/Imagen%207%20-%20Dataframe%20selecci%C3%B3n%20aleatotria.png)

- Para concluir con este apartado se **concatenarón o unieron los DataFrames** anteriores para tener una versión final.
### Imagen 7
![DataFrame Final.](https://github.com/Andy062025/Proyecto-1-SentimentAPI-An-lisis-de-Sentimientos-de-Feedbacks/blob/main/Imagen%208%20-%20Dataframe%20final.png)

- Apartir del DataFrame final se realizó un nuevo histograma, pero en este caso representando **la frecuencia en la longitud de los caracterés hasta 200**.
### Imagen 8 
![Histograma Final.](https://github.com/Andy062025/Proyecto-1-SentimentAPI-An-lisis-de-Sentimientos-de-Feedbacks/blob/main/Imagen%209%20-%20Histograma%20final.png)

 ## ▶️Siguientes acciones
 A partir de este **dataframe normalizado** Los miembros del equipo Data Science desarrollarán cada uno en un Colab de manera individual, un modelo de aprendizaje automático. En este caso lo más apropiado para el proyecto es un modelo de **aprendizaje supervisado** Lo anterior debido a que este tipo de modelo aprende apartir de datos etiquetados (*Ya sabemos la respuesta correcta*) 
 ### 🎯Modelos más adecuados
 **Regresión Logística**
 * Arboles de decisión
 * Random Forest
 * SVM (*Support vector machine*)
## 🛠️Herramientas utilizadas
* Entorno Google Colab
* Lenguaje Python
* **Bibliotecas** 
* Pandas: Procesamiento y análisis de datos.
* Numpy: Manipulación matemática.
* Matplotlib: Visualización de datos, gráficas.

---

9. ### **Modelo de Árbol de Decisión para Análisis de Sentimiento**

La implementación de un modelo de aprendizaje supervisado basado en Árbol de Decisión, diseñado para clasificar el sentimiento de comentarios cortos de clientes de Amazon en tres categorías:

✅ Positivo

➖ Neutro

❌ Negativo

---

10. ### **Objetivo del Proyecto con este modelo**

Implementar un Árbol de Decisión mejorado para análisis de sentimiento.

* Evitar sesgos extremos (todo positivo o todo negativo).
* Permitir la clasificación en tres clases.
* Facilitar una comparación justa con un modelo de Regresión Logística.

---

11. ### **Estructura del Dataset**
El dataset utilizado está en formato `.csv`y contiene aproximadamente **100 registros** con comentarios cortos (3 a 20 caracteres).

Columnas relevantes:

`review_body:` texto del comentario

`stars:` calificación del producto (1 a 5)

`lenght_review_body:` longitud del comentario

`sentiment:` sentimiento categorizado **(Positivo, Neutro, Negativo)**

---

12. ### **Enfoque del Modelo** 

Debido a las limitaciones del Árbol de Decisión para procesar texto corto, se implementó un **enfoque híbrido**:

* Preprocesamiento del texto
* Vectorización TF-IDF controlada
* Variable numérica adicional (longitud del texto)
* Configuración del Árbol con restricciones
* Capa léxica simple para mejorar coherencia

---

13. ### 🔧**Librerías Utilizadas para este modelo Árbol de decisión**

* pandas
* numpy
* scikit-learn
* scipy
* joblib
* re

---

14. ### **Configuración del Modelo**

**Vectorización del texto**
* TF-IDF con vocabulario limitado
* Solo unigramas
* Eliminación de palabras muy poco frecuentes

**Árbol de Decisión** 

Parámetros clave:

* `max_depth = 5`
* `min_samples_leaf = 5`
* `class_weight = 'balanced'`

Esto evita el sobreajuste y mejora la generalización del árbol.

---

15. ### **Evaluación del Modelo**
El modelo se evalúa usando:

* `Accuracy`

* `Precision`

* `Recall`

* `F1-Score`

Estas métricas permiten analizar el desempeño individual por clase, especialmente en escenarios con desbalance.

---

16. ### **Función de Predicción** 

El sistema cuenta con una función de inferencia que:

* Limpia el texto de entrada

* Aplica reglas léxicas simples

* Utiliza el Árbol de Decisión como respaldo

* Retorna :
    * Sentimiento predicho
    * Precisión global del modelo

**Ejemplo de salida:**

`Sentimiento (Árbol de Decisión): Positivo | Precisión del modelo: 0.52` 

---

17. ### 📌 Conclusión
**El Árbol de Decisión**

* Funciona correctamente para predecir las tres clases de sentimientos
* Presenta resultados coherentes tras los ajustes
* Evidencia las limitaciones del modelo frente a texto.

---

18. ### 📈 Modelo de Regresión Logística para Análisis de Sentimiento

Este repositorio contiene la implementación de un **modelo de aprendizaje supervisado** basado en **Regresión Logística**, orientado al **análisis de sentimiento** de comentarios cortos de clientes de Amazon.

El modelo clasifica los comentarios en tres categorías:

* ✅ Positivo
* ➖ Neutro
* ❌ Negativo

Este modelo se utiliza como **modelo principal** del proyecto, ya que presenta un mejor desempeño que el Árbol de Decisión al trabajar con texto.

---

## 🎯 Objetivo del Proyecto de este modelo

* Implementar un modelo de **Regresión Logística multiclase**.
* Clasificar comentarios cortos en sentimientos positivo, neutro y negativo.
* Obtener métricas estables y coherentes.
* Comparar su desempeño frente a un Árbol de Decisión.

---

##  Estructura del Dataset

El dataset utilizado se encuentra en formato `.csv` y contiene aproximadamente **100 registros**, con comentarios de entre **3 y 20 caracteres**.

Columnas relevantes:

* `review_body`: texto del comentario
* `stars`: calificación del producto (1 a 5)
* `lenght_review_body`: longitud del comentario
* `sentiment`: etiqueta de sentimiento (Positivo, Neutro, Negativo)

---

## Enfoque del Modelo

La Regresión Logística es un modelo **lineal**, lo que la hace especialmente adecuada para problemas de clasificación de texto. El enfoque utilizado incluye:

1. Limpieza y normalización del texto
2. Vectorización TF-IDF
3. Inclusión de una variable numérica (longitud del texto)
4. Entrenamiento con balanceo de clases
5. Decisión final basada en probabilidades

---

## 🔧 Librerías Utilizadas

```python
pandas
numpy
scikit-learn
scipy
joblib
re
```

---

## Configuración del Modelo

### Vectorización del texto

* TF-IDF con unigramas y bigramas
* Vocabulario más amplio que el Árbol de Decisión
* Eliminación de ruido léxico

### Regresión Logística

Parámetros clave:

* `max_iter = 1000`
* `class_weight = 'balanced'`
* `solver = 'liblinear'` o `lbfgs`

Esta configuración permite una **mejor generalización semántica**.

---

## Evaluación del Modelo

El modelo se evalúa utilizando:

* Accuracy
* Precision
* Recall
* F1-Score

La métrica **F1-Score** es especialmente relevante debido al desbalance entre clases y al tamaño reducido del dataset.

---

## Función de Predicción

El sistema cuenta con una función de inferencia que:

* Valida la entrada del usuario
* Limpia y transforma el texto
* Aplica reglas léxicas básicas
* Usa la Regresión Logística para la predicción final

Salida esperada:

```
Sentimiento: Positivo | Precisión del modelo: 0.58
```

---

## Serialización del Modelo

El modelo fue serializado utilizando `joblib`, almacenando:

* Modelo entrenado
* Vectorizador TF-IDF
* Métrica de precisión

Esto permite reutilizar el modelo sin reentrenamiento.

---

## ✅ Ventajas del Modelo

* Mejor desempeño en texto corto
* Mayor estabilidad en las predicciones
* Capacidad de generalizar palabras similares
* Predicción consistente de las tres clases

---


## 📌 Conclusión

La Regresión Logística demostró ser el modelo más adecuado para el análisis de sentimiento en este proyecto, superando al Árbol de Decisión en términos de estabilidad, coherencia y métricas de desempeño.

Por esta razón, se selecciona como **modelo principal**, mientras que el Árbol de Decisión se utiliza como referencia comparativa.
