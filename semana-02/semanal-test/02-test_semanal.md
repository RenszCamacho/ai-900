# 🎯 SIMULACRO DE ESCENARIOS - AI-900 (Semana 2)

## Simulacro #1 - Scenario-Based Questions

**Tipo de preguntas:** Escenarios de negocio realistas  
**Cantidad:** 25 preguntas agrupadas en 8 escenarios  
**Tiempo sugerido:** 40 minutos  
**Estilo:** Microsoft AI-900 oficial

---

## 📋 INSTRUCCIONES

**Formato de escenarios:**

- Cada escenario tiene 2-4 preguntas relacionadas
- Lee TODO el escenario antes de responder
- Las preguntas están conectadas (como en el examen real)
- Anota tus respuestas en tu cuaderno
- NO mires las respuestas hasta terminar

**Anotación sugerida:**

```
SIMULACRO ESCENARIOS #1
Fecha: ___________

1. __    6. __    11. __    16. __    21. __
2. __    7. __    12. __    17. __    22. __
3. __    8. __    13. __    18. __    23. __
4. __    9. __    14. __    19. __    24. __
5. __    10. __   15. __    20. __    25. __
```

---

# 📝 ESCENARIOS Y PREGUNTAS

---

## 🏥 ESCENARIO 1: Sistema de diagnóstico médico

**Contexto:**
You work for a hospital that wants to develop an AI system to help doctors diagnose pneumonia from chest X-ray images. The hospital has a dataset of 50,000 X-ray images:

- 45,000 images of healthy lungs (90%)
- 5,000 images showing pneumonia (10%)

Each image is labeled by expert radiologists as either "healthy" or "pneumonia".

Your initial model produces the following results:

```
Confusion Matrix:
                  Predicted
              Healthy  Pneumonia
Actual  H      8,900      100
        P        400      600

Metrics:
- Accuracy: 95%
- Precision: 85.7%
- Recall: 60%
- F1 Score: 70.6%
- AUC: 0.88
```

---

### Question 1

What type of machine learning is most appropriate for this pneumonia detection system?

- [ ] A) Unsupervised learning
- [x] B) Supervised learning
- [ ] C) Reinforcement learning
- [ ] D) Semi-supervised learning

---

### Question 2

The hospital is most concerned about missing pneumonia cases (patients who have pneumonia but are diagnosed as healthy). Which metric indicates the severity of this problem?

- [ ] A) Precision of 85.7%
- [x] B) Recall of 60%
- [ ] C) Accuracy of 95%
- [ ] D) AUC of 0.88

---

### Question 3

What does the Recall value of 60% mean in this medical context?

- [ ] A) 60% of patients predicted to have pneumonia actually have it
- [x] B) The model correctly identifies 60% of all actual pneumonia cases
- [ ] C) The model is 60% accurate overall
- [ ] D) 60% of healthy patients are correctly identified

---

### Question 4

The hospital director says: "We cannot afford to miss pneumonia cases. False negatives could be fatal." Which metric should you prioritize when optimizing the model?

- [ ] A) Accuracy
- [ ] B) Precision
- [x] C) Recall
- [ ] D) F1 Score

---

## 🏦 ESCENARIO 2: Sistema bancario de aprobación de préstamos

**Contexto:**
A bank wants to build an AI model to automate loan approval decisions. They have historical data from 100,000 past loan applications with the following information for each application:

- Applicant age, income, employment history, credit score
- Whether the loan was approved or rejected
- Whether the borrower defaulted (if loan was approved)

The bank wants to predict whether a new applicant should be approved or rejected based on their likelihood to repay.

---

### Question 5

What type of machine learning task is this?

- [ ] A) Regression
- [x] B) Classification
- [ ] C) Clustering
- [ ] D) Anomaly detection

---

### Question 6

You train a model and achieve the following metrics:

- Accuracy: 92%
- Precision (for approval): 78%
- Recall (for approval): 85%

The bank is concerned about approving loans to people who will default. Which metric best addresses this concern?

- [ ] A) Accuracy - shows overall performance
- [x] B) Precision - shows reliability when approving loans
- [ ] C) Recall - shows how many good applicants we approve
- [ ] D) F1 Score - balances both concerns

---

### Question 7

The bank decides that missing good customers (false negatives) is less costly than approving bad loans (false positives). How should you adjust the model?

- [x] A) Increase the classification threshold to improve Precision
- [ ] B) Decrease the classification threshold to improve Recall
- [ ] C) Maximize Accuracy regardless of Precision/Recall
- [ ] D) Use clustering instead of classification

---

## 🏭 ESCENARIO 3: Predicción de mantenimiento en fábrica

**Contexto:**
A manufacturing company wants to predict when industrial machines will need maintenance. They have collected 2 years of sensor data from 500 machines:

- Temperature readings every minute
- Vibration levels
- Hours of operation
- When each machine actually failed or required maintenance

The goal is to predict "hours until maintenance needed" for each machine.

---

### Question 8

What type of machine learning task is this?

- [ ] A) Classification
- [x] B) Regression
- [ ] C) Clustering
- [ ] D) Reinforcement learning

---

### Question 9

Your model produces the following metrics:

- RMSE: 48 hours
- MAE: 32 hours
- R²: 0.73

Machines typically run 2,000-3,000 hours between maintenance. How should you interpret the R² value?

- [ ] A) The model has 73% accuracy
- [x] B) The model explains 73% of the variance in maintenance timing
- [ ] C) 73% of predictions are within 48 hours
- [ ] D) The model will be correct 73% of the time

---

### Question 10

The factory manager asks: "What does RMSE of 48 hours mean practically?" What is the best explanation?

- [ ] A) The model will be wrong 48% of the time
- [x] B) On average, predictions are off by approximately 48 hours
- [ ] C) The model predicts exactly 48 hours for all machines
- [ ] D) 48% of machines need maintenance

---

## 🛒 ESCENARIO 4: Sistema de recomendación de e-commerce

**Contexto:**
An e-commerce company wants to build a recommendation system. They have:

- Purchase history for 10 million customers
- Product catalog with 500,000 items
- Customer browsing behavior and search history

They want to group customers with similar purchasing patterns to provide better recommendations.

---

### Question 11

What type of machine learning approach is most suitable for finding customer groups?

- [ ] A) Supervised learning - Classification
- [ ] B) Supervised learning - Regression
- [x] C) Unsupervised learning - Clustering
- [ ] D) Reinforcement learning

---

### Question 12

After grouping customers, the company wants to predict which products a customer will buy next based on their group membership and past purchases. What type of machine learning is this?

- [ ] A) Unsupervised learning
- [x] B) Supervised learning
- [ ] C) Reinforcement learning
- [ ] D) Transfer learning

---

## 🚗 ESCENARIO 5: Azure AutoML para predicción de precios de autos

**Contexto:**
You are building a car price prediction model using Azure Automated ML. Your dataset contains:

- 50,000 used car listings
- Features: brand, model, year, mileage, condition, location
- Target: selling price

You configure the AutoML experiment with:

- Task type: Regression
- Primary metric: normalized_root_mean_squared_error
- Training job time: 2 hours
- Metric score threshold: 0.15
- Enable early stopping: Yes
- Max concurrent iterations: 4

---

### Question 13

When will the AutoML experiment stop training?

- [ ] A) Exactly after 2 hours
- [ ] B) After trying all possible algorithms
- [x] C) After 2 hours OR when normalized RMSE reaches 0.15, whichever comes first
- [ ] D) When it has trained exactly 4 models

---

### Question 14

The experiment completes with these results for the top 3 models:

```
1. VotingEnsemble:    RMSE = 0.12, R² = 0.89
2. StackEnsemble:     RMSE = 0.13, R² = 0.87
3. LightGBM:          RMSE = 0.14, R² = 0.86
```

Which model will AutoML select as the best?

- [x] A) VotingEnsemble - lowest RMSE (0.12)
- [ ] B) VotingEnsemble - highest R² (0.89)
- [ ] C) StackEnsemble - it's more sophisticated
- [ ] D) LightGBM - it's the fastest

---

### Question 15

What does "Enable early stopping: Yes" accomplish in this experiment?

- [ ] A) Stops immediately if any model fails
- [x] B) Stops training individual models if they stop improving
- [ ] C) Stops the entire experiment after the first model
- [ ] D) Prevents overfitting in all models

---

### Question 16

After the experiment completes, you want to understand which features most influence car prices. Where should you look in Azure ML Studio?

- [ ] A) The Confusion Matrix tab
- [x] B) The Explanations tab (Feature Importance)
- [ ] C) The ROC Curve tab
- [ ] D) The Compute tab

---

## 📧 ESCENARIO 6: Filtro de spam empresarial

**Contexto:**
A company receives 1 million emails per day. They want to build a spam filter with these requirements:

**Business requirements:**

- Critical work emails MUST NOT be blocked (highest priority)
- Some spam in inbox is acceptable
- Blocked emails go to quarantine (can be reviewed)

Your spam detection model produces:

```
Out of 10,000 test emails:
- 7,000 legitimate emails
- 3,000 spam emails

Confusion Matrix:
                  Predicted
              Legitimate  Spam
Actual  Leg      6,860    140
        Spam       450  2,550

Metrics:
- Accuracy: 94.1%
- Precision: 94.8%
- Recall: 85%
```

---

### Question 17

What does the Precision of 94.8% tell you about this spam filter?

- [ ] A) 94.8% of all emails are classified correctly
- [x] B) 94.8% of emails marked as spam are actually spam
- [ ] C) 94.8% of spam emails are correctly detected
- [ ] D) The filter blocks 94.8% of all emails

---

### Question 18

What is the main problem with this model given the business requirement that "critical work emails MUST NOT be blocked"?

- [ ] A) Recall is too low at 85%
- [ ] B) Accuracy is too low at 94.1%
- [x] C) There are 140 false positives (legitimate emails marked as spam)
- [ ] D) There are 450 false negatives (spam emails not detected)

---

### Question 19

How many legitimate work emails would be incorrectly blocked per day (false positives) if this model is deployed?

- [ ] A) 140 emails
- [ ] B) 450 emails
- [x] C) Approximately 14,000 emails
- [ ] D) Approximately 45,000 emails

---

### Question 20

Given the business requirement to prioritize not blocking legitimate emails, what should you do?

- [x] A) Increase the classification threshold to improve Precision further
- [ ] B) Decrease the classification threshold to improve Recall
- [ ] C) Focus on improving Accuracy to 99%
- [ ] D) Use a different primary metric like F1 Score

---

## 🏥 ESCENARIO 7: Azure ML Workspace para investigación médica

**Contexto:**
A medical research team wants to use Azure Machine Learning to analyze patient data and develop diagnostic models. They need to:

- Store large datasets from multiple hospitals (stored in Azure Blob Storage and Azure Data Lake)
- Run multiple training experiments in parallel
- Allow 5 data scientists to work simultaneously
- Track all experiment results and model versions
- Deploy the best models for clinical testing

They have an Azure subscription and need to set up their ML infrastructure.

---

### Question 21

What is the FIRST resource they should create in Azure?

- [ ] A) Compute Cluster
- [x] B) Azure ML Workspace
- [ ] C) Storage Account
- [ ] D) Virtual Machine

---

### Question 22

To connect their existing Azure Blob Storage (containing patient data) to Azure ML, what should they create?

- [ ] A) A new Storage Account
- [x] B) A Datastore
- [ ] C) A Compute Instance
- [ ] D) An Experiment

---

### Question 23

The team needs to run multiple model training jobs in parallel using different algorithms. Which compute resource should they provision?

- [ ] A) 5 separate Compute Instances (one per data scientist)
- [x] B) A Compute Cluster with min_nodes=0 and max_nodes=5
- [ ] C) A single powerful Virtual Machine
- [ ] D) An Inference Cluster

---

### Question 24

Where should the team look to compare metrics across all their experiments?

- [x] A) The Experiments section showing all runs
- [ ] B) The Models section in the registry
- [ ] C) The Datastores section
- [ ] D) The Compute section

---

### Question 25

After identifying the best model, they want to version it and prepare for deployment. Where should they register the model?

- [ ] A) In Azure Blob Storage
- [ ] B) In the Datastore
- [x] C) In the Model Registry
- [ ] D) In a new Experiment

---

## ⏸️ PAUSA - No continúes hasta terminar

**¿Terminaste las 25 preguntas?**

Si SÍ → Continúa para ver las respuestas  
Si NO → No hagas scroll todavía

---

---

---

# 📊 RESPUESTAS Y EXPLICACIONES DETALLADAS

---

## 🏥 ESCENARIO 1: Sistema de diagnóstico médico

### Respuesta 1: B) Supervised learning

**Explicación:**
Tienes 50,000 imágenes **etiquetadas** por radiólogos expertos (healthy o pneumonia). Esto es aprendizaje supervisado porque:

- Tienes datos de entrada (X-ray images)
- Tienes datos de salida conocidos (labels: healthy/pneumonia)
- El modelo aprende de estos ejemplos etiquetados

**Temática:** Tipos de ML

---

### Respuesta 2: B) Recall of 60%

**Explicación:**
**Casos perdidos = Falsos Negativos (FN)**

```
FN = 400 (tienen pneumonia pero el modelo dice "healthy")

Recall = TP / (TP + FN) = 600 / (600 + 400) = 60%
```

**Recall del 60% significa:**

- El modelo solo detecta el 60% de los casos de pneumonia
- Se pierde el 40% (400 pacientes con pneumonia diagnosticados como sanos)

**Esto es GRAVE:** Pacientes enfermos se van a casa sin tratamiento.

**Por qué otras no:**

- Precision: Mide confiabilidad cuando dice "pneumonia"
- Accuracy: Puede ser engañosa con clases desbalanceadas
- AUC: Métrica general, no específica para FN

**Temática:** Clasificación - Métricas

---

### Respuesta 3: B) The model correctly identifies 60% of all actual pneumonia cases

**Explicación:**
**Recall = Sensibilidad = ¿Detecto todos los casos positivos?**

```
Total casos reales de pneumonia: 1,000
Casos detectados correctamente: 600
Casos perdidos: 400

Recall = 600 / 1,000 = 60%
```

**En contexto médico:**

- De cada 100 pacientes con pneumonia
- El modelo detecta 60
- Se le escapan 40

**Temática:** Clasificación - Interpretación de Recall

---

### Respuesta 4: C) Recall

**Explicación:**
**"No podemos permitirnos perder casos de pneumonia"** → Priorizar Recall

**Razonamiento:**

- **Falso Negativo (FN):** Paciente tiene pneumonia pero no se detecta → FATAL (no recibe tratamiento)
- **Falso Positivo (FP):** Paciente sano diagnosticado con pneumonia → Confirmación con más pruebas

**En medicina:**

```
FN (no detectar enfermedad) >>> FP (falsa alarma)
```

**Estrategia:** Maximizar Recall aunque genere más falsos positivos (que se pueden verificar).

**Temática:** Clasificación - Decisión de negocio

---

## 🏦 ESCENARIO 2: Sistema bancario de aprobación de préstamos

### Respuesta 5: B) Classification

**Explicación:**
Predices una **categoría binaria:**

- Aprobar (approve)
- Rechazar (reject)

**No es regresión porque:**

- No predices un valor numérico (ej: "probabilidad de default")
- Predices una decisión categórica

**Nota:** Internamente el modelo puede calcular probabilidades, pero la salida final es una clasificación.

**Temática:** Tipos de tareas ML

---

### Respuesta 6: B) Precision - shows reliability when approving loans

**Explicación:**
**"Preocupados por aprobar préstamos a gente que hará default"** → Falsos Positivos

**Precision responde:**
"De todos los préstamos que APROBAMOS, ¿cuántos realmente serán pagados?"

```
Precision = 78%

Significa:
- De cada 100 préstamos aprobados
- 78 serán pagados (TP)
- 22 harán default (FP) ← Problema del banco
```

**Precision baja = Muchos préstamos malos aprobados = Pérdidas financieras**

**Por qué otras no:**

- Accuracy: Métrica general, no específica para este riesgo
- Recall: Mide cuántos buenos clientes detectamos (menos crítico)
- F1: Balance, pero aquí hay prioridad clara

**Temática:** Clasificación - Aplicación de negocio

---

### Respuesta 7: A) Increase the classification threshold to improve Precision

**Explicación:**
**"Perder buenos clientes es menos costoso que aprobar malos préstamos"** → Priorizar Precision

**Ajuste de umbral:**

**Umbral normal (0.5):**

```
Probabilidad > 0.5 → Aprobar
```

**Umbral alto (0.7):**

```
Probabilidad > 0.7 → Aprobar (más conservador)

Efecto:
✅ Menos FP (menos préstamos malos aprobados)
✅ Mayor Precision
❌ Más FN (rechazamos algunos buenos clientes)
❌ Menor Recall
```

**Decisión de negocio:** Ser conservador, aprobar solo cuando estés muy seguro.

**Temática:** Clasificación - Optimización de modelo

---

## 🏭 ESCENARIO 3: Predicción de mantenimiento en fábrica

### Respuesta 8: B) Regression

**Explicación:**
Predices **"horas hasta mantenimiento"** = Valor numérico continuo

**Características de regresión:**

- Variable objetivo: numérica (48 horas, 1,234 horas, etc.)
- Puede tomar cualquier valor en un rango
- No son categorías discretas

**Si fuera clasificación:** Predirías "necesita mantenimiento pronto/tarde/nunca"

**Temática:** Tipos de tareas ML

---

### Respuesta 9: B) The model explains 73% of the variance in maintenance timing

**Explicación:**
**R² = 0.73 (Coeficiente de determinación)**

**Significa:**

- El modelo explica el 73% de la variabilidad en cuándo las máquinas necesitan mantenimiento
- El 27% restante no es explicado (factores externos, aleatoriedad, etc.)

**Interpretación:**

- R² = 0.73 es un modelo **bueno/moderado**
- Para mantenimiento predictivo es aceptable
- Podría mejorarse pero es útil

**NO significa:**

- ❌ 73% de accuracy
- ❌ 73% de predicciones correctas
- ❌ Error del 27%

**Temática:** Regresión - Interpretación de R²

---

### Respuesta 10: B) On average, predictions are off by approximately 48 hours

**Explicación:**
**RMSE = 48 horas**

**En términos prácticos:**

- Si predices que una máquina necesita mantenimiento en 1,000 horas
- El valor real probablemente estará entre 952-1,048 horas
- Error promedio típico: ±48 horas

**Contexto:**

- Máquinas operan 2,000-3,000 horas entre mantenimientos
- Error de 48 horas = ~2-3% del ciclo
- **Es razonable** para planificación de mantenimiento

**Por qué otras no:**

- ❌ "Wrong 48% of the time": RMSE no es un porcentaje de error
- ❌ "Predicts exactly 48 hours": RMSE es una medida de error, no una predicción
- ❌ "48% need maintenance": No tiene relación

**Temática:** Regresión - Interpretación práctica de RMSE

---

## 🛒 ESCENARIO 4: Sistema de recomendación de e-commerce

### Respuesta 11: C) Unsupervised learning - Clustering

**Explicación:**
**"Agrupar clientes con patrones similares"** = Clustering (unsupervised)

**Por qué unsupervised:**

- NO tienes etiquetas predefinidas de "grupos de clientes"
- Quieres que el algoritmo **descubra** automáticamente los grupos
- No sabes de antemano cuántos grupos hay o cómo son

**Algoritmos típicos:**

- K-means
- Hierarchical clustering
- DBSCAN

**Resultado:** Clientes agrupados por similitud en comportamiento de compra.

**Temática:** Tipos de ML - Unsupervised learning

---

### Respuesta 12: B) Supervised learning

**Explicación:**
**"Predecir qué productos comprará"** basado en datos históricos = Supervised learning

**Por qué supervised:**

- Tienes datos históricos: qué productos compró cada cliente (labels conocidos)
- El modelo aprende de estos ejemplos
- Predice compras futuras basándose en patrones aprendidos

**Flujo completo:**

1. **Unsupervised:** Agrupar clientes similares (clustering)
2. **Supervised:** Predecir compras futuras basándose en grupo y historial

**Temática:** Tipos de ML - Combinación de enfoques

---

## 🚗 ESCENARIO 5: Azure AutoML para predicción de precios de autos

### Respuesta 13: C) After 2 hours OR when normalized RMSE reaches 0.15, whichever comes first

**Explicación:**
**Exit Criterion** define cuándo parar:

**Dos condiciones:**

1. **Training job time:** 2 hours
2. **Metric score threshold:** 0.15 (normalized RMSE)

**El experimento para cuando se cumple CUALQUIERA:**

**Escenario A:**

```
Hora 1: Mejor RMSE = 0.20
Hora 1.5: Mejor RMSE = 0.14 ← Alcanzó 0.15
→ PARA (solo tardó 1.5 horas)
```

**Escenario B:**

```
Hora 1: Mejor RMSE = 0.25
Hora 2: Mejor RMSE = 0.18 ← Tiempo agotado
→ PARA (no alcanzó 0.15 pero se acabó el tiempo)
```

**Temática:** AutoML - Exit Criterion

---

### Respuesta 14: A) VotingEnsemble - lowest RMSE (0.12)

**Explicación:**
**Primary metric configurada:** normalized_root_mean_squared_error

**AutoML selecciona el modelo con el MEJOR valor de la primary metric:**

```
Primary metric: RMSE (lower is better)

VotingEnsemble:  RMSE = 0.12 ← MEJOR (más bajo)
StackEnsemble:   RMSE = 0.13
LightGBM:        RMSE = 0.14
```

**Ganador:** VotingEnsemble (RMSE más bajo)

**Nota:** Aunque VotingEnsemble también tiene el R² más alto (0.89), la decisión se basa en la primary metric (RMSE), no en R².

**Temática:** AutoML - Primary Metric

---

### Respuesta 15: B) Stops training individual models if they stop improving

**Explicación:**
**Early Stopping:**

- Monitorea cada modelo durante su entrenamiento
- Si un modelo deja de mejorar después de X iteraciones/epochs
- Para ese modelo específicamente (no todo el experimento)

**Beneficios:**

- ⏱️ Ahorra tiempo de compute
- 💰 Reduce costos
- 🎯 Evita overfitting

**Ejemplo:**

```
LightGBM training:
- Epoch 1-10: RMSE mejora (0.30 → 0.18)
- Epoch 11-20: RMSE estancado (0.18 → 0.18)
→ EARLY STOP: Para LightGBM en epoch 20
→ AutoML continúa con otros algoritmos
```

**NO para todo el experimento, solo modelos individuales que no mejoran.**

**Temática:** AutoML - Early Stopping

---

### Respuesta 16: B) The Explanations tab (Feature Importance)

**Explicación:**
**Feature Importance** muestra qué características más influyen en las predicciones.

**En Azure ML Studio:**

```
Best Model → Tab "Explanations" → Feature Importance

Ejemplo de resultado:
1. Mileage:     0.32 (32%) ← MÁS IMPORTANTE
2. Brand:       0.25 (25%)
3. Year:        0.18 (18%)
4. Condition:   0.15 (15%)
5. Model:       0.10 (10%)
```

**Interpretación:**

- El kilometraje (mileage) es el factor más importante en el precio
- La marca también influye significativamente
- El año del auto tiene impacto moderado

**Por qué otras no:**

- Confusion Matrix: Solo para clasificación
- ROC Curve: Solo para clasificación
- Compute: Gestión de recursos, no insights del modelo

**Temática:** AutoML - Interpretabilidad

---

## 📧 ESCENARIO 6: Filtro de spam empresarial

### Respuesta 17: B) 94.8% of emails marked as spam are actually spam

**Explicación:**
**Precision responde:** "De todo lo que marqué como spam, ¿cuánto realmente es spam?"

```
Precision = TP / (TP + FP)

TP = 2,550 (spam detectado correctamente)
FP = 140 (legítimo marcado como spam)

Precision = 2,550 / (2,550 + 140) = 2,550 / 2,690 = 94.8%
```

**Significa:**

- De cada 1,000 emails que el filtro marca como spam
- 948 realmente son spam ✅
- 52 son legítimos ❌ (bloqueados incorrectamente)

**Temática:** Clasificación - Interpretación de Precision

---

### Respuesta 18: C) There are 140 false positives (legitimate emails marked as spam)

**Explicación:**
**Requisito de negocio:** "Critical work emails MUST NOT be blocked"

**Problema del modelo:**

```
False Positives (FP) = 140 emails legítimos bloqueados

En 10,000 emails:
- 140 emails de trabajo importantes van a cuarentena
- Los usuarios NO ven estos emails
- Pueden perder información crítica
```

**Por qué otras no:**

- **A) Recall 85%:** Se relaciona con spam no detectado (FN), no con emails legítimos bloqueados
- **B) Accuracy 94.1%:** Métrica general, no específica al problema
- **D) 450 FN:** Spam que pasa al inbox es molesto, pero menos grave que bloquear trabajo importante

**Temática:** Clasificación - Identificación de problemas de negocio

---

### Respuesta 19: C) Approximately 14,000 emails

**Explicación:**
**Cálculo de extrapolación:**

```
Test set: 10,000 emails
- Legitimate: 7,000 (70%)
- False Positives: 140

Ratio FP: 140 / 7,000 = 0.02 = 2%

Daily volume: 1,000,000 emails
- Legitimate emails: 70% = 700,000
- Expected FP: 700,000 × 0.02 = 14,000 emails
```

**Resultado:** ~14,000 emails legítimos bloqueados por día

**Impacto:**

- 14,000 emails importantes en cuarentena diariamente
- Requiere revisión manual
- Pérdida de productividad masiva

**Temática:** Clasificación - Impacto de negocio

---

### Respuesta 20: A) Increase the classification threshold to improve Precision further

**Explicación:**
**Objetivo:** Minimizar FP (emails legítimos bloqueados)

**Estrategia:** Aumentar umbral de clasificación

**Ajuste de umbral:**

**Actual (umbral ~0.5):**

```
Score > 0.5 → Spam
Precision = 94.8%
FP = 140
```

**Nuevo (umbral 0.8):**

```
Score > 0.8 → Spam (más conservador)

Efecto:
✅ Mayor Precision (99%+)
✅ Menos FP (~20-30 emails bloqueados incorrectamente)
❌ Menor Recall (~70%)
❌ Más spam en inbox (aceptable según requisitos)
```

**Decisión de negocio:**

- Prioridad #1: NO bloquear trabajo importante
- Aceptable: Algo de spam en inbox
- Trade-off correcto para el negocio

**Por qué otras no:**

- **B) Decrease threshold:** Aumentaría FP (peor)
- **C) Focus on Accuracy:** No resuelve el problema de FP
- **D) Use F1:** No cambia la priorización del problema

**Temática:** Clasificación - Optimización basada en negocio

---

## 🏥 ESCENARIO 7: Azure ML Workspace para investigación médica

### Respuesta 21: B) Azure ML Workspace

**Explicación:**
**Azure ML Workspace** es el recurso fundamental y PRIMERO que se debe crear.

**Razones:**

1. **Es el contenedor central** para todos los demás recursos
2. **Requiere:**
   - Suscripción de Azure
   - Resource Group
   - Región
3. **Crea automáticamente:** Storage Account, Key Vault, Application Insights

**Flujo correcto:**

```
1. Crear Workspace ← PRIMERO
2. Crear Datastores (conectar blob storage existente)
3. Crear Compute resources
4. Crear Experiments
```

**NO puedes crear Compute, Datastores o Experiments sin un Workspace.**

**Temática:** Azure ML - Configuración inicial

---

### Respuesta 22: B) A Datastore

**Explicación:**
**Datastore** = Conexión/referencia a servicios de almacenamiento existentes

**En este caso:**

```
Ya existe: Azure Blob Storage con datos de pacientes
Necesitas: Conectarlo a Azure ML

Solución: Crear un Datastore que:
- Referencias el Blob Storage existente
- Almacena credenciales de forma segura
- Permite acceso desde experimentos
```

**Código ejemplo:**

```python
from azure.ai.ml.entities import AzureBlobDatastore

blob_datastore = AzureBlobDatastore(
    name="patient_data_store",
    account_name="hospitalstorage",
    container_name="patient-records",
    credentials=account_key
)

ml_client.datastores.create_or_update(blob_datastore)
```

**Por qué otras no:**

- **A) New Storage Account:** Ya tienen storage, no necesitan otro
- **C) Compute Instance:** Para desarrollo, no para datos
- **D) Experiment:** Para tracking de runs, no para datos

**Temática:** Azure ML - Datastores

---

### Respuesta 23: B) A Compute Cluster with min_nodes=0 and max_nodes=5

**Explicación:**
**Requisito:** "Run multiple training jobs in parallel"

**Compute Cluster características:**

```
Configuración ideal:
- min_nodes: 0 (escala a cero cuando inactivo = ahorro)
- max_nodes: 5 (permite hasta 5 jobs en paralelo)
- VM size: Standard_DS3_v2 o similar

Beneficios:
✅ Auto-scaling (0 a 5 nodos según demanda)
✅ Ejecución paralela de múltiples experimentos
✅ Cost-effective (pagas solo lo que usas)
✅ Compartido entre todos los data scientists
```

**Por qué otras no:**

- **A) 5 Compute Instances separados:**
  - Más costoso (siempre activos)
  - No escalan automáticamente
  - Difícil de administrar
- **C) Single VM:**
  - No permite paralelización
  - No escala
- **D) Inference Cluster:**
  - Para deployment, no para training

**Temática:** Azure ML - Compute resources

---

### Respuesta 24: A) The Experiments section showing all runs

**Explicación:**
**Experiments** agrupa y organiza múltiples runs (ejecuciones).

**En Azure ML Studio:**

```
Experiments → "Medical Diagnosis Research"

Verás tabla con todos los runs:
Run ID    Algorithm         Accuracy  Precision  Recall  AUC
─────────────────────────────────────────────────────────
run_001   LogisticReg      0.82      0.78       0.85   0.88
run_002   RandomForest     0.87      0.84       0.88   0.92
run_003   XGBoost          0.89      0.86       0.90   0.94
run_004   VotingEnsemble   0.91      0.88       0.92   0.95

✅ Comparar métricas fácilmente
✅ Identificar el mejor modelo
✅ Ver tendencias y progreso
```

**Funcionalidad:**

- Ordenar por cualquier métrica
- Filtrar runs
- Visualizar gráficos comparativos
- Exportar resultados

**Por qué otras no:**

- **B) Models:** Muestra modelos registrados, no todos los runs
- **C) Datastores:** Para gestión de datos
- **D) Compute:** Para gestión de recursos

**Temática:** Azure ML - Experiments y tracking

---

### Respuesta 25: C) In the Model Registry

**Explicación:**
**Model Registry** = Repositorio centralizado para modelos entrenados

**Propósito:**

```
1. Registrar modelo:
   - Nombre: "pneumonia-detector"
   - Versión: v1
   - Métricas: Accuracy=0.91, AUC=0.95
   - Archivos: model.pkl, preprocessing.pkl
   - Tags: "production-ready", "clinical-trial"

2. Versionado automático:
   - v1 → Initial model
   - v2 → Improved with more data
   - v3 → Fine-tuned version

3. Metadata:
   - Quién lo creó
   - Cuándo se creó
   - De qué experiment/run viene
   - Hiperparámetros usados

4. Deployment:
   - Deploy directamente desde registry
   - Rollback a versiones anteriores
   - A/B testing entre versiones
```

**Beneficios:**

- ✅ Trazabilidad completa
- ✅ Versionado automático
- ✅ Facilita deployment
- ✅ Auditoría y compliance
- ✅ Colaboración entre equipo

**Por qué otras no:**

- **A) Blob Storage:** Almacenamiento raw, sin versionado ni metadata
- **B) Datastore:** Para datos, no modelos
- **D) Experiment:** Para tracking de runs, no para modelos finales

**Temática:** Azure ML - Model Registry

---

# 📊 CALIFICACIÓN Y ANÁLISIS

## Tu puntuación:

```
Respuestas correctas: ___ / 25

Porcentaje: (correctas / 25) × 100 = ____%
```

---

## 🎯 Interpretación:

**23-25 correctas (92-100%):** 🌟 Excelente

- Dominas escenarios de negocio
- Aplicas conceptos correctamente
- Listo para el examen

**20-22 correctas (80-88%):** ✅ Muy Bueno

- Buena comprensión de escenarios
- Revisa las que fallaste
- Casi listo

**17-19 correctas (68-76%):** 👍 Bueno

- Comprensión sólida
- Necesitas practicar interpretación de negocio
- Repasa áreas débiles

**14-16 correctas (56-64%):** ⚠️ Regular

- Entiendes conceptos técnicos
- Dificultad aplicando a negocio
- Repasa escenarios

**<14 correctas (<56%):** 🔄 Necesitas repasar

- Repasa material de Semana 2
- Practica más con escenarios
- Enfócate en aplicación práctica

---

## 📈 Análisis por escenario:

**Escenario 1 (Medicina - Q1-4):** **\_/4
**Escenario 2 (Banca - Q5-7):** \_**/3
**Escenario 3 (Manufactura - Q8-10):** **\_/3
**Escenario 4 (E-commerce - Q11-12):** \_**/2
**Escenario 5 (AutoML - Q13-16):** **\_/4
**Escenario 6 (Spam - Q17-20):** \_**/4
**Escenario 7 (Azure ML - Q21-25):** \_\_\_/5

---

## 💡 Áreas a reforzar según errores:

**Si fallaste en Escenarios 1 o 6:**
→ Repasa: Precision vs Recall, decisiones de negocio, trade-offs

**Si fallaste en Escenario 2:**
→ Repasa: Ajuste de umbrales, optimización basada en costos

**Si fallaste en Escenario 3:**
→ Repasa: Interpretación de RMSE y R² en contexto real

**Si fallaste en Escenario 4:**
→ Repasa: Diferencia entre supervised y unsupervised learning

**Si fallaste en Escenario 5:**
→ Repasa: AutoML (exit criterion, primary metric, feature importance)

**Si fallaste en Escenario 7:**
→ Repasa: Azure ML Workspace, Datastores, Compute, Model Registry

---

## 🎊 ¡EXCELENTE TRABAJO!

**Has completado el Simulacro de Escenarios #1**

**¿Quieres el Simulacro #2 con más escenarios?** 🚀

---

_Simulacro creado: Domingo, Noviembre 2025_  
_Basado en: Semana 2 completa - Escenarios realistas_  
_Estilo: Microsoft AI-900 Scenario-Based Questions_
