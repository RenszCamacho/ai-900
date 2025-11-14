# 📚 VIERNES 14 NOV - SEMANA 2: AutoML (Automated Machine Learning)

**Fecha:** Viernes 14 de noviembre 2025  
**Semana:** 2 de 6  
**Tema:** Automated Machine Learning en Azure  
**Duración:** 1 hora 30 minutos

---

## 🎯 Objetivos del día

Al finalizar hoy deberás:

- ✅ Entender qué es Azure AutoML y cuándo usarlo
- ✅ Conocer el proceso automatizado de selección y entrenamiento de modelos
- ✅ Comprender la configuración de experimentos en Azure ML Studio
- ✅ Identificar los algoritmos que prueba AutoML
- ✅ Entender conceptos clave: ensemble, featurization, early stopping

---

## 📖 PARTE 1: ¿Qué es AutoML? (30 minutos)

### Definición

**Automated Machine Learning (AutoML)** es un proceso que automatiza las tareas complejas y repetitivas del desarrollo de modelos de Machine Learning.

### ¿Qué automatiza AutoML?

1. **Preparación de datos**
   - Limpieza de datos
   - Manejo de valores faltantes
   - Normalización y escalado
   - Codificación de variables categóricas

2. **Selección de algoritmos**
   - Prueba múltiples algoritmos diferentes
   - Compara rendimiento automáticamente

3. **Ingeniería de características (Feature Engineering)**
   - Crea nuevas características
   - Transforma variables existentes
   - Selecciona características relevantes

4. **Ajuste de hiperparámetros**
   - Optimiza configuración de cada algoritmo
   - Encuentra la mejor combinación de parámetros

5. **Selección del mejor modelo**
   - Compara todos los modelos generados
   - Elige el mejor basado en métricas definidas

### ¿Cuándo usar AutoML?

✅ **USA AutoML cuando:**

- No eres experto en Machine Learning
- Quieres prototipar rápidamente
- Necesitas comparar múltiples algoritmos eficientemente
- Tienes datos estructurados (en forma de tabla)
- Quieres una línea base para mejorar después
- Tienes tiempo/recursos limitados

❌ **NO uses AutoML cuando:**

- Necesitas control total y granular del proceso
- Trabajas con datos muy complejos o no estructurados
- Tienes requisitos muy específicos del modelo
- Necesitas arquitecturas de deep learning personalizadas
- El problema requiere técnicas muy especializadas

---

## 📖 PARTE 2: Tipos de tareas en AutoML (20 minutos)

Azure AutoML soporta tres tipos principales de tareas:

### 1. Classification (Clasificación) 🏷️

**¿Qué es?**

- Predice a qué categoría o clase pertenece algo
- La variable objetivo es categórica

**Ejemplos:**

- Spam o No spam
- Fraude o No fraude
- Tipo de flor (setosa, versicolor, virginica)
- Riesgo del paciente (bajo, medio, alto)

**Métricas principales:**

- **Accuracy:** % de predicciones correctas
- **Precision:** De los positivos predichos, cuántos son realmente positivos
- **Recall:** De todos los positivos reales, cuántos detectamos
- **F1 Score:** Media armónica de Precision y Recall
- **AUC:** Área bajo la curva ROC

### 2. Regression (Regresión) 📈

**¿Qué es?**

- Predice un valor numérico continuo
- La variable objetivo es numérica

**Ejemplos:**

- Precio de una casa
- Temperatura futura
- Número de ventas
- Edad de una persona
- Consumo energético

**Métricas principales:**

- **RMSE (Root Mean Squared Error):** Raíz del error cuadrático medio
- **MAE (Mean Absolute Error):** Error absoluto medio
- **R² (R-squared):** Coeficiente de determinación (0-1)
- **MAPE (Mean Absolute Percentage Error):** Error porcentual

### 3. Time Series Forecasting (Predicción de series temporales) 📊

**¿Qué es?**

- Predice valores futuros basándose en datos históricos con componente temporal
- Considera patrones temporales, estacionalidad, tendencias

**Ejemplos:**

- Ventas futuras del próximo mes
- Demanda energética de mañana
- Precio futuro de acciones
- Tráfico web esperado
- Demanda de inventario

**Métricas principales:**

- **RMSE:** Raíz del error cuadrático medio
- **MAPE:** Error porcentual absoluto medio
- **MAE:** Error absoluto medio

**Características especiales:**

- Maneja estacionalidad
- Detecta tendencias
- Requiere configurar horizonte de tiempo
- Puede incluir características de calendario (día, mes, año)

---

## 📖 PARTE 3: Proceso de AutoML en Azure (25 minutos)

### Flujo completo de trabajo

```
1. Crear experimento AutoML
   ↓
2. Configurar datos
   ↓
3. Seleccionar compute
   ↓
4. Configurar parámetros del experimento
   ↓
5. Definir validación
   ↓
6. Ejecutar experimento
   ↓
7. Revisar resultados y seleccionar modelo
   ↓
8. Desplegar modelo (opcional)
```

### Paso 1: Crear experimento AutoML

**En Azure ML Studio:**

```
Azure ML Studio → Automated ML → + New Automated ML job
```

O mediante código Python:

```python
from azure.ai.ml import automl

classification_job = automl.classification(
    compute="cpu-cluster",
    experiment_name="mi-experimento-automl",
    training_data=my_training_data,
    target_column_name="label",
    primary_metric="accuracy"
)
```

### Paso 2: Configurar datos

**Opciones de datos:**

- Subir dataset local (CSV, Parquet, JSON)
- Conectar a Azure Blob Storage
- Usar datos de datastore registrado
- Conectar a Azure SQL Database

**Configuración importante:**

- **Target column:** Columna que quieres predecir
- **Task type:** Classification, Regression o Forecasting
- **Training data:** Datos de entrenamiento
- **Validation data** (opcional): Datos de validación separados

### Paso 3: Configurar compute

**Opciones:**

- **Compute cluster:** Para entrenamientos largos y paralelos
- **Compute instance:** Para experimentos pequeños

**Configuración:**

- **VM size:** Standard_DS3_v2, Standard_DS12_v2, etc.
- **Min nodes:** Nodos mínimos (generalmente 0)
- **Max nodes:** Nodos máximos (ej: 4, 6)
- **Idle seconds:** Tiempo antes de escalar a cero

### Paso 4: Configurar experimento

**Primary metric (Métrica principal):**

Para **Classification:**

- Accuracy
- AUC weighted
- Precision score weighted
- Recall score weighted

Para **Regression:**

- Normalized root mean squared error
- R2 score
- Normalized mean absolute error

Para **Forecasting:**

- Normalized root mean squared error
- Normalized mean absolute error

**Exit criterion (Criterio de salida):**

- **Training job time (hours):** Tiempo máximo del experimento
  - Ejemplo: 1 hora, 3 horas, 12 horas
- **Metric score threshold:** Parar si alcanza X score
  - Ejemplo: Accuracy ≥ 0.95

**Concurrency (Concurrencia):**

- **Max concurrent iterations:** Ejecuciones en paralelo
  - Depende del número de nodos del cluster
  - Ejemplo: 4 nodos = máximo 4 iteraciones paralelas

### Paso 5: Configurar validación

**Opciones de validación:**

**1. Cross-validation (Validación cruzada):**

- K-fold cross-validation
- Típicamente 5-fold o 10-fold
- Divide datos en K partes
- Entrena K veces usando diferentes partes como validación

**2. Validation data (Datos de validación):**

- Proporcionar un conjunto de validación separado
- Porcentaje del dataset (ej: 20%)
- Dataset completamente separado

**3. Train-validation split:**

- Proporción de datos para entrenamiento vs validación
- Típicamente 80-20 o 70-30

### Paso 6: Ejecutar y esperar

**Lo que hace AutoML durante la ejecución:**

1. **Preprocesa los datos**
   - Imputa valores faltantes
   - Codifica variables categóricas
   - Normaliza/escala características

2. **Prueba múltiples algoritmos**
   - Ejecuta diferentes algoritmos en paralelo
   - Ajusta hiperparámetros de cada uno

3. **Genera métricas**
   - Calcula métricas de rendimiento
   - Crea gráficos de comparación

4. **Crea modelos ensemble** (opcional)
   - Combina los mejores modelos
   - Voting ensemble o Stack ensemble

5. **Selecciona el mejor**
   - Basado en la primary metric
   - Guarda el modelo ganador

**Tiempo de ejecución:**

- Depende del tamaño de datos
- Número de algoritmos a probar
- Configuración de exit criterion
- Recursos de compute

### Paso 7: Revisar resultados

**En el portal verás:**

- **Best model:** Modelo con mejor métrica
- **All models:** Lista de todos los modelos probados
- **Metrics:** Gráficos de rendimiento
- **Explanations:** Explicabilidad del modelo
- **Fairness:** Métricas de equidad (opcional)

---

## 📖 PARTE 4: Algoritmos que prueba AutoML (15 minutos)

### Para Classification (Clasificación)

1. **Logistic Regression**
   - Simple, rápido
   - Bueno como baseline

2. **Decision Trees**
   - Fácil de interpretar
   - Puede hacer overfitting

3. **Random Forest**
   - Ensemble de árboles
   - Robusto, menos overfitting

4. **Gradient Boosting**
   - Muy potente
   - Puede requerir más tiempo

5. **LightGBM**
   - Gradient boosting optimizado
   - Rápido y eficiente

6. **XGBoost**
   - Gradient boosting extremo
   - Muy popular en competiciones

7. **Support Vector Machines (SVM)**
   - Bueno para clasificación binaria
   - Funciona bien en alta dimensionalidad

8. **Naive Bayes**
   - Rápido, simple
   - Bueno para texto

9. **K-Nearest Neighbors (KNN)**
   - Simple, basado en similitud
   - Lento con muchos datos

### Para Regression (Regresión)

1. **Linear Regression**
   - Modelo más simple
   - Baseline estándar

2. **Decision Tree Regressor**
   - No asume linealidad
   - Interpretable

3. **Random Forest Regressor**
   - Ensemble de árboles
   - Robusto

4. **Gradient Boosting Regressor**
   - Muy preciso
   - Requiere más recursos

5. **LightGBM Regressor**
   - Optimizado para velocidad
   - Maneja grandes datasets

6. **XGBoost Regressor**
   - Alto rendimiento
   - Muy usado

7. **ElasticNet**
   - Regresión con regularización
   - Bueno cuando hay multicolinealidad

8. **Lasso / Ridge**
   - Variantes de regresión lineal
   - Con regularización L1/L2

### Para Time Series Forecasting

- **ARIMA** (AutoRegressive Integrated Moving Average)
- **Prophet** (de Facebook)
- **ForecastTCN**
- Combinación de algoritmos de regresión con features temporales

### Combinaciones que prueba AutoML

AutoML no solo prueba algoritmos, también prueba:

1. **Diferentes hiperparámetros**
   - Learning rate
   - Número de árboles
   - Profundidad máxima
   - Etc.

2. **Diferentes técnicas de preprocesamiento**
   - Normalización vs estandarización
   - PCA (reducción dimensionalidad)
   - Selección de características

3. **Diferentes configuraciones**
   - Con/sin balanceo de clases
   - Diferentes encodings para categorías

---

## 🔑 CONCEPTOS CLAVE PARA EL EXAMEN

### 1. Guardrails (Barandillas de seguridad)

**Explicability (Explicabilidad):**

- AutoML genera explicaciones automáticamente
- Muestra qué características son más importantes
- Feature importance global y local
- Ayuda a entender decisiones del modelo

**Fairness (Equidad):**

- Evalúa si el modelo es justo
- Métricas de disparidad entre grupos
- Identifica posibles sesgos
- Integrado en Azure ML Studio

**Responsible AI (IA Responsable):**

- Transparencia
- Inclusión
- Equidad
- Confiabilidad y seguridad
- Privacidad y seguridad
- Responsabilidad

### 2. Featurization (Caracterización)

**¿Qué es?**
Transformación automática de datos crudos en características útiles para el modelo.

**Opciones en AutoML:**

**a) Automatic (Automático):**

- AutoML decide qué transformaciones aplicar
- Basado en el tipo de datos
- Recomendado para principiantes

**b) Custom (Personalizado):**

- Tú especificas transformaciones
- Para usuarios avanzados
- Más control

**c) Off (Desactivado):**

- Sin transformaciones automáticas
- Solo si ya preprocesaste los datos

**Transformaciones comunes:**

- Imputación de valores faltantes
- One-hot encoding para categóricas
- Normalización/escalado
- Ingeniería de características temporales
- Detección y manejo de outliers

### 3. Early Stopping (Parada temprana)

**¿Qué es?**
Técnica que detiene el entrenamiento si no hay mejora significativa después de X iteraciones.

**Beneficios:**

- Ahorra tiempo de compute
- Reduce costos
- Evita sobreentrenamiento (overfitting)

**Cómo funciona:**

```
Si después de 10 iteraciones no mejora la métrica:
  → Para el experimento
  → Usa el mejor modelo encontrado hasta ahora
```

**Configuración:**

- **Enable early termination:** Sí/No
- **Evaluation interval:** Cada cuántas iteraciones evaluar
- **Delay evaluation:** Iteraciones mínimas antes de evaluar

### 4. Ensemble Models (Modelos ensemble)

**¿Qué es?**
Combinación de múltiples modelos para obtener mejores predicciones que cualquier modelo individual.

**Tipos en AutoML:**

**a) Voting Ensemble:**

- Combina predicciones mediante votación
- Para clasificación: mayoría de votos
- Para regresión: promedio de predicciones
- Cada modelo tiene un peso

**b) Stack Ensemble:**

- Más sofisticado
- Un "meta-modelo" aprende a combinar otros modelos
- Dos niveles: modelos base + meta-modelo
- Generalmente más preciso que voting

**Ventajas:**

- Reduce varianza
- Más robusto
- Mejor generalización
- A menudo el mejor modelo de AutoML es ensemble

**Configuración:**

- **Enable stack ensemble:** Sí/No
- **Stack ensemble iterations:** Número de iteraciones para ensemble

### 5. Blocked Algorithms (Algoritmos bloqueados)

**¿Para qué?**
Puedes excluir ciertos algoritmos que no quieres que AutoML pruebe.

**Razones para bloquear:**

- Algoritmo muy lento para tu dataset
- No apropiado para tu tipo de problema
- Restricciones de compliance
- Preferencias del equipo

**Ejemplo:**

```python
blocked_models = ['XGBoostClassifier', 'RandomForest']
```

### 6. Allowed Algorithms (Algoritmos permitidos)

**¿Para qué?**
Especificar exactamente qué algoritmos quieres que AutoML pruebe.

**Uso típico:**

- Ya sabes qué algoritmos funcionan bien
- Reducir tiempo de experimentación
- Enfocarse en familia específica de algoritmos

---

## ✅ AUTOEVALUACIÓN (10 minutos)

### Pregunta 1

**¿Qué es AutoML?**

<details>
<summary>Ver respuesta</summary>

Un proceso automatizado que:

- Prueba múltiples algoritmos de Machine Learning
- Preprocesa los datos automáticamente
- Ajusta hiperparámetros
- Selecciona el mejor modelo basándose en una métrica especificada

Todo esto sin requerir experiencia profunda en ML.

</details>

---

### Pregunta 2

**¿Qué tres tipos de tareas soporta AutoML en Azure?**

<details>
<summary>Ver respuesta</summary>

1. **Classification** (Clasificación) - Predecir categorías
2. **Regression** (Regresión) - Predecir valores numéricos
3. **Time Series Forecasting** - Predecir valores futuros con componente temporal
</details>

---

### Pregunta 3

**¿Qué es la "primary metric" en un experimento AutoML?**

<details>
<summary>Ver respuesta</summary>

La métrica principal que AutoML usará para:

- Evaluar el rendimiento de cada modelo
- Comparar diferentes modelos entre sí
- Seleccionar el mejor modelo

Ejemplos:

- Accuracy para clasificación
- RMSE para regresión
- AUC weighted para clasificación desbalanceada
</details>

---

### Pregunta 4

**¿Qué significa "exit criterion" (criterio de salida)?**

<details>
<summary>Ver respuesta</summary>

Condiciones que determinan cuándo AutoML debe parar de entrenar modelos:

1. **Training job time:** Tiempo máximo del experimento (ej: 1 hora)
2. **Metric score threshold:** Parar si alcanza cierto score (ej: Accuracy ≥ 0.95)

Cuando se cumple cualquiera, AutoML detiene la ejecución.

</details>

---

### Pregunta 5

**¿Puede AutoML crear modelos ensemble? ¿Qué tipos?**

<details>
<summary>Ver respuesta</summary>

**Sí**, AutoML puede crear modelos ensemble:

1. **Voting Ensemble:**
   - Combina predicciones por votación/promedio
   - Cada modelo tiene un peso

2. **Stack Ensemble:**
   - Un meta-modelo aprende a combinar otros modelos
   - Generalmente más preciso
   - Dos niveles: modelos base + meta-modelo

Los ensemble a menudo son los mejores modelos de AutoML.

</details>

---

### Pregunta 6

**¿Qué es "featurization" en AutoML?**

<details>
<summary>Ver respuesta</summary>

Transformación automática de datos crudos en características útiles para el modelo.

**Modos:**

- **Automatic:** AutoML decide transformaciones
- **Custom:** Usuario especifica transformaciones
- **Off:** Sin transformaciones automáticas

**Include:**

- Imputación de valores faltantes
- One-hot encoding
- Normalización/escalado
- Feature engineering
</details>

---

### Pregunta 7

**¿Qué es "early stopping" y por qué es útil?**

<details>
<summary>Ver respuesta</summary>

Técnica que para el entrenamiento si no hay mejora significativa después de X iteraciones.

**Beneficios:**

- ✅ Ahorra tiempo de compute
- ✅ Reduce costos de Azure
- ✅ Evita overfitting
- ✅ Optimiza uso de recursos

**Ejemplo:** Si después de 10 iteraciones la métrica no mejora, para el experimento.

</details>

---

### Pregunta 8

**Nombra 3 algoritmos que AutoML prueba para clasificación.**

<details>
<summary>Ver respuesta</summary>

1. **Logistic Regression** - Simple, rápido, buen baseline
2. **Random Forest** - Ensemble de árboles, robusto
3. **LightGBM** - Gradient boosting optimizado, muy eficiente

Otros: XGBoost, Decision Trees, SVM, Naive Bayes, KNN

</details>

---

### Pregunta 9

**¿Qué diferencia hay entre "cross-validation" y "validation data"?**

<details>
<summary>Ver respuesta</summary>

**Cross-validation (K-fold):**

- Divide datos en K partes
- Entrena K veces, cada vez usando parte diferente como validación
- Más robusto, usa todos los datos
- Ejemplo: 5-fold CV

**Validation data:**

- Conjunto separado de datos para validación
- Puede ser un porcentaje (ej: 20%) o dataset externo
- Más simple, más rápido
- Datos de validación nunca usados para entrenamiento
</details>

---

### Pregunta 10

**¿Qué son los "guardrails" en AutoML?**

<details>
<summary>Ver respuesta</summary>

Características de seguridad y responsabilidad integradas:

1. **Explicability:** Genera explicaciones del modelo automáticamente
2. **Fairness:** Evalúa equidad y detecta sesgos
3. **Responsible AI:** Integra principios de IA responsable

Ayudan a crear modelos:

- Transparentes
- Justos
- Confiables
- Éticos
</details>

---

## 📝 FLASHCARDS para crear HOY

Agrega estas tarjetas a tu mazo de Anki:

### Tarjeta 1

**Frente:** ¿Qué es AutoML?  
**Reverso:** Proceso automatizado que prueba múltiples algoritmos, preprocesa datos, ajusta hiperparámetros y selecciona el mejor modelo basándose en una métrica especificada.

### Tarjeta 2

**Frente:** Tipos de tareas que soporta AutoML en Azure  
**Reverso:** 1) Classification, 2) Regression, 3) Time Series Forecasting

### Tarjeta 3

**Frente:** ¿Qué es Primary Metric en AutoML?  
**Reverso:** Métrica principal usada para evaluar, comparar y seleccionar el mejor modelo (ej: Accuracy, RMSE, AUC)

### Tarjeta 4

**Frente:** ¿Qué es Exit Criterion?  
**Reverso:** Condición para parar experimento AutoML (tiempo límite o umbral de métrica alcanzado)

### Tarjeta 5

**Frente:** ¿Qué es Featurization?  
**Reverso:** Transformación automática de datos crudos en características útiles. Modos: Automatic, Custom, Off

### Tarjeta 6

**Frente:** Tipos de Ensemble Models en AutoML  
**Reverso:** 1) Voting Ensemble (combina por votación/promedio), 2) Stack Ensemble (meta-modelo aprende a combinar)

### Tarjeta 7

**Frente:** ¿Qué es Early Stopping?  
**Reverso:** Para experimento si no hay mejora en X iteraciones. Ahorra tiempo, costo y evita overfitting

### Tarjeta 8

**Frente:** Algoritmos de clasificación en AutoML (3 ejemplos)  
**Reverso:** Logistic Regression, Random Forest, LightGBM, XGBoost, Decision Trees, SVM

### Tarjeta 9

**Frente:** Algoritmos de regresión en AutoML (3 ejemplos)  
**Reverso:** Linear Regression, Random Forest Regressor, LightGBM, XGBoost, ElasticNet

### Tarjeta 10

**Frente:** ¿Qué es Cross-validation (K-fold)?  
**Reverso:** Técnica que divide datos en K partes, entrena K veces usando diferentes partes como validación. Más robusto.

### Tarjeta 11

**Frente:** Guardrails en AutoML  
**Reverso:** 1) Explicability (explicaciones automáticas), 2) Fairness (métricas de equidad), 3) Responsible AI (principios éticos)

### Tarjeta 12

**Frente:** ¿Qué automatiza AutoML? (5 cosas)  
**Reverso:** 1) Preparación datos, 2) Selección algoritmos, 3) Feature engineering, 4) Ajuste hiperparámetros, 5) Selección mejor modelo

### Tarjeta 13

**Frente:** Métricas principales para Classification  
**Reverso:** Accuracy, Precision, Recall, F1 Score, AUC

### Tarjeta 14

**Frente:** Métricas principales para Regression  
**Reverso:** RMSE (Root Mean Squared Error), MAE (Mean Absolute Error), R² (R-squared)

### Tarjeta 15

**Frente:** ¿Cuándo NO usar AutoML?  
**Reverso:** Cuando necesitas control total, datos muy complejos, requisitos muy específicos, o arquitecturas deep learning personalizadas

---

## 🎯 RESUMEN DEL DÍA

### Lo que aprendiste hoy:

✅ **Concepto de AutoML**

- Proceso automatizado de ML
- Qué automatiza (5 pasos principales)
- Cuándo usar y cuándo no

✅ **Tipos de tareas**

- Classification (categorías)
- Regression (valores numéricos)
- Time Series Forecasting (predicción temporal)

✅ **Proceso completo**

- 7 pasos desde creación hasta despliegue
- Configuración de datos, compute, experimento
- Opciones de validación

✅ **Algoritmos**

- Algoritmos para clasificación (8+)
- Algoritmos para regresión (8+)
- Algoritmos para forecasting

✅ **Conceptos clave**

- Ensemble models (voting y stack)
- Featurization (automatic, custom, off)
- Early stopping
- Guardrails (explicability, fairness)
- Primary metric y exit criterion

---

## 📊 Tu progreso en la Semana 2

```
Semana 2: Machine Learning en profundidad
├── ✅ Lunes 10: Tipos de ML profundo
├── ✅ Martes 11: Regresión y métricas
├── ✅ Miércoles 12: Clasificación y métricas
├── ✅ Jueves 13: Azure ML workspace
├── ✅ Viernes 14: AutoML (HOY - COMPLETADO)
├── 📅 Sábado 15: Lab - Crear primer modelo con AutoML
└── 📅 Domingo 16: Descanso
```

**¡Ya completaste el 71% de la Semana 2!** 🎉

---

## 📅 MAÑANA (Sábado 15 de noviembre)

**Tema:** Lab práctico - Crear tu primer modelo con AutoML

**Lo que harás:**

- 🔬 Crear experimento AutoML real en Azure ML Studio
- 🎯 Entrenar modelo de clasificación o regresión
- 📊 Analizar resultados y métricas
- 🚀 Entender cómo desplegar el modelo

**Duración:** 2-3 horas (lab práctico hands-on)

---

## 💡 CONSEJOS PARA HOY

1. **Crea las flashcards inmediatamente** después de leer cada sección
2. **No memorices todo de golpe** - enfócate en entender conceptos
3. **Relaciona con días anteriores:**
   - AutoML usa los algoritmos de clasificación/regresión que ya viste
   - Usa las métricas que aprendiste el martes/miércoles
   - Se ejecuta en el Azure ML workspace del jueves
4. **Si algo no queda claro**, apúntalo para preguntarme
5. **Mañana lo aplicarás en práctica**, así que no te preocupes si no dominas todo hoy

---

## 🎓 PARA EL EXAMEN - PREGUNTAS TÍPICAS

**Ejemplo 1:**
_"¿Qué característica de Azure Machine Learning permite probar automáticamente múltiples algoritmos y seleccionar el mejor modelo?"_

- **Respuesta:** Automated ML (AutoML)

**Ejemplo 2:**
_"Estás creando un modelo de clasificación y quieres que AutoML pare si alcanza 95% de accuracy. ¿Qué configuración usas?"_

- **Respuesta:** Exit criterion con metric score threshold = 0.95

**Ejemplo 3:**
_"¿Qué tipo de modelo combina predicciones de múltiples modelos usando votación o stacking?"_

- **Respuesta:** Ensemble model

**Ejemplo 4:**
_"¿Qué configuración de AutoML transforma automáticamente variables categóricas y maneja valores faltantes?"_

- **Respuesta:** Featurization (en modo Automatic)

**Ejemplo 5:**
_"Necesitas predecir las ventas de los próximos 30 días basándote en datos históricos. ¿Qué tipo de tarea de AutoML usas?"_

- **Respuesta:** Time Series Forecasting

---

## ✅ CHECKLIST DE HOY

Antes de terminar el día, asegúrate de:

- [ ] Leer todo el material (1h 30min)
- [ ] Entender los 3 tipos de tareas de AutoML
- [ ] Conocer el proceso de 7 pasos
- [ ] Identificar al menos 5 algoritmos que prueba AutoML
- [ ] Comprender qué son ensemble models
- [ ] Entender featurization, early stopping y guardrails
- [ ] Crear las 15 flashcards en Anki
- [ ] Completar la autoevaluación (10 preguntas)
- [ ] Repasar brevemente los días anteriores de la semana

---

## 🚀 MOTIVACIÓN

**¡Excelente progreso!** Ya llevas:

- ✅ 1 semana completa
- ✅ 5 días de la Semana 2

**Faltan solo:**

- 📅 2 días para completar Semana 2
- 📅 4 semanas más para el examen
- 📅 30 días aproximadamente para tu certificación AI-900

**Estás siendo muy consistente. ¡Sigue así!** 💪

---

## 📞 ¿NECESITAS AYUDA?

Si tienes dudas sobre:

- Conceptos que no quedaron claros
- Diferencias entre algoritmos
- Cómo funciona algo en Azure
- Preguntas de práctica adicionales

**¡No dudes en preguntar!** Estoy aquí para ayudarte a conseguir esa certificación.

---

**¡Que tengas un excelente estudio hoy Viernes!** 📚💻

**Nos vemos mañana para el lab práctico.** 🔬🚀

---

_Última actualización: Viernes 14 de noviembre 2025_  
_Semana 2 de 6 - Día 5 de 7_
