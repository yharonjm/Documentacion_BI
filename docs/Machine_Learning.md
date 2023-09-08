# <span style="color: #00A1DD">Arquitectura de Machine Learning</span>
<hr style="border-color: #00A1DD;">
En la siguiente imagen se observa una representación gráfica de la arquitectura propuesta para la aplicación de Machine Learning sobre los datos de Seguridad ciudadana:

![Arquitectura](images\ARQ_V1.png "ML_Arquitectura")

## <span style="border-bottom: 1px solid; border-bottom-color: #00A1DD; color: #00A1DD">Análisis de Datos</span>
Los primeros dies registros del dataset para cada una de los atributos se muestran como muestra de ejemplo en la siguiente imagen:

![Arquitectura](images\head_data.png "ML_Arquitectura")

Se debe anexar que cada uno de los atributos llegan con la característica de ser datos tipo object y que se debe realizar una transformación para el consumo por parte del modelo.

![Arquitectura](images\data_type.png "ML_Arquitectura")

Es importante también definir con que columnas se realizara el entrenamiento, por lo que se llevara a cabo entrenamientos considerando solo los atributos más relevantes, en este caso son todos los correspondientes a datos de fechas y el atributo mas importante comuna.
La primera gráfica analítica de estos datos que se obtuvo fue la siguiente:

[![Analítica](images\d1.png "Analítica_1")](images\d1.png "Analítica_1")

Donde se observa el alto desbalanceo de las clases para el atributo comuna.
Dentro de una Jupyter-Notebook utilizando el servicio de AWS-Athena por medio de la librería _boto3_ de Python (<img src="https://raw.githubusercontent.com/FortAwesome/Font-Awesome/0698449d50f2b95517562295a59d414afc68b369/svgs/brands/python.svg" width="15" height="15">) se realiza la consulta de datos y una primera limpieza donde solo se consideraran las comunas con números de registros considerables para realizar un buen entrenamiento sobre algún modelo de Machine Learning:

![Consulta](images\consulta.png "Consulta")

Esto lleva a que en dicho entrenamiento se consideren solo las siguientes clases esperando que el problema del desbalanceo no sea tan influyente:

![Analítica](images\d2.png "Analítica_2")

## <span style="border-bottom: 1px solid; border-bottom-color: #00A1DD; color: #00A1DD">Primera etapa de ML</span>
Como primer objetivo se sugiere encontrar un modelo con el cual a partir de la data de seguridad ciudadana correspondiente a hurtos lograr predecir la comuna más probable donde se llevara a cabo futuros hechos delictivos de manera mas precisa que con la analítica del histórico de registros. Este modelo en primer lugar se entrenara teniendo en cuenta los campos **categóricos** del dataset correspondientes a: _fecha_del_hecho_, _dia_de_la_semana_, _hora_del_hecho_, y _comuna_.

Posteriormente se lleva a cabo una codificación de datos incorporando las herramientas que ofrece la librería de M.L de Python conocida como _Scikit-Learn_ esto con el fin de ingresar datos funcionales al respectivo modelo. 

![Codificación](images\cod1.png "cod_1"){width=800}

El modelo en que se ejecuto el primer entrenamiento con datos naturales se denomina un clasificador por vecinos cercanos ```KNeighborsClassifier```, un modelo reconocido en problemas de clasificación de datos de tipo categóricos los cuales se están usando en este caso:

![Codificación](images\cod2.png "cod_2"){width=800}

Luego del entrenamiento, la búsqueda de los mejores hiperparámetros y el test del modelo sobre un porcentaje del mismo dataset se llego al siguientes resultados:

<span style="color: #00A1DD">1.</span> Exactitud del modelo (Accuracy):

![Accuracy](images\cod3.png "Accuracy"){width=500}

Para encontrar el mejor modelo e hiperparámetros con datos naturales se automatizo esta búsqueda y se llego al siguiente resultado:  

![Accuracy](images\cod4.png "Accuracy"){width=800}
![Accuracy](images\cod5.png "Accuracy"){width=800}
## <span style="border-bottom: 1px solid; border-bottom-color: #00A1DD; color: #00A1DD">Conclusiones</span>
<span style="color: #00A1DD">-</span> Un problema que se encontró fue la correlación de datos, prácticamente no existe esta característica en estos datos, como se muestra en el mapa de calor:

![Treemap](images\cod6.png "Treemap"){width=800}

Por lo que es necesario el diseño de nuevas categorías para mejor este echo e indagar si esto mejora el entrenamiento del modelo en este caso.

<span style="color: #00A1DD">-</span> El objetivo después de mejorar el factor de eficiencia es desplegar basándose en la arquitectura planteada una serie de tiempo predictiva, sin embargo este no es un hecho definitivo pues el paso anterior podría provocar un replanteamiento de esta acción.

[![Timeserie](images\newplot.png "Timeserie"){width=800}](images\newplot.png "Timeserie")