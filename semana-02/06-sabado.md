# 🔬 SÁBADO 15 NOV - SEMANA 2: LAB PRÁCTICO - AutoML

**Fecha:** Sábado 15 de noviembre 2025  
**Semana:** 2 de 6  
**Tema:** Laboratorio práctico - Crear tu primer modelo con AutoML  
**Duración:** 2-3 horas (hands-on)

---

## 🎯 Objetivos del laboratorio

Al finalizar hoy habrás:

- ✅ Creado un experimento AutoML completo en Azure ML Studio
- ✅ Configurado datos, compute y parámetros del experimento
- ✅ Entrenado un modelo de clasificación o regresión
- ✅ Analizado resultados y métricas
- ✅ Comparado diferentes modelos
- ✅ Entendido cómo interpretar las salidas de AutoML
- ✅ Visto en práctica TODO lo aprendido esta semana

---

## 📋 ANTES DE EMPEZAR

### ✅ Pre-requisitos

**Necesitas tener:**

- [ ] Cuenta de Azure activa (gratuita o de pago)
- [ ] Azure ML Workspace creado (lo hiciste el jueves)
- [ ] Navegador web actualizado
- [ ] Conexión a internet estable

**Si NO tienes workspace:**

- Sigue las instrucciones del Jueves para crearlo
- Toma 5-10 minutos

---

### 🧠 Conceptos que aplicarás hoy

**De toda la semana:**

- Lunes: Tipos de ML (supervisado/no supervisado)
- Martes: Métricas de regresión (RMSE, R², MAE)
- Miércoles: Métricas de clasificación (Accuracy, Precision, Recall, AUC)
- Jueves: Azure ML Workspace, compute, datasets
- Viernes: AutoML (ensemble, featurization, early stopping)

**¡Hoy pondrás TODO en práctica!** 💪

---

## 🔬 LABORATORIO: Opción A - Clasificación (Diabetes)

### Escenario del proyecto

**Problema de negocio:**
Predecir si un paciente tiene diabetes basándose en datos médicos.

**Tipo de ML:** Clasificación binaria (Sí diabetes / No diabetes)

**Dataset:** Pima Indians Diabetes Dataset

- 768 pacientes
- 8 características médicas
- Variable objetivo: diabetes (0=No, 1=Sí)

---

## 📝 PASO 1: Preparar el dataset (15 minutos)

### 1.1 Descargar el dataset

**Opción A: Desde Azure ML Studio**

```
1. Ve a Azure ML Studio (ml.azure.com)
2. Selecciona tu workspace
3. En el menú izquierdo → Data
4. Busca "diabetes" en sample datasets
```

**Opción B: Subir manualmente**

**URL del dataset:**

```
https://raw.githubusercontent.com/jbrownlee/Datasets/master/pima-indians-diabetes.data.csv
```

**Columnas:**

1. Pregnancies (embarazos)
2. Glucose (glucosa)
3. BloodPressure (presión arterial)
4. SkinThickness (grosor piel)
5. Insulin (insulina)
6. BMI (índice masa corporal)
7. DiabetesPedigreeFunction (función pedigrí)
8. Age (edad)
9. Outcome (resultado: 0=No diabetes, 1=Sí diabetes)

---

### 1.2 Crear dataset en Azure ML

```
Pasos en Azure ML Studio:

1. Menú izquierdo → Data → Create

2. Configuración básica:
   Name: diabetes-dataset
   Type: Tabular
   Description: Pima Indians Diabetes data

3. Data source:
   - From web files
   - Web URL: [pega la URL de arriba]

4. Settings:
   - File format: Delimited
   - Delimiter: Comma
   - Encoding: UTF-8
   - Column headers: No headers (usaremos nombres por defecto)
   - Skip rows: 0

5. Schema:
   Renombrar columnas:
   - Column1 → Pregnancies
   - Column2 → Glucose
   - Column3 → BloodPressure
   - Column4 → SkinThickness
   - Column5 → Insulin
   - Column6 → BMI
   - Column7 → DiabetesPedigreeFunction
   - Column8 → Age
   - Column9 → Outcome

6. Review → Create
```

**⏱️ Tiempo:** ~5 minutos

---

### 1.3 Explorar el dataset

```
1. En Data, click en tu dataset "diabetes-dataset"

2. Tab "Explore":
   - Observa las primeras filas
   - Revisa distribución de Outcome (0 y 1)
   - Nota valores estadísticos

3. Tab "Profile":
   - Genera profile si no existe
   - Observa:
     * Missing values (valores faltantes)
     * Distribuciones
     * Outliers potenciales

📊 Observaciones esperadas:
- ~500 pacientes sin diabetes (Outcome=0)
- ~268 pacientes con diabetes (Outcome=1)
- Clases ligeramente desbalanceadas
```

---

## 🤖 PASO 2: Configurar experimento AutoML (20 minutos)

### 2.1 Crear nuevo experimento AutoML

```
1. Menú izquierdo → Automated ML

2. Click "+ New Automated ML job"

3. Select dataset:
   - Elige "diabetes-dataset"
   - Next

4. Configure job:
   Experiment name: diabetes-classification-exp
   New experiment name: diabetes-prediction
   Target column: Outcome
   Compute target: [selecciona o crea compute cluster]
```

---

### 2.2 Configurar compute (si no tienes)

**Si NO tienes compute cluster:**

```
Create new compute:

1. Click "+ New"

2. Configuración:
   Compute name: cpu-cluster-automl
   VM type: CPU
   VM priority: Dedicated
   VM size: Standard_DS3_v2 (4 cores, 14GB RAM)

3. Scaling:
   Min nodes: 0 (ahorro de costos)
   Max nodes: 4 (paralelización)
   Idle seconds: 120 (escala a 0 después de 2 min inactivo)

4. Create → espera 3-5 minutos

💡 Esto escala a 0 cuando no se usa = NO PAGAS cuando inactivo
```

**Si YA tienes compute:**

- Selecciónalo de la lista

---

### 2.3 Configurar task y settings

```
5. Task type: Classification ← IMPORTANTE

6. Additional configuration settings:

   Primary metric: AUC_weighted
   (porque clases están ligeramente desbalanceadas)

   Explain best model: ✓ (ver feature importance)

   Blocked algorithms: (ninguno por ahora)

   Exit criterion:
   - Training job time (hours): 0.5 (30 minutos)
   - Metric score threshold: 0.90 (para si AUC ≥ 0.90)

   Concurrency:
   - Max concurrent iterations: 4
   (igual al max nodes del cluster)

7. Validation and test:

   Validation type: k-fold cross-validation
   Number of cross validations: 5

   Test dataset: None (usaremos validation)

8. Next
```

---

### 2.4 Revisar y enviar

```
9. Review:
   - Verifica toda la configuración
   - Task: Classification ✓
   - Primary metric: AUC_weighted ✓
   - Target: Outcome ✓
   - Timeout: 0.5 hours ✓

10. Submit training job

11. Verás:
    "Submitting AutoML job..."
    "Job submitted successfully"

12. Click "View job" o ve a:
    Automated ML → diabetes-classification-exp
```

**⏱️ El entrenamiento tomará 15-30 minutos**

---

## ⏳ MIENTRAS ESPERA EL ENTRENAMIENTO (15-30 min)

### Actividades durante la espera:

**1. Observa el progreso en tiempo real:**

```
En la página del experimento verás:
- Status: Running
- Child runs: Modelos probados hasta ahora
- Best model so far: Mejor modelo actual
- Best metric: AUC actual del mejor modelo
```

**2. Explora los modelos que va probando:**

```
Tab "Models":
- Ve la lista de algoritmos probados
- Observa métricas de cada uno
- Nota cuáles son ensemble
```

**Algoritmos típicos que probará:**

- LogisticRegression
- RandomForest
- LightGBM
- XGBoostClassifier
- VotingEnsemble ← Probablemente el ganador
- StackEnsemble

**3. Repasa conceptos de la semana:**

- ¿Qué es un ensemble model?
- ¿Por qué AUC_weighted es buena métrica aquí?
- ¿Qué esperas ver en la confusion matrix?

**4. Prepara preguntas:**

- ¿Qué modelo esperas que gane?
- ¿Será importante Precision o Recall?
- ¿Cómo interpretarás los resultados?

---

## 📊 PASO 3: Analizar resultados (30 minutos)

### 3.1 Ver el mejor modelo

**Cuando termine el experimento:**

```
1. Status cambia a: "Completed"

2. Tab "Overview":
   - Best model algorithm: [ej: VotingEnsemble]
   - Best model AUC_weighted: [ej: 0.8542]

3. Click en "View best model"
```

---

### 3.2 Explorar métricas del modelo

```
En la página del Best Model:

Tab "Metrics":

📊 Classification Metrics:
- Accuracy: ¿Qué % de predicciones correctas?
- AUC weighted: ¿Capacidad de discriminación?
- Precision: ¿Confiable cuando dice "diabetes"?
- Recall: ¿Detecta todos los casos de diabetes?
- F1 score: ¿Balance entre Precision y Recall?

🔍 Ejemplo de resultados esperados:
- Accuracy: ~0.77 (77%)
- AUC: ~0.85 (85%)
- Precision: ~0.72 (72%)
- Recall: ~0.65 (65%)
- F1: ~0.68 (68%)
```

---

### 3.3 Analizar Confusion Matrix

```
Tab "Metrics" → Scroll down → Confusion Matrix

Ejemplo de matriz esperada:

                  Predicted
              No diabetes  Diabetes
Actual  No        420        80
        Diabetes   95       173

📊 Interpretación:

True Negatives (TN): 420
- Correctamente identificados SIN diabetes

True Positives (TP): 173
- Correctamente identificados CON diabetes

False Positives (FP): 80
- Error: dijo diabetes pero NO la tienen

False Negatives (FN): 95
- PELIGROSO: dijo NO diabetes pero SÍ la tienen
```

---

### 3.4 Calcular métricas manualmente

**🧮 Ejercicio práctico:**

Usando la confusion matrix del ejemplo:

```
TN = 420, FP = 80
FN = 95,  TP = 173
Total = 768

1. Accuracy:
   (420 + 173) / 768 = 593 / 768 = 0.772 = 77.2%

2. Precision:
   173 / (173 + 80) = 173 / 253 = 0.684 = 68.4%

3. Recall:
   173 / (173 + 95) = 173 / 268 = 0.646 = 64.6%

4. F1:
   2 × (0.684 × 0.646) / (0.684 + 0.646) = 0.664 = 66.4%
```

**💡 Verifica que coincidan con las métricas mostradas en Azure ML**

---

### 3.5 Analizar ROC Curve

```
Tab "Metrics" → Scroll down → ROC Curve

📈 Observa:

1. La curva debe estar por encima de la línea diagonal
2. AUC (área sombreada) debería ser ~0.85
3. Cuanto más arriba-izquierda, mejor

Interpretación AUC = 0.85:
"El modelo tiene 85% de probabilidad de darle mayor
score a un paciente con diabetes que a uno sin diabetes"

→ Es un modelo BUENO (0.8-0.9 es muy bueno)
```

---

### 3.6 Ver Feature Importance

```
Tab "Explanations" (si activaste "Explain best model")

📊 Features más importantes (ejemplo típico):

1. Glucose: 0.28 (28%) ← MÁS IMPORTANTE
2. BMI: 0.18 (18%)
3. Age: 0.15 (15%)
4. DiabetesPedigreeFunction: 0.12 (12%)
5. Pregnancies: 0.10 (10%)
6. BloodPressure: 0.08 (8%)
7. Insulin: 0.05 (5%)
8. SkinThickness: 0.04 (4%)

💡 Interpretación:
- Glucose es el predictor más fuerte
- BMI y Age también muy importantes
- SkinThickness tiene poco poder predictivo
```

---

### 3.7 Comparar múltiples modelos

```
Vuelve al experimento → Tab "Models"

📊 Compara top 3 modelos:

Modelo                  AUC    Accuracy  Precision  Recall
────────────────────────────────────────────────────────
VotingEnsemble         0.854    0.772     0.684    0.646
StackEnsemble          0.851    0.769     0.680    0.643
XGBoostClassifier      0.842    0.765     0.672    0.638
LightGBM               0.838    0.761     0.668    0.635
RandomForest           0.825    0.753     0.655    0.625

🎯 Observaciones:
- Ensembles ganan (VotingEnsemble #1)
- Diferencias pequeñas entre top modelos
- Trade-off entre Precision y Recall visible
```

---

## 🤔 PASO 4: Interpretación de negocio (15 minutos)

### 4.1 ¿Es un buen modelo?

**Contexto médico:**

```
Métricas:
- Recall: 64.6% (detecta 65% de casos de diabetes)
- Precision: 68.4% (68% confiable cuando dice "diabetes")

⚠️ PROBLEMA: Recall bajo

Recall = 64.6% significa:
- De 100 personas CON diabetes
- Solo detectamos 65
- Nos perdemos 35 casos (False Negatives)

En medicina esto es GRAVE:
→ 35 personas con diabetes no diagnosticadas
→ No reciben tratamiento
→ Complicaciones de salud
```

---

### 4.2 ¿Qué podríamos hacer?

**Opciones para mejorar:**

**1. Ajustar el umbral de clasificación:**

```
En vez de umbral = 0.5, usar umbral = 0.3

Efecto:
✅ Aumenta Recall (detectamos más casos)
❌ Disminuye Precision (más falsos positivos)

Trade-off aceptable en medicina:
Mejor tener algunos falsos positivos (confirmar
con más pruebas) que perder casos reales.
```

**2. Recolectar más datos:**

```
- El dataset tiene solo 268 casos de diabetes
- Más datos → mejor modelo
- Especialmente en la clase minoritaria
```

**3. Feature engineering:**

```
- Crear features combinadas (ej: BMI * Age)
- Transformaciones (logaritmos, polinomios)
- Agregar más variables médicas
```

**4. Probar otros algoritmos:**

```
- Deep learning (redes neuronales)
- Modelos especializados en clases desbalanceadas
```

**5. Cambiar primary metric:**

```
En vez de AUC_weighted, usar:
- Recall (para maximizar detección)
- F1_score_weighted (balance)
```

---

### 4.3 Decisión de negocio

**Pregunta clave:**
"¿Qué es más costoso?"

**Opción A: Alta Precision (conservador)**

```
✅ Evitas tratamientos innecesarios
❌ Te pierdes muchos casos reales
```

**Opción B: Alto Recall (agresivo)**

```
✅ Detectas casi todos los casos
❌ Muchas personas sin diabetes reciben diagnóstico falso
```

**En diabetes:**

```
→ Priorizar RECALL

Razón:
- Diabetes no diagnosticada → complicaciones graves
- Falso positivo → hacer más pruebas (confirmar)
- Costo de FN >> Costo de FP
```

---

## 🔄 PASO 5 (OPCIONAL): Repetir experimento optimizado (30 min)

### 5.1 Crear experimento mejorado

**Si quieres mejorar el modelo:**

```
1. New Automated ML job

2. Same dataset: diabetes-dataset

3. Experiment name: diabetes-classification-exp-v2

4. Configure job:
   Target: Outcome
   Compute: cpu-cluster-automl

5. Task: Classification

6. CAMBIOS:
   Primary metric: Recall_score_weighted ← CAMBIO
   (en vez de AUC_weighted)

   Training job time: 1.0 hours ← Más tiempo

   Metric score threshold: 0.75 (75% recall)

   Enable deep learning: ✓ ← NUEVO

7. Submit
```

**Espera:** 30-60 minutos

**Resultado esperado:**

- Mayor Recall (~75-80%)
- Menor Precision (~60-65%)
- Mejor balance para caso médico

---

## 📝 PASO 6: Documentar aprendizajes (15 minutos)

### 6.1 Completa esta evaluación

**Responde en tu cuaderno:**

```
1. ¿Qué tipo de ML usaste? (clasificación/regresión)

2. ¿Qué algoritmo ganó?

3. Métricas del mejor modelo:
   - Accuracy: ____%
   - AUC: ____
   - Precision: ____%
   - Recall: ____%
   - F1: ____%

4. ¿Cuál fue la feature más importante?

5. ¿Es un buen modelo para uso médico? ¿Por qué?

6. ¿Qué métrica priorizarías? ¿Por qué?

7. ¿Qué aprendiste de los ensembles?

8. Si tuvieras más tiempo, ¿qué mejorarías?
```

---

### 6.2 Reflexión final

**Escribe 2-3 párrafos sobre:**

1. **Experiencia práctica:**
   - ¿Fue fácil usar AutoML?
   - ¿Qué te sorprendió?
   - ¿Qué fue más difícil?

2. **Conexión con teoría:**
   - ¿Viste en práctica los conceptos de la semana?
   - ¿Entiendes mejor las métricas ahora?
   - ¿Qué concepto te quedó más claro?

3. **Aplicación futura:**
   - ¿Cómo usarías esto en tu trabajo?
   - ¿Qué otros problemas podrías resolver?

---

## 🔬 LABORATORIO ALTERNATIVO: Opción B - Regresión (OPCIONAL)

**Si prefieres hacer regresión en vez de clasificación:**

### Dataset: Predicción de precios de casas

```
Dataset: California Housing
URL: Disponible en Azure ML samples

Variables:
- MedInc (ingreso medio)
- HouseAge (edad de la casa)
- AveRooms (habitaciones promedio)
- AveBedrms (dormitorios promedio)
- Population (población)
- AveOccup (ocupación promedio)
- Latitude (latitud)
- Longitude (longitud)
Target: MedianHouseValue (precio medio)

Pasos similares pero:
- Task type: Regression
- Primary metric: Normalized root mean squared error
- Métricas: RMSE, MAE, R²
```

---

## ✅ CHECKLIST DEL LABORATORIO

Al final del día, debes haber:

- [ ] Creado dataset en Azure ML
- [ ] Configurado experimento AutoML completo
- [ ] Esperado y monitoreado el entrenamiento
- [ ] Analizado el mejor modelo
- [ ] Interpretado confusion matrix
- [ ] Calculado métricas manualmente
- [ ] Visto ROC curve y AUC
- [ ] Analizado feature importance
- [ ] Comparado múltiples modelos
- [ ] Reflexionado sobre aplicación de negocio
- [ ] Documentado aprendizajes
- [ ] (Opcional) Creado experimento optimizado

---

## 🎯 CONCEPTOS QUE PRACTICASTE HOY

### De la semana completa:

**Lunes - Tipos de ML:**

- ✅ Usaste supervised learning (clasificación)
- ✅ Viste datos etiquetados (Outcome conocido)

**Martes - Regresión:**

- ✅ Si hiciste Opción B, aplicaste RMSE, MAE, R²
- ✅ Entendiste diferencia con clasificación

**Miércoles - Clasificación:**

- ✅ Calculaste Accuracy, Precision, Recall, F1
- ✅ Analizaste confusion matrix en detalle
- ✅ Viste ROC curve y AUC en práctica

**Jueves - Azure ML:**

- ✅ Usaste workspace, compute, datasets
- ✅ Navegaste Azure ML Studio
- ✅ Configuraste recursos

**Viernes - AutoML:**

- ✅ Configuraste experimento completo
- ✅ Estableciste primary metric y exit criterion
- ✅ Viste ensemble models ganar
- ✅ Entendiste featurization automática

---

## 🎓 PREGUNTAS DE REFLEXIÓN

### Técnicas:

1. ¿Por qué VotingEnsemble suele ganar?
2. ¿Cómo afecta el exit criterion al resultado?
3. ¿Por qué AUC es mejor que Accuracy aquí?
4. ¿Qué significa que Glucose sea la feature más importante?
5. ¿Cómo interpretarías un AUC de 0.95?

### De negocio:

6. ¿Usarías este modelo en producción? ¿Por qué?
7. ¿Qué le dirías al doctor sobre Recall del 65%?
8. ¿Cómo balancearías Precision vs Recall en medicina?
9. ¿Qué otros datos pedirías para mejorar el modelo?
10. ¿Cómo explicarías feature importance a un no técnico?

---

## 💡 TROUBLESHOOTING

### Problemas comunes:

**1. "Compute cluster no se crea"**

```
Solución:
- Verifica límites de tu suscripción
- Intenta otra región
- Usa VM size más pequeño (DS2_v2)
```

**2. "Experimento falla inmediatamente"**

```
Solución:
- Verifica que target column esté correcta
- Asegura que no haya errores en dataset
- Revisa logs en la página del experimento
```

**3. "No veo ROC curve"**

```
Solución:
- Solo aparece en clasificación binaria
- Espera a que termine el experimento
- Tab "Metrics" del best model
```

**4. "Feature importance no aparece"**

```
Solución:
- Asegúrate de activar "Explain best model"
- Tab "Explanations" del best model
- Puede tardar unos minutos en generarse
```

**5. "Compute no escala a cero"**

```
Solución:
- Espera 2 minutos (idle seconds: 120)
- Verifica en "Compute" → "Compute clusters"
- Manualmente scale down si es necesario
```

---

## 📊 COMPARACIÓN: TUS RESULTADOS vs ESPERADOS

### Completa esta tabla:

| Métrica        | Esperado       | Tus resultados | ¿Mejor/Peor/Igual? |
| -------------- | -------------- | -------------- | ------------------ |
| Accuracy       | ~77%           | \_\_\_%        | \_\_\_             |
| AUC            | ~0.85          | \_\_\_         | \_\_\_             |
| Precision      | ~68%           | \_\_\_%        | \_\_\_             |
| Recall         | ~65%           | \_\_\_%        | \_\_\_             |
| F1 Score       | ~66%           | \_\_\_%        | \_\_\_             |
| Best Algorithm | VotingEnsemble | \_\_\_         | \_\_\_             |
| Training Time  | 20-30 min      | \_\_\_ min     | \_\_\_             |

**Si tus resultados son diferentes:**

- ✅ Normal, AutoML tiene componente aleatorio
- ✅ Resultados en ±5% son equivalentes
- ✅ Lo importante es entender las métricas

---

## 🚀 PRÓXIMOS PASOS

### Después del laboratorio:

**1. Limpia recursos (IMPORTANTE):**

```
Para evitar costos:

1. Ve a "Compute" → "Compute clusters"
2. Verifica que cluster esté en 0 nodes
3. Si quieres, DELETE el cluster
4. Los experimentos y modelos se conservan
```

**2. Guarda tu notebook (si hiciste anotaciones):**

```
- Captura de pantalla de métricas
- Notas sobre interpretación
- Decisiones que tomaste
```

**3. Practica con otro dataset:**

```
Ideas:
- Titanic (clasificación: sobrevivió/no)
- Boston Housing (regresión: precio casas)
- Iris (clasificación multiclase: 3 flores)
```

---

## 📅 RESUMEN DE LA SEMANA 2

```
Semana 2: Machine Learning en profundidad
├── ✅ Lunes 10: Tipos de ML profundo
├── ✅ Martes 11: Regresión y métricas
├── ✅ Miércoles 12: Clasificación y métricas
├── ✅ Jueves 13: Azure ML workspace
├── ✅ Viernes 14: AutoML
├── ✅ Sábado 15: LAB - Crear primer modelo (HOY COMPLETADO)
└── 📅 Domingo 16: DESCANSO
```

**¡Completaste el 86% de la Semana 2!** 🎉

---

## 🎊 ¡FELICITACIONES!

### Lo que lograste hoy:

✅ **Creaste tu primer modelo de ML** en la nube  
✅ **Aplicaste AutoML** end-to-end  
✅ **Analizaste métricas** en contexto real  
✅ **Interpretaste resultados** de negocio  
✅ **Conectaste teoría con práctica** de toda la semana

### Habilidades desarrolladas:

- 🔧 Configurar experimentos AutoML
- 📊 Analizar confusion matrix
- 📈 Interpretar ROC curves
- 🧠 Feature importance analysis
- 💼 Decisiones basadas en métricas
- ☁️ Trabajar con Azure ML Studio

---

## 📚 MATERIAL COMPLEMENTARIO (Opcional)

### Videos recomendados:

1. **"Azure AutoML Tutorial"** - Microsoft Learn (20 min)
2. **"Understanding Model Metrics"** - Explicaciones visuales
3. **"Feature Importance Explained"** - Interpretación práctica

### Lecturas:

1. **Microsoft Learn:** "Train models with AutoML"
2. **Documentación:** "Classification metrics in Azure ML"
3. **Blog:** "Best practices for AutoML experiments"

---

## 💭 REFLEXIÓN FINAL

**Antes de terminar, piensa:**

1. **¿Qué fue lo más sorprendente del lab?**
   - ¿La facilidad de AutoML?
   - ¿Los ensembles ganando?
   - ¿La importancia del trade-off Precision/Recall?

2. **¿Qué concepto entiendes mejor ahora?**
   - ¿Métricas de clasificación?
   - ¿Feature importance?
   - ¿Ensemble models?

3. **¿Cómo aplicarías esto en tu contexto?**
   - ¿Qué problemas podrías resolver?
   - ¿Qué datos tienes disponibles?
   - ¿Qué métricas priorizarías?

---

## 📞 ¿NECESITAS AYUDA?

**Si tienes dudas:**

- Repasa el material del día correspondiente
- Consulta la documentación de Azure ML
- Pregunta en los foros de Microsoft Learn
- **Pregúntame a mí** - estoy aquí para ayudarte

---

## 🎯 PREPARACIÓN PARA MAÑANA

### Domingo 16: Día de descanso

**NO estudies mañana** ✋

**En su lugar:**

- 😴 Descansa bien
- 🧘 Relájate
- 🚶 Haz ejercicio
- 🎮 Diviértete
- 💭 Deja que tu cerebro consolide lo aprendido

**Tu cerebro necesita tiempo para:**

- Consolidar memorias
- Crear conexiones neuronales
- Prepararse para Semana 3

**Lunes empezamos Semana 3:**

- Computer Vision
- Azure AI Vision services
- Reconocimiento de imágenes
- OCR y Face API

---

## ✅ CHECKLIST FINAL

Antes de cerrar Azure:

- [ ] Experimento completado exitosamente
- [ ] Métricas analizadas y documentadas
- [ ] Compute cluster escalado a 0 nodes
- [ ] Reflexiones escritas en tu cuaderno
- [ ] Screenshots guardados (opcional)
- [ ] Entendiste los conceptos principales
- [ ] Listo para descansar mañana

---

**🎉 ¡EXCELENTE TRABAJO EN EL LABORATORIO!** 🎉

**Has dado un paso ENORME en tu preparación para el AI-900.**

**Descansa bien este domingo. ¡Te lo mereces!** 💪😊

---

_Última actualización: Sábado 15 de noviembre 2025_  
_Semana 2 de 6 - Día 6 de 7 (Lab Práctico)_  
_¡Semana 2 casi completa!_
