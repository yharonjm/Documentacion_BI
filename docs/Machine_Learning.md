# <span style="color: #00A1DD">Arquitectura de Machine Learning</span>
---
En la siguiente imagen se observa una representación gráfica de la arquitectura propuesta para la aplicación de Machine Learning sobre los datos de Seguridad ciudadana:

![Arquitectura](images\ArqML.png "ML_Arquitectura")

## <span style="color: #00A1DD">Primer avance</span>
Como primer objetivo se sugiere encontrar un modelo con el cual a partir de la data de seguridad ciudadana correspondiente a hurtos lograr predecir la comuna más probable donde se llevara a cabo futuros hechos delictivos de manera mas precisa que con la analítica del histórico de registros. Este modelo en primer lugar se entrenara teniendo en cuenta los campos **categóricos** del dataset correspondientes al dia de la semana del hecho y su respectiva hora.


Dentro de una Jupyter-Notebook utilizando el servicio de AWS-Athena por medio de la librería _boto3_ de Python (<img src="https://raw.githubusercontent.com/FortAwesome/Font-Awesome/0698449d50f2b95517562295a59d414afc68b369/svgs/brands/python.svg" width="15" height="15">) se realiza la consulta de datos y una primera limpieza donde solo se consideraran las comunas con números de registros considerables para realizar un buen entrenamiento a algún modelo de Machine Learning:

![Consulta](images\consulta.png "Consulta")

Posteriormente se lleva a cabo una codificación de datos incorporando las herramientas que ofrece la librería de M.L de Python conocida como _Scikit-Learn_ esto con el fin de ingresar datos funcionales al respectivo modelo. El primer modelo que se considero se denomina un clasificador por árbol de decision ```DecisionTreeClassifier()```, un modelo simple y reconocido en problemas de clasificación de datos de tipo categóricos los cuales se están usando en este caso.

Luego del entrenamiento, la búsqueda de los mejores hiperparámetros y el test del modelo sobre un porcentaje del mismo dataset se llegaron a los siguientes resultados:

<span style="color: #00A1DD">1.</span> Hiperparámetros y Exactitud del modelo (Accuracy):

![Accuracy](images\accuracy.png "Accuracy")

<span style="color: #00A1DD">2.</span> Matriz de confusión:

![Matriz](images\mc.png "Matriz"){width=800}

<span style="color: #00A1DD">3.</span> Conteo de predicciones (gráfico):

![Conteo](images\conteo.png "Conteo"){width=800}

## <span style="color: #00A1DD">Primeras conclusiones</span>
Como la limpieza de los datos y la búsqueda de hiperparámetros no esta incrementando el accuracy del modelo se optara por abordar las siguientes alternativas:

<span style="color: #00A1DD">-</span> Entrenar modelos mas avanzados para datos categóricos, esperando encontrar una exactitud mayor de manera no forzada.

<span style="color: #00A1DD">-</span> Si la acción previa no genera resultados satisfactorios se procederá a realizar análisis sobre el dataset en si, y abordar posibles mejoras sobre el muestreo de clases.