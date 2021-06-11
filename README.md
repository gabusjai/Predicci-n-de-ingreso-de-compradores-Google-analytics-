# Prediccion de ingreso de compradores Google analytics
 Especialización en analítica y ciencia de datos
 
 # Marco experimental

Para lograr los objetivos propuestos se analiza un conjunto de datos otorgado por Kaggle en un periodo de tiempo del 01 de
agosto de 2016 al 15 de octubre de 2018 y se busca predecir los ingresos
generados entre el 01 de diciembre de 2018 y el 31 de enero de 2019. Con el fin de brindar un mejor uso
a los presupuestos de marketing que permita el enfoque en sus campañas y posteriormente
mejorar las ventas en la tienda. 

Según la fuente de datos presentada, en este trabajo se pretende mediante dos
experimentos evaluar el desempeño del entrenamiento de los modelos, esto se
realiza mediante la agrupación de los datos de entrenamiento y validación; es
importante resaltar que los datos de la competencia “test.csv” no cuentan con
la columna “transactionRevenue”, por esto, se decide descartar estos datos que
fueron suministrados en la competencia. Esta 
variable es el objetivo a predecir en la competición, donde, para cada
usuario, tenemos que averiguar el total de todas las transacciones durante el
período de prueba.



Con el fin de realizar una buena predicción de los ingresos de los usuarios en la tienda,
se plantean dos experimentos, el primero consiste en evaluar todos los
registros del dataset, cuyo propósito es medir la respuesta del aprendizaje
frente al comportamiento de los usuarios según la secuencia temporal en la cual
se presentaron los registros, y lograr predecir futuros comportamientos. La
estrategia planteada es similar a la usada en series de tiempo pero con
segmentación no acomulada, es decir, se seleccionaron tres grupos temporales
independientes uno del otro, de igual manera se separó un cuarto grupo de
prueba para la predicción.  Es importante
aclarar que no existe una librería capaz de realizar este proceso tal y como se
describe, asi que se diseña una estrategia manual para la ejecución de este
experimento.



El segundo experimento está enfocado en generar un aprendizaje dado el comportamiento de
cada usuario, el objetivo es evaluar la respuesta de aprendizaje dada según la
huella única digital que genera un usuario en la plataforma. En este se decide
tomar la variable “fullVisitorId” , dado que es el registro digital que permite
reconocer a cada usuario. En este caso se hace la división con una función
llamada GroupKFold (Scikit-Learn,s. f.) que permite agrupar los datos según los requerimientos establecidos
previamente para este caso. 


Para la búsqueda de los mejores hiperparametros del modelo con los algoritmos de
árboles de decisión, se opta por variar el número de ramas entre 20 - 100 con
un paso de 10 , y la profundidad entre 3 - 21 con un paso de 3. Mientras que en
el aprendizaje con redes neuronales se selecciona  como hiperparametros el número de neuronas
que varían entre 64 - 1024, con un paso de múltiplos pares, y el parámetro de
regularización entre 0,1 - 0,5, con un paso de 0,1. 
