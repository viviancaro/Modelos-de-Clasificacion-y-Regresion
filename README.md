# MODELOS DE CLASIFICACIÓN Y REGRESIÓN
El objetivo de este proyecto, es realizar una clasificación de comentarios de acuerdo al sentimiento positivo o negativo expresado en ellos. El análisis se realiza en un conjunto de datos sobre reviews de películas y se trabaja con procesamiento de texto para luego aplicar diferentes técnicas predictivas. 
En este caso no se utiliza un archivo '.csv', sino con un directorio estructurado.

El procedimiento que se realiza en este proyecto es:
-	Carga de las opiniones con la función ‘load_files’ de Sickit-learn que permite recorrer este tipo de estructuras para poder comenzar a procesarlas.
-	Creación de DataFrame con Pandas.
-	División del dataset en conjunto de entrenamiento, para el cual será utilizado el 80% de los datos y conjunto de testeo con el restante 20%.
-	Pre procesamiento de datos para la conversión del texto a una representación numérica, capaz de ser interpretada por los algoritmos de clasificación. Se realiza tokenización del texto, conversión a vectores de términos/documentos y aplicación de la herramienta tf_idf de TfidfVectorizer de la biblioteca Scikit-learn.
-	Observación de la matriz creada.
### Entrenamiento de modelos
A partir de la matriz creada con los vectores, se inicia con el proceso de entrenamiento de los algoritmos. Se utiliza GridSearchCV recorriendo una lista de parámetros según cada algoritmo. También se usan 5-fold CV y el área bajo la curva Roc como scoring. 

Se entrenan y comparan los siguientes modelos:

**1.**	Support Vector Machines (SVM)

**2.**	Multilayer Perceptron

**3.**	Random Forest

**4.**	AdaBoost

**5.**	Voting

Para cada modelo se realiza el proceso enumerado a continuación:
-	Se utiliza el GridSearchCV y el clasificador correspondiente con los parámetros específicos.
-	Se muestran los resultados promediados para cada combinación de parámetros.
-	Se encuentra la mejor combinación de parámetros y se guarda el resultado en una variable.
-	Se visualiza el resultado de cada clasificador en una matriz de confusión creada a partir de una función utilizando 'matplotlib'. Se observa la matriz normalizada y no normalizada.

### Comparación y Prueba
- Por último, se arma un ensamble entre los modelos y se mide el accuracy de cada uno.
-	Se elige el modelo con el mejor score y se entrena de nuevo con todos los datos del conjunto 'train'.
-	Se prueba el modelo optimizado en el entrenamiento sobre otro conjunto de datos y se observan los resultados.
