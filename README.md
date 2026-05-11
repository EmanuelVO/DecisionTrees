# DecisionTrees

Problema:   Imagina que eres un investigador médico que recopila datos para un estudio. Has recopilado datos sobre un conjunto de pacientes, todos ellos con la misma enfermedad. Durante su tratamiento, cada paciente ha respondido a uno de los 5 medicamentos, el fármaco A, el fármaco B, el fármaco c, el fármaco X y el Y. 

Parte de tu trabajo consiste en construir un modelo para averiguar qué medicamento podría ser apropiado para un futuro paciente con la misma enfermedad. Los conjuntos de características de este conjunto de datos son la edad, el sexo, la presión arterial y el colesterol de los pacientes, y el objetivo es estudiar el fármaco al que respondió cada paciente. 

Se trata de un ejemplo de clasificación multiclase, y se puede utilizar la parte de entrenamiento del conjunto de datos para construir un árbol de decisión, y luego utilizarlo para predecir la clase de un paciente desconocido, o para prescribirlo a un nuevo paciente.

1. Cargue la base de datos “drugs.csv” en Python e investigue cómo convertir las variables predictoras cualitativas de esta base a una escala numérica mediante la instrucción “preprocessing.LabelEncoder()”. Por ejemplo, si una variable tiene 3 posibles categorías, deberá cambiar sus resultados a 0, 1 o 2.

Se transformaron las variables 'Sex', 'BP' y 'Cholesterol'.

2. Use el método de Árboles de decisión para generar un modelo predictivo para este problema. Pruebe con los dos criterios vistos en esta lección (Gini y Entropía) y diversos niveles de profundidad. En cada caso elabore un reporte de clasificación detallado. Interprete verbalmente sus indicadores y determine cuál es la mejor opción.

GINI
<img width="904" height="774" alt="image" src="https://github.com/user-attachments/assets/59abb499-9773-4101-854c-adc2434797b1" />

ENTROPY
<img width="877" height="773" alt="image" src="https://github.com/user-attachments/assets/a9252b52-4249-48cc-af32-075d4be047a0" />

El criterio Gini arroja un reporte de clasificación con las precisiones máximas y el criterio Entropy también cuando el max_depth es superior a 4. Por lo tanto, cualquiera de estos criterios son considerados buena opción.

3. Explique verbalmente las reglas del árbol propuesto al momento de pronosticar.

Para pronosticar utilizamos el criterio Gini. Por lo que las reglas son las siguientes: Si Na_to_K es inferior o igual a 14.829 se considera la siguiente variable BP, de lo contrario se pronostica Drug Y como el mejor medicamento. Si BP es inferior o igual a 0.5, se considera la variable Age, de lo contrario se considera si BP es inferior o igual a 1.5. Si Age es inferior o igual a 50.5 se pronostica Drug A como el mejor medicamento, en caso contrario se pronostica Drug B. Si BP es inferior o igual a 1.5 se considera la variable Cholesterol, de lo contrario se pronostica Drug X como el mejor medicamento.  Si Cholesterol es inferior o igual a 0.5 se pronostica Drug C como el mejor medicamento, en caso contrario se pronostica Drug X. 

4. ¿Qué medicamento recomendaría utilizar para un paciente con los siguientes datos?

<img width="460" height="86" alt="image" src="https://github.com/user-attachments/assets/efe07c59-1158-4d54-9066-dfa6860d7c78" />

Con estos datos, Drug Y se pronostica como el medicamento más apropiado. 
