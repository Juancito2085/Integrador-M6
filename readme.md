# Proyecto Integrador Machine Learning

<p align="justify">
En este proyecto integrador se pone en práctica todo lo aprendido en el Módulo 6 realizando un EDA (Análisis exploratorio de datos), procesamiento de datos para poder realizar un entrenamiento supervisado de un modelo de ML (Machine Learning) y optimizarlo en base a las métricas obtenidas del mismo. En este Readme podemos encontrar un resumen de lo realizado en los notebooks.
</p>

## Introducción
<p align="justify">
En este trabajo el objetivo era analizar datos de vehículos donde además de las características técnicas también se contaba con el valor del mismo.
El objetivo aquí es entrenar un modelo para poder predecir el precio mediante los datos que tenemos disponibles, por lo tanto nos encontramos ante un problema de regresión, es decir, predecir un valor númerico a partir de diferentes datos.
Luego debemos entrenar otro modelo que clasifique si el auto es de gama baja o alta, para esto se etiquetan los vehículos que tenemos disponibles basandonos en la mediana de precios. Este es un problema de clasificación donde a partir de datos debemos entrenar el modelo para predecir la categoría a la que pertenece.
</p>

## Procedimiento
<p align="justify">
1) Primero se realiza un análisi exploratorio de los datos que se encuentras en el archivo <strong>ML_cars.csv</strong>. En esta etapa se verifica que no hay valores faltantes ni valores atípicos pero si tenemos varios datos con diferentes tipos de distribuciones. Esto se analiza mediante <strong>seaborn<7strong> principalmente debido a su practicidad.
</p>
<p align="justify">
2) Luego se procede a la transformación de datos para que los modelos de machine learning puedan utilizarlos. En esta etapa se utiliza principalmente el método de pandas <strong>get.dummies()</strong> que lo que hace es crear columnas para las diferentes categorias de las variables cualitativas y por decirlo de una manera simple codificarlas.
</p>
<p align="justify">
3) Con los datos filtrados se analiza la correlación lineal entre el precio y las demás características del vehículo. Se considera un valor de correlación lineal mayor a 0.8 o -0.8 como una correlación fuerte, por lo que las variables con valores de correlación por debajo de ese umbral no son consideradas.
</p>
<p align="justify">
4) Se crea un dataframe para a partir de las variables con correlación lineal fuerte, el precio y se crea una columna donde se clasifica cada vehículo en gama alta o baja, siendo esta división efectuada con respecto a la mediana del precio.
</p>
<p align="justify">
5) Luego se comienza con el entrenamiento del modelo de regresión probando varios modelos para comparar métricas. Principalmente la métrica R2 y no solo comparando entre modelos sino también dentro del modelo para comparar este valor entre los datos de prueba y los datos de entrenamiento para verificar si el modelo esta sobreentrenado. Una vez elegido el modelo se procede a hacer una optimización de hiperparámetros para encontrar el correcto.
</p>
<p align="justify">
6) Finalmente se llega a la conclusión de que el mejor modelo en este caso es una <em>Regresión lineal de Ridge</em> con parámetro <em>Alpha=0.7.</em>
</p>
<p align="justify">
7) Luego se comienza con el proceso de entrenamiento del modelo de clasificación donde si bien estos modelos son diferentes a los anteriores la manera de trabajar es prácticamente la misma. La diferencia radica en las métricas en la que nos basamos para la selección del mismo.
</p>
<p align="justify">
8) Una vez que se han evaluado una cantidad de modelos se selecciona el mejor, basado en la métrica <em>Accuracy</em> haciendo hincapié en la diferencia qu se produce entre los datos de entrenamiento y los de prueba para que el modelo tenga una capacidad de generalización importante.
c
<p align="justify">
9) Se procede luego a una optimización de hiperparámetros basado en busqueda de grilla de diferentes valores de los mismos. En este caso elegimos el modelo <em>SVM</em>.
</p>
<p align="justify">
10) El modelo <em>SVM</em> queda en este caso con los parametros <em>C=0.1</em>, <em>gamma=0.0001</em> y <em>kernel=rbf</em>.
</p>