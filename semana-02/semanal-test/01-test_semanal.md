# 🎓 SIMULACRO EXAMEN AI-900 - SEMANA 2

## Preguntas Estilo Microsoft (Aleatorias)

**Instrucciones:**

- 40 preguntas tipo examen real Microsoft AI-900
- Tiempo sugerido: 60 minutos (1.5 min por pregunta)
- Anota tus respuestas en tu cuaderno
- NO mires las respuestas hasta terminar todas
- Algunas preguntas están relacionadas consecutivamente (como en el examen real)
- Mezcla de toda la Semana 2: ML tipos, regresión, clasificación, Azure ML, AutoML

**Formato de anotación sugerido:**

```
1. B
2. C
3. A
...
```

---

## 📝 PREGUNTAS (Respuestas al final)

### Pregunta 1

You need to predict whether a bank transaction is fraudulent based on historical transaction data with known outcomes. Which type of machine learning should you use?

A) Unsupervised learning  
B) Supervised learning  
C) Reinforcement learning  
D) Semi-supervised learning

---

### Pregunta 2

You are building a model to predict house prices. After training, your model has the following metrics:

- RMSE: $45,000
- MAE: $32,000
- R²: 0.82

What does the R² value of 0.82 indicate?

A) The model has 82% accuracy  
B) The model explains 82% of the variance in house prices  
C) The model has an error of 18%  
D) 82% of predictions are within $45,000 of the actual value

---

### Pregunta 3

Which of the following scenarios is best suited for unsupervised learning?

A) Predicting customer churn based on historical data  
B) Grouping customers into segments based on purchasing behavior  
C) Classifying emails as spam or not spam  
D) Predicting stock prices based on historical trends

---

### Pregunta 4

You are evaluating a classification model with the following confusion matrix:

```
                Predicted
            Negative  Positive
Actual  Neg    850      50
        Pos     30      70
```

What is the Recall of this model?

A) 70%  
B) 58%  
C) 85%  
D) 92%

---

### Pregunta 5

In Azure Machine Learning, what is the purpose of a Datastore?

A) To store trained models  
B) To provide a reference to Azure storage services where data is kept  
C) To execute training jobs  
D) To deploy models to production

---

### Pregunta 6 (relacionada con 4)

Based on the confusion matrix in Question 4, what is the Precision of the model?

A) 70%  
B) 58%  
C) 85%  
D) 92%

---

### Pregunta 7

You need to train multiple machine learning models in parallel using different algorithms. Which Azure Machine Learning compute resource should you use?

A) Compute Instance  
B) Compute Cluster  
C) Inference Cluster  
D) Local computer

---

### Pregunta 8

Which metric penalizes large prediction errors more severely than small errors?

A) MAE (Mean Absolute Error)  
B) R² (R-squared)  
C) RMSE (Root Mean Squared Error)  
D) MAPE (Mean Absolute Percentage Error)

---

### Pregunta 9

You are building a spam email detector. Your primary concern is ensuring that legitimate emails are not marked as spam. Which metric should you prioritize?

A) Accuracy  
B) Precision  
C) Recall  
D) F1 Score

---

### Pregunta 10

In reinforcement learning, what does an agent receive after taking an action?

A) A labeled dataset  
B) A reward or penalty  
C) A confusion matrix  
D) Feature importance scores

---

### Pregunta 11

You configure an Automated ML experiment with the following settings:

- Task: Classification
- Primary metric: AUC_weighted
- Training job time: 1 hour
- Metric score threshold: 0.90

When will the experiment stop?

A) Only after exactly 1 hour  
B) Only when AUC reaches 0.90  
C) After 1 hour OR when AUC reaches 0.90, whichever comes first  
D) After trying all possible algorithms

---

### Pregunta 12

What does a False Negative represent in a binary classification model?

A) The model predicted positive, but the actual value was negative  
B) The model predicted negative, but the actual value was positive  
C) The model predicted positive and the actual value was positive  
D) The model predicted negative and the actual value was negative

---

### Pregunta 13

You are training a regression model to predict customer lifetime value. Your model achieves:

- R² = 0.45
- RMSE = $8,500

What does the R² value suggest about your model?

A) The model is excellent  
B) The model explains less than half of the variance and needs improvement  
C) The model has 45% accuracy  
D) The model is overfitted

---

### Pregunta 14

In Azure Automated ML, what is "featurization"?

A) The process of selecting the best algorithm  
B) The automatic transformation of raw data into features useful for machine learning  
C) The deployment of a trained model  
D) The process of splitting data into training and testing sets

---

### Pregunta 15

Which type of machine learning would you use to train a robot to navigate a maze through trial and error?

A) Supervised learning  
B) Unsupervised learning  
C) Reinforcement learning  
D) Transfer learning

---

### Pregunta 16

You are building a medical diagnosis system to detect a rare disease. The disease affects only 2% of the population. Your model achieves 98% accuracy. Is this a good model?

A) Yes, 98% accuracy indicates an excellent model  
B) No, the model might just be predicting "no disease" for everyone  
C) Yes, accuracy is the most important metric in medicine  
D) No, you should use RMSE instead

---

### Pregunta 17

What is the difference between a Datastore and a Dataset in Azure ML?

A) There is no difference; they are the same thing  
B) Datastore is a connection to storage; Dataset is a specific version of data  
C) Datastore is for structured data; Dataset is for unstructured data  
D) Datastore is for training; Dataset is for inference

---

### Pregunta 18

In AutoML, what is an "ensemble model"?

A) The first model that AutoML trains  
B) A model that combines predictions from multiple models  
C) A model that uses only one algorithm  
D) A model specifically for time series data

---

### Pregunta 19

You need to create machine learning pipelines visually without writing code in Azure ML. Which tool should you use?

A) Jupyter Notebooks  
B) Azure ML Designer  
C) Visual Studio Code  
D) Azure Portal

---

### Pregunta 20

Which of the following is an example of supervised learning?

A) Grouping similar products together  
B) Detecting unusual patterns in network traffic  
C) Predicting temperature based on historical weather data  
D) A chess AI learning by playing against itself

---

### Pregunta 21

Your classification model has:

- Precision: 85%
- Recall: 45%

What does this indicate?

A) The model is excellent  
B) The model is very confident when it predicts positive, but misses many positive cases  
C) The model has high false positive rate  
D) The model should be used in production immediately

---

### Pregunta 22

What does the AUC (Area Under the ROC Curve) measure?

A) The accuracy of the model  
B) The model's ability to discriminate between positive and negative classes  
C) The training time of the model  
D) The amount of memory used by the model

---

### Pregunta 23

In Azure Machine Learning, what is an Experiment?

A) A type of machine learning algorithm  
B) A logical container for grouping related training runs  
C) A cloud service for data storage  
D) A type of virtual machine

---

### Pregunta 24

You are predicting apartment rental prices. Which type of machine learning task is this?

A) Classification  
B) Regression  
C) Clustering  
D) Anomaly detection

---

### Pregunta 25

What does "early stopping" do in an AutoML experiment?

A) Stops immediately when the experiment starts  
B) Stops training if no improvement is seen after several iterations  
C) Stops after training exactly one model  
D) Stops only when all algorithms have been tested

---

### Pregunta 26

An AutoML experiment completes with VotingEnsemble as the best model with AUC = 0.87. What does this suggest?

A) The model is poor and should not be used  
B) The model has good discriminative ability  
C) The model is overfitted  
D) The model only works on training data

---

### Pregunta 27 (scenario starts)

You work for a bank and need to detect fraudulent credit card transactions. Your model has the following metrics:

- Accuracy: 96%
- Precision: 60%
- Recall: 85%
- F1 Score: 70%

Fraud represents only 1% of all transactions.

What is your primary concern about this model?

A) Recall is too high  
B) Accuracy is too low  
C) Precision is relatively low, meaning many legitimate transactions will be flagged  
D) F1 Score indicates the model is useless

---

### Pregunta 28 (scenario continues)

Given the scenario in Question 27, which metric should you prioritize for this fraud detection system?

A) Accuracy  
B) Precision  
C) Recall  
D) Specificity

---

### Pregunta 29

What is the difference between classification and regression?

A) Classification predicts continuous values; regression predicts categories  
B) Classification predicts categories; regression predicts continuous values  
C) There is no difference  
D) Classification is unsupervised; regression is supervised

---

### Pregunta 30

In Azure ML, what is the purpose of the Model Registry?

A) To register new users  
B) To store and version trained models centrally  
C) To register new datasets  
D) To manage compute resources

---

### Pregunta 31

You are building a movie recommendation system. You want to group users with similar viewing preferences. Which type of machine learning should you use?

A) Supervised learning - Classification  
B) Supervised learning - Regression  
C) Unsupervised learning - Clustering  
D) Reinforcement learning

---

### Pregunta 32

Your regression model has RMSE = $50,000 when predicting house prices that range from $200,000 to $800,000. Is this acceptable?

A) No, RMSE should always be zero  
B) Yes, RMSE of $50,000 is reasonable for this price range  
C) No, RMSE is too high  
D) Cannot determine without knowing R²

---

### Pregunta 33

What does an AUC of 0.5 indicate?

A) Perfect model  
B) Excellent model  
C) Model performs no better than random guessing  
D) Model is slightly better than random

---

### Pregunta 34

In AutoML, you set "blocked_algorithms" to exclude XGBoost and LightGBM. What will happen?

A) Only XGBoost and LightGBM will be tested  
B) All algorithms except XGBoost and LightGBM will be tested  
C) The experiment will fail  
D) No algorithms will be tested

---

### Pregunta 35

Which Azure ML compute resource should you use for interactive development and testing with Jupyter notebooks?

A) Compute Cluster  
B) Compute Instance  
C) Inference Cluster  
D) Azure Kubernetes Service

---

### Pregunta 36

You need to predict whether customers will churn (leave) or stay. Historical data includes customers who left and customers who stayed. Which type of machine learning is this?

A) Unsupervised learning  
B) Supervised learning - Regression  
C) Supervised learning - Classification  
D) Reinforcement learning

---

### Pregunta 37

What is F1 Score?

A) The first model trained in AutoML  
B) The harmonic mean of Precision and Recall  
C) The same as Accuracy  
D) A metric only for regression

---

### Pregunta 38

In AutoML, what does the "primary metric" determine?

A) The type of task (classification or regression)  
B) Which model AutoML will select as the best  
C) The training time  
D) The size of the dataset

---

### Pregunta 39

You have trained a model with R² = -0.15. What does this indicate?

A) The model explains 15% of variance  
B) There is a calculation error; R² cannot be negative  
C) The model is worse than simply predicting the mean  
D) The model is excellent

---

### Pregunta 40

Your cancer detection model has:

- Precision: 70%
- Recall: 95%

What does the high Recall indicate?

A) The model misses very few actual cancer cases  
B) The model has many false positives  
C) Both A and B  
D) The model should not be used

---

## ⏸️ PAUSA - No continúes hasta terminar

**¿Terminaste las 40 preguntas?**

Si SÍ → Continúa para ver las respuestas  
Si NO → No hagas scroll todavía

---

# 📊 RESPUESTAS Y EXPLICACIONES

---

## Respuesta 1: B) Supervised learning

**Explicación:**  
Tienes datos históricos con resultados conocidos (fraudulento o no). Esto es aprendizaje supervisado porque el modelo aprende de ejemplos etiquetados.

**Tema:** Lunes - Tipos de ML

---

## Respuesta 2: B) The model explains 82% of the variance in house prices

**Explicación:**  
R² (coeficiente de determinación) indica qué porcentaje de la variabilidad en la variable objetivo es explicada por el modelo. R² = 0.82 es un modelo muy bueno.

**Tema:** Martes - Regresión y métricas

---

## Respuesta 3: B) Grouping customers into segments based on purchasing behavior

**Explicación:**  
Unsupervised learning se usa cuando NO tienes etiquetas. Clustering (agrupar) es el caso típico de unsupervised learning.

- A, C, D requieren datos etiquetados → Supervised

**Tema:** Lunes - Tipos de ML

---

## Respuesta 4: A) 70%

**Cálculo:**

```
Recall = TP / (TP + FN)
TP = 70 (detectó correctamente como positivo)
FN = 30 (era positivo pero predijo negativo)

Recall = 70 / (70 + 30) = 70 / 100 = 0.70 = 70%
```

**Tema:** Miércoles - Clasificación y métricas

---

## Respuesta 5: B) To provide a reference to Azure storage services where data is kept

**Explicación:**  
Un Datastore es una abstracción que referencia servicios de almacenamiento de Azure (Blob Storage, Data Lake, etc.) y almacena credenciales de acceso de forma segura.

**Tema:** Jueves - Azure ML Workspace

---

## Respuesta 6: B) 58%

**Cálculo:**

```
Precision = TP / (TP + FP)
TP = 70
FP = 50

Precision = 70 / (70 + 50) = 70 / 120 = 0.583 = 58.3% ≈ 58%
```

**Tema:** Miércoles - Clasificación y métricas

---

## Respuesta 7: B) Compute Cluster

**Explicación:**  
Compute Cluster escala automáticamente y permite ejecutar múltiples trabajos en paralelo. Es ideal para entrenar varios modelos simultáneamente.

- Compute Instance: para desarrollo interactivo (un solo nodo)
- Inference Cluster: para desplegar modelos

**Tema:** Jueves - Azure ML Workspace

---

## Respuesta 8: C) RMSE (Root Mean Squared Error)

**Explicación:**  
RMSE eleva los errores al cuadrado antes de promediarlos, lo que magnifica los errores grandes. Un error de 10 se convierte en 100, mientras que un error de 2 se convierte en 4.

MAE trata todos los errores linealmente.

**Tema:** Martes - Regresión y métricas

---

## Respuesta 9: B) Precision

**Explicación:**  
Cuando dices "spam", quieres estar muy seguro (alta Precision). Los falsos positivos (emails legítimos marcados como spam) son muy costosos porque pierdes información importante.

- Recall sería para detectar TODO el spam (incluso con falsas alarmas)

**Tema:** Miércoles - Clasificación y métricas

---

## Respuesta 10: B) A reward or penalty

**Explicación:**  
En reinforcement learning, el agente:

1. Toma una acción
2. Recibe una recompensa (si fue buena) o penalización (si fue mala)
3. Aprende qué acciones maximizan recompensas a largo plazo

Ejemplo: Robot que aprende a caminar recibe recompensa por avanzar, penalización por caer.

**Tema:** Lunes - Tipos de ML

---

## Respuesta 11: C) After 1 hour OR when AUC reaches 0.90, whichever comes first

**Explicación:**  
Exit criterion define cuándo parar. El experimento se detiene cuando se cumple CUALQUIERA de las condiciones:

- Tiempo límite (1 hora)
- Métrica objetivo alcanzada (AUC ≥ 0.90)

**Tema:** Viernes - AutoML

---

## Respuesta 12: B) The model predicted negative, but the actual value was positive

**Explicación:**  
**False Negative (FN):**

- Modelo dijo: "Negativo"
- Realidad: "Positivo"
- Es un ERROR (se le escapó el caso positivo)

Ejemplo: Detector de cáncer dice "no hay cáncer" pero sí lo hay (muy peligroso).

**Tema:** Miércoles - Clasificación y métricas

---

## Respuesta 13: B) The model explains less than half of the variance and needs improvement

**Explicación:**  
R² = 0.45 significa que el modelo solo explica el 45% de la variabilidad. El 55% queda sin explicar.

**Interpretación:**

- R² > 0.7: Bueno
- R² = 0.4-0.7: Moderado/Pobre
- R² < 0.4: Mal modelo

**Tema:** Martes - Regresión y métricas

---

## Respuesta 14: B) The automatic transformation of raw data into features useful for machine learning

**Explicación:**  
Featurization incluye:

- Imputación de valores faltantes
- Encoding de variables categóricas
- Normalización/escalado
- Feature engineering automático

Puede ser: Automatic, Custom, u Off.

**Tema:** Viernes - AutoML

---

## Respuesta 15: C) Reinforcement learning

**Explicación:**  
El robot aprende mediante trial and error (prueba y error):

- Intenta diferentes acciones
- Recibe recompensas (llegar a la meta)
- Recibe penalizaciones (chocar con pared)
- Aprende la mejor estrategia con el tiempo

**Tema:** Lunes - Tipos de ML

---

## Respuesta 16: B) No, the model might just be predicting "no disease" for everyone

**Explicación:**  
Con una enfermedad rara (2% prevalencia), un modelo que SIEMPRE predice "no enfermedad" tendría 98% accuracy:

- 98 personas sanas → predice "no" → correcto
- 2 personas enfermas → predice "no" → incorrecto

**Accuracy = 98/100 = 98%** pero el modelo es INÚTIL (nunca detecta la enfermedad).

Este es el problema clásico de accuracy con clases desbalanceadas.

**Tema:** Miércoles - Clasificación y métricas

---

## Respuesta 17: B) Datastore is a connection to storage; Dataset is a specific version of data

**Explicación:**

- **Datastore:** Conexión/referencia al servicio de almacenamiento (Blob, Data Lake)
- **Dataset:** Versión específica de datos, con metadata, versionado, puede venir de uno o más datastores

Analogía:

- Datastore = Conexión a biblioteca
- Dataset = Libro específico con edición

**Tema:** Jueves - Azure ML Workspace

---

## Respuesta 18: B) A model that combines predictions from multiple models

**Explicación:**  
Ensemble model combina múltiples modelos para obtener mejor resultado que cualquier modelo individual.

**Tipos en AutoML:**

- **Voting Ensemble:** Votación/promedio de predicciones
- **Stack Ensemble:** Meta-modelo que aprende a combinar otros modelos

Los ensembles suelen ser los ganadores en AutoML.

**Tema:** Viernes - AutoML

---

## Respuesta 19: B) Azure ML Designer

**Explicación:**  
Azure ML Designer es una interfaz visual drag-and-drop para crear pipelines de ML sin escribir código.

- Notebooks: requieren código Python
- VS Code: editor de código
- Azure Portal: administración general de Azure

**Tema:** Jueves - Azure ML Workspace

---

## Respuesta 20: C) Predicting temperature based on historical weather data

**Explicación:**  
Supervised learning requiere:

- Datos de entrada (features)
- Datos de salida conocidos (labels/targets)

Predicción de temperatura tiene datos históricos con temperaturas reales conocidas.

- A y B: Unsupervised (sin etiquetas)
- D: Reinforcement learning (aprendizaje por recompensas)

**Tema:** Lunes - Tipos de ML

---

## Respuesta 21: B) The model is very confident when it predicts positive, but misses many positive cases

**Explicación:**

- **Precision 85%:** Cuando dice "positivo", tiene razón el 85% de las veces → muy confiable
- **Recall 45%:** Solo detecta el 45% de los casos positivos reales → se pierde el 55%

El modelo es **conservador**: solo predice positivo cuando está muy seguro, pero se pierde muchos casos (alto FN).

**Tema:** Miércoles - Clasificación y métricas

---

## Respuesta 22: B) The model's ability to discriminate between positive and negative classes

**Explicación:**  
AUC (Area Under ROC Curve) mide qué tan bien el modelo puede separar clases positivas de negativas.

**Interpretación:**

- AUC = 1.0: Perfecto
- AUC = 0.9-1.0: Excelente
- AUC = 0.8-0.9: Muy bueno
- AUC = 0.5: Aleatorio (como lanzar moneda)

**Tema:** Miércoles - Clasificación y métricas (ROC/AUC)

---

## Respuesta 23: B) A logical container for grouping related training runs

**Explicación:**  
Un Experiment agrupa múltiples runs (ejecuciones) relacionadas, facilitando:

- Comparar diferentes intentos
- Tracking de métricas
- Organización de trabajos

Ejemplo: "House-Price-Prediction" experiment con múltiples runs probando diferentes algoritmos.

**Tema:** Jueves - Azure ML Workspace

---

## Respuesta 24: B) Regression

**Explicación:**  
Predecir precios es regresión porque:

- La variable objetivo es **numérica continua** (precio en $)
- Puede tomar cualquier valor en un rango
- No son categorías discretas

**Tema:** Martes - Regresión

---

## Respuesta 25: B) Stops training if no improvement is seen after several iterations

**Explicación:**  
Early stopping detiene el experimento si la métrica no mejora después de X iteraciones, para:

- Ahorrar tiempo de compute
- Reducir costos
- Evitar overfitting

**Tema:** Viernes - AutoML

---

## Respuesta 26: B) The model has good discriminative ability

**Explicación:**  
AUC = 0.87 está en el rango "Muy bueno" (0.8-0.9).

Significa que el modelo tiene 87% de probabilidad de darle mayor score a un caso positivo que a uno negativo.

**Tema:** Viernes - AutoML + Miércoles - ROC/AUC

---

## Respuesta 27: C) Precision is relatively low, meaning many legitimate transactions will be flagged

**Explicación:**  
Precision 60% significa que de todas las transacciones que el modelo marca como fraude:

- 60% realmente son fraude (TP)
- 40% son legítimas (FP) ← Problema

Con millones de transacciones, esto significa miles de clientes legítimos tendrán sus tarjetas bloqueadas incorrectamente (muy malo para customer experience).

**Tema:** Miércoles - Clasificación y métricas

---

## Respuesta 28: C) Recall

**Explicación:**  
En detección de fraude:

- **Falso Negativo** (FN): No detectar fraude real → banco pierde dinero
- **Falso Positivo** (FP): Bloquear transacción legítima → cliente molesto

Aunque ambos son malos, **perder dinero por fraude no detectado es peor** que molestar clientes (que pueden confirmar la transacción).

Por eso se prioriza **Recall** (detectar todos los fraudes), aunque genere algunos FP.

**Tema:** Miércoles - Clasificación y métricas

---

## Respuesta 29: B) Classification predicts categories; regression predicts continuous values

**Explicación:**

- **Classification:** Predice categorías discretas (spam/no spam, perro/gato/pájaro)
- **Regression:** Predice valores numéricos continuos (precio, temperatura, edad)

Ambos son supervised learning.

**Tema:** Lunes - Tipos de ML

---

## Respuesta 30: B) To store and version trained models centrally

**Explicación:**  
Model Registry es un repositorio centralizado que:

- Almacena modelos entrenados
- Versiona automáticamente (v1, v2, v3...)
- Guarda metadata (métricas, tags)
- Facilita deployment
- Permite rollback a versiones anteriores

**Tema:** Jueves - Azure ML Workspace

---

## Respuesta 31: C) Unsupervised learning - Clustering

**Explicación:**  
No tienes etiquetas predefinidas de "grupos de usuarios". Quieres que el algoritmo **descubra** automáticamente usuarios similares.

Clustering (K-means, etc.) agrupa usuarios con comportamiento similar sin supervisión.

**Tema:** Lunes - Tipos de ML

---

## Respuesta 32: B) Yes, RMSE of $50,000 is reasonable for this price range

**Explicación:**  
RMSE debe evaluarse en contexto del rango de valores:

- Rango de precios: $200k - $800k (amplitud $600k)
- RMSE: $50k
- Error relativo: $50k / $600k ≈ 8.3%

Un error del ~8% es razonable para predicción de precios de casas.

**Tema:** Martes - Regresión y métricas

---

## Respuesta 33: C) Model performs no better than random guessing

**Explicación:**  
AUC = 0.5 corresponde a la línea diagonal en la curva ROC, que representa un clasificador aleatorio (como lanzar una moneda).

El modelo no tiene capacidad de discriminación entre clases.

**Tema:** Miércoles - Clasificación y métricas (ROC/AUC)

---

## Respuesta 34: B) All algorithms except XGBoost and LightGBM will be tested

**Explicación:**  
`blocked_algorithms` especifica qué algoritmos **NO** probar.

AutoML probará todos los algoritmos disponibles EXCEPTO los bloqueados.

- `allowed_algorithms` haría lo contrario: solo probar los especificados

**Tema:** Viernes - AutoML

---

## Respuesta 35: B) Compute Instance

**Explicación:**  
Compute Instance es ideal para:

- Desarrollo interactivo
- Jupyter notebooks
- Testing y experimentación
- Un solo usuario
- Siempre un nodo (no escala)

Compute Cluster es para entrenamiento de modelos y jobs en paralelo.

**Tema:** Jueves - Azure ML Workspace

---

## Respuesta 36: C) Supervised learning - Classification

**Explicación:**

- Tienes datos históricos con resultado conocido (churn o no churn) → **Supervised**
- Predices categoría (stay/leave) → **Classification**

Si predijeras "cuánto tiempo hasta que el cliente se vaya" sería regresión.

**Tema:** Lunes - Tipos de ML

---

## Respuesta 37: B) The harmonic mean of Precision and Recall

**Explicación:**

```
F1 Score = 2 × (Precision × Recall) / (Precision + Recall)
```

F1 Score:

- Balancea Precision y Recall
- Penaliza extremos (solo alta P o solo alto R)
- Útil cuando necesitas equilibrio
- Rango: 0 a 1

**Tema:** Miércoles - Clasificación y métricas

---

## Respuesta 38: B) Which model AutoML will select as the best

**Explicación:**  
Primary metric es la métrica que AutoML usa para:

- Evaluar cada modelo
- Comparar modelos entre sí
- Seleccionar el mejor modelo

Ejemplos:

- Classification: AUC_weighted, Accuracy, Precision
- Regression: Normalized RMSE, R², MAE

**Tema:** Viernes - AutoML

---

## Respuesta 39: C) The model is worse than simply predicting the mean

**Explicación:**  
R² negativo es posible (aunque raro) y significa:

- El modelo hace predicciones **peores** que simplemente predecir la media de todos los valores
- Hay un error fundamental en el modelo o datos
- Necesitas revisar: features, preprocesamiento, tipo de modelo

R² = 0 sería predecir siempre la media (baseline).

**Tema:** Martes - Regresión y métricas

---

## Respuesta 40: C) Both A and B

**Explicación:**  
**Recall 95%:** Detecta el 95% de todos los casos reales de cáncer → se pierde muy pocos casos (excelente).

**Precision 70%:** De todos los que marca como "cáncer", solo el 70% realmente lo tienen → 30% son falsos positivos (muchos pacientes sin cáncer reciben diagnóstico falso).

En medicina, especialmente cáncer:

- **Alto Recall es CRÍTICO** (no podemos perdernos casos reales)
- Falsos positivos son manejables (más pruebas para confirmar)

Este modelo es apropiado para screening inicial.

**Tema:** Miércoles - Clasificación y métricas

---

# 📊 RESULTADOS

## Calcula tu puntuación:

```
Total de respuestas correctas: ___ / 40

Puntuación: (correctas / 40) × 100 = ____%
```

---

## 🎯 Interpretación de tu resultado:

**90-100% (36-40 correctas):** 🌟 Excelente

- Dominas los conceptos de la Semana 2
- Listo para el examen en esta área
- Continúa con Semana 3

**80-89% (32-35 correctas):** ✅ Muy Bueno

- Buen dominio general
- Repasa temas donde fallaste
- Casi listo para el examen

**70-79% (28-31 correctas):** 👍 Bueno

- Comprensión sólida pero con lagunas
- Repasa las secciones débiles
- Practica más con las métricas

**60-69% (24-27 correctas):** ⚠️ Regular

- Necesitas repasar varios conceptos
- Revisa el material de la semana
- Enfócate en áreas débiles

**<60% (<24 correctas):** 🔄 Necesitas repasar

- Repasa toda la Semana 2
- Vuelve a leer el material
- Haz los ejercicios prácticos
- Repite el simulacro en 2-3 días

---

## 📈 Análisis por tema:

**Identifica tus áreas débiles:**

### Lunes - Tipos de ML:

Preguntas: 1, 3, 10, 15, 20, 29, 31, 36

### Martes - Regresión y métricas:

Preguntas: 2, 8, 13, 24, 32, 39

### Miércoles - Clasificación y métricas:

Preguntas: 4, 6, 9, 12, 16, 21, 22, 27, 28, 33, 37, 40

### Jueves - Azure ML Workspace:

Preguntas: 5, 7, 17, 19, 23, 30, 35

### Viernes - AutoML:

Preguntas: 11, 14, 18, 25, 26, 34, 38

---

## 💡 Próximos pasos según tu resultado:

**Si obtuviste >80%:**

1. ✅ ¡Felicidades! Dominas la Semana 2
2. 📝 Repasa solo las preguntas que fallaste
3. 🚀 Continúa con Semana 3 (Computer Vision)

**Si obtuviste 60-80%:**

1. 📚 Identifica temas débiles (usa análisis por tema arriba)
2. 📖 Relee las secciones correspondientes
3. ✍️ Repasa flashcards de esos días
4. 🔄 Repite este simulacro en 2 días

**Si obtuviste <60%:**

1. 📕 Repasa TODO el material de Semana 2
2. ✏️ Haz los ejercicios prácticos de cada día
3. 🧠 Crea y repasa TODAS las flashcards
4. ⏸️ NO avances a Semana 3 todavía
5. 🔁 Repite simulacro en 3-4 días

---

## 🎯 Consejos para mejorar:

1. **Las métricas son clave:**
   - Practica calcular Accuracy, Precision, Recall manualmente
   - Entiende CUÁNDO usar cada métrica
   - Comprende el trade-off Precision vs Recall

2. **Confusion Matrix:**
   - Dibuja matrices en papel
   - Identifica TP, TN, FP, FN rápidamente
   - Calcula métricas desde la matriz

3. **Contexto de negocio:**
   - Piensa en el COSTO de los errores
   - FP vs FN: ¿cuál es peor?
   - Relaciona con casos reales

4. **Azure ML:**
   - Familiarízate con terminología
   - Datastore vs Dataset
   - Compute Instance vs Cluster
   - AutoML configuración

5. **ROC y AUC:**
   - Entiende qué mide AUC
   - Interpreta valores (0.5 = aleatorio, 1.0 = perfecto)
   - Ventajas sobre Accuracy

---

## 📝 Registro de intentos:

**Intento 1:**

- Fecha: \***\*\_\_\_\*\***
- Puntuación: \_\_\_\_%
- Temas débiles: \***\*\_\_\_\*\***

**Intento 2 (si es necesario):**

- Fecha: \***\*\_\_\_\*\***
- Puntuación: \_\_\_\_%
- Mejora: \_\_\_\_%
- Temas débiles restantes: \***\*\_\_\_\*\***

---

## 🎊 ¡EXCELENTE TRABAJO!

Has completado el simulacro de la Semana 2.

**Recuerda:**

- El examen AI-900 real tiene 40-60 preguntas
- Tiempo: 45 minutos
- Puntuación aprobatoria: 700/1000 (≈70%)

**Estás en buen camino para conseguir tu certificación!** 💪🚀

---

_Simulacro creado: Noviembre 2025_  
_Basado en: Semana 2 completa del roadmap AI-900_  
_Estilo: Microsoft AI-900 oficial_
