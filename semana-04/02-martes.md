# 📚 AI-900 | SEMANA 4 - MARTES 26 NOV

## 🔍 Azure AI Language - Análisis de Texto y Sentimiento

---

## 🎯 OBJETIVOS DEL DÍA

Al finalizar hoy, serás capaz de:

- ✅ Explicar qué es Azure AI Language y qué servicios ofrece
- ✅ Entender cómo funciona el análisis de sentimiento en profundidad
- ✅ Diferenciar entre sentiment analysis y opinion mining
- ✅ Conocer los confidence scores y cómo interpretarlos
- ✅ Identificar casos de uso reales de Azure AI Language

**Tiempo estimado:** 1.5 horas  
**Nivel de dificultad:** ⭐⭐⭐⚪⚪ (Media)

---

## 📖 PARTE 1: ¿QUÉ ES AZURE AI LANGUAGE? (15 min)

### 🌟 Definición

**Azure AI Language** es un conjunto de servicios de NLP basados en la nube que permite:

- Analizar texto sin necesidad de expertise en ML
- Usar modelos pre-entrenados listos para usar
- Personalizar modelos para tu dominio específico

```
ANTES (Sin Azure AI Language):
👨‍💻 Necesitas: Equipo de Data Scientists
📚 Entrenar modelos desde cero
💰 Meses de desarrollo
🔧 Infraestructura compleja

AHORA (Con Azure AI Language):
🚀 API REST simple
⚡ Resultados en segundos
💳 Pago por uso
📦 Modelos pre-entrenados
```

---

### 🎯 Servicios Principales de Azure AI Language

#### 1️⃣ : **Pre-built Features (Características Pre-construidas)**

Listas para usar sin entrenamiento:

| Servicio                     | Descripción                                  | Ejemplo                        |
| ---------------------------- | -------------------------------------------- | ------------------------------ |
| **Sentiment Analysis**       | Detecta positivo/negativo/neutral            | "¡Excelente!" → Positivo       |
| **Opinion Mining**           | Detecta opiniones sobre aspectos específicos | "Comida buena, servicio malo"  |
| **Key Phrase Extraction**    | Extrae conceptos principales                 | "IA, machine learning, Python" |
| **Named Entity Recognition** | Identifica personas, lugares, fechas         | "Microsoft en Seattle"         |
| **Entity Linking**           | Vincula entidades a Wikipedia                | "Gates" → Bill Gates (persona) |
| **Language Detection**       | Identifica idioma                            | "Hello" → Inglés               |
| **PII Detection**            | Detecta información personal                 | "Mi email es juan@example.com" |

#### 2️⃣ : **Custom Features (Características Personalizables)**

Requieren entrenamiento con tus datos:

- **Custom Named Entity Recognition**: Detecta entidades específicas de tu dominio
- **Custom Text Classification**: Clasifica texto según tus categorías
- **Conversational Language Understanding (CLU)**: Crea bots inteligentes

---

### 🔑 Conceptos Clave

**API REST:**

```
POST https://[endpoint].cognitiveservices.azure.com/text/analytics/v3.1/sentiment
```

**Autenticación:**

- Requiere API Key o Azure AD token
- Endpoint único por recurso

**Límites:**

- Texto máximo: 5,120 caracteres por documento
- Hasta 10 documentos por solicitud
- Rate limits según tier de pricing

---

## 📖 PARTE 2: SENTIMENT ANALYSIS EN PROFUNDIDAD (25 min)

### 🎭 ¿Qué es Sentiment Analysis?

Analiza el **tono emocional** de un texto y lo clasifica en:

```
😊 POSITIVE (Positivo)
😐 NEUTRAL (Neutral)
😞 NEGATIVE (Negativo)
🤔 MIXED (Mixto)
```

---

### 📊 Cómo Funciona - Ejemplo Real

**INPUT:**

```json
{
  "documents": [
    {
      "id": "1",
      "language": "es",
      "text": "¡Me encanta este producto! Superó todas mis expectativas."
    }
  ]
}
```

**OUTPUT:**

```json
{
  "documents": [
    {
      "id": "1",
      "sentiment": "positive",
      "confidenceScores": {
        "positive": 0.99,
        "neutral": 0.01,
        "negative": 0.0
      },
      "sentences": [
        {
          "text": "¡Me encanta este producto!",
          "sentiment": "positive",
          "confidenceScores": {
            "positive": 0.98,
            "neutral": 0.01,
            "negative": 0.01
          }
        },
        {
          "text": "Superó todas mis expectativas.",
          "sentiment": "positive",
          "confidenceScores": {
            "positive": 0.99,
            "neutral": 0.01,
            "negative": 0.0
          }
        }
      ]
    }
  ]
}
```

---

### 🎯 Interpretando Confidence Scores

**Confidence Scores** indican qué tan seguro está el modelo:

```
ESCALA: 0.00 a 1.00 (0% a 100%)

HIGH CONFIDENCE (Alta confianza):
✅ 0.90 - 1.00 → El modelo está muy seguro
Ejemplo: "¡Increíble!" → positive: 0.99

MEDIUM CONFIDENCE (Confianza media):
⚠️ 0.60 - 0.89 → El modelo está moderadamente seguro
Ejemplo: "Está bien" → neutral: 0.75

LOW CONFIDENCE (Baja confianza):
❌ 0.00 - 0.59 → El modelo no está seguro
Ejemplo: "No está mal pero tampoco bien" → mixed scores
```

**REGLA IMPORTANTE:**
Los 3 scores (positive, neutral, negative) siempre suman 1.00

```
positive: 0.85
neutral:  0.10
negative: 0.05
-----------------
TOTAL:    1.00 ✅
```

---

### 🔍 Análisis a Nivel de Documento vs Oración

Azure AI Language analiza en **DOS niveles**:

#### 📄 **Nivel de Documento** (Document Level)

El sentimiento general del texto completo

```
TEXTO COMPLETO:
"El hotel es hermoso y la ubicación perfecta.
Pero el servicio fue terrible y la comida fría."

SENTIMIENTO DOCUMENTO: MIXED (Mixto)
- positive: 0.45
- negative: 0.45
- neutral: 0.10
```

#### 📝 **Nivel de Oración** (Sentence Level)

El sentimiento de cada oración individual

```
ORACIÓN 1: "El hotel es hermoso y la ubicación perfecta."
→ POSITIVE (0.95)

ORACIÓN 2: "Pero el servicio fue terrible y la comida fría."
→ NEGATIVE (0.92)
```

**¿Por qué es útil?**

- Identifica **qué partes específicas** son positivas/negativas
- Útil para análisis detallado de feedback
- Ayuda a encontrar problemas específicos en reseñas largas

---

## 📖 PARTE 3: OPINION MINING (20 min)

### 💎 ¿Qué es Opinion Mining?

**Opinion Mining** (Minería de Opiniones) va **MÁS ALLÁ** del sentiment analysis básico.

No solo detecta SI es positivo/negativo, sino:

- **QUÉ** aspecto específico se menciona
- **CÓMO** se siente el usuario sobre ese aspecto

```
SENTIMENT ANALYSIS básico:
"La comida estaba deliciosa pero el servicio fue lento"
→ MIXED (positivo + negativo) ✅

OPINION MINING avanzado:
"La comida estaba deliciosa pero el servicio fue lento"
→ "comida": POSITIVO ✅
→ "servicio": NEGATIVO ❌
```

---

### 🎯 Componentes de Opinion Mining

#### 1️⃣ : **Targets (Objetivos)**

Los aspectos o características mencionadas

```
EJEMPLO: "La batería dura mucho pero la pantalla es pequeña"

TARGETS identificados:
- "batería"
- "pantalla"
```

#### 2️⃣ : **Assessments (Evaluaciones)**

Las opiniones expresadas sobre cada target

```
ASSESSMENTS:
- "dura mucho" (sobre batería)
- "es pequeña" (sobre pantalla)
```

#### 3️⃣ : **Sentiments**

El sentimiento de cada assessment

```
SENTIMENTS:
- "batería" → "dura mucho" → POSITIVO ✅
- "pantalla" → "es pequeña" → NEGATIVO ❌
```

---

### 📊 Ejemplo Completo de Opinion Mining

**INPUT:**

```
"El hotel tiene habitaciones limpias y cómodas.
El personal es amable.
Pero el wifi es lento y el desayuno caro."
```

**OUTPUT:**

| Target (Aspecto) | Assessment (Opinión) | Sentiment   |
| ---------------- | -------------------- | ----------- |
| habitaciones     | limpias y cómodas    | ✅ POSITIVE |
| personal         | amable               | ✅ POSITIVE |
| wifi             | lento                | ❌ NEGATIVE |
| desayuno         | caro                 | ❌ NEGATIVE |

**VALOR EMPRESARIAL:**

```
Dashboard automático:
✅ Fortalezas: habitaciones (95%), personal (92%)
❌ Áreas de mejora: wifi (78% negativo), desayuno (82% negativo)

ACCIÓN: Mejorar wifi y revisar precios de desayuno
```

---

## 🎯 CONCEPTOS CLAVE PARA EL EXAMEN AI-900

### ✅ DEBES SABER:

1. **Azure AI Language** = Conjunto de servicios NLP pre-entrenados

2. **Sentiment Analysis:**
   - Clasifica: positive, negative, neutral, mixed
   - Retorna confidence scores (0.00 a 1.00)
   - Analiza a nivel de documento Y oración

3. **Opinion Mining:**
   - Más detallado que Sentiment Analysis
   - Identifica: Target + Assessment + Sentiment
   - Útil para análisis granular de productos/servicios

4. **Confidence Scores:**
   - Miden certeza del modelo
   - Rango: 0.00 a 1.00
   - Los 3 scores suman siempre 1.00

5. **Pre-built vs Custom:**
   - Pre-built: Listos para usar
   - Custom: Requieren entrenamiento con tus datos

---

## 🎴 FLASHCARDS PARA HOY

1. **P:** ¿Qué es Azure AI Language?  
   **R:** Conjunto de servicios NLP pre-entrenados para analizar texto sin necesidad de expertise en ML

2. **P:** ¿Qué es Sentiment Analysis?  
   **R:** Analiza el tono emocional y clasifica texto en positive, negative, neutral o mixed

3. **P:** ¿Qué son los confidence scores?  
   **R:** Valores de 0.00 a 1.00 que indican qué tan seguro está el modelo de su predicción

4. **P:** ¿Qué es Opinion Mining?  
   **R:** Análisis granular que identifica aspectos específicos (targets) y las opiniones sobre ellos

5. **P:** Diferencia entre Sentiment Analysis y Opinion Mining  
   **R:** Sentiment da tono general, Opinion Mining identifica qué aspecto específico es positivo/negativo

6. **P:** ¿Qué es un "target" en Opinion Mining?  
   **R:** El aspecto o característica específica mencionada (ej: "batería", "servicio")

7. **P:** ¿Qué es un "assessment" en Opinion Mining?  
   **R:** La opinión expresada sobre un target (ej: "dura mucho", "muy lento")

8. **P:** ¿Los confidence scores suman cuánto?  
   **R:** Siempre suman 1.00 (positive + neutral + negative = 1.00)

9. **P:** ¿A qué niveles analiza Azure AI Language el sentimiento?  
   **R:** Nivel de documento (texto completo) y nivel de oración (cada oración individual)

10. **P:** ¿Cuándo usar Opinion Mining vs Sentiment Analysis?  
    **R:** Opinion Mining cuando necesitas insights accionables sobre aspectos específicos; Sentiment para clasificación general rápida

---

## ✅ CHECKLIST DE HOY

- [ ] Entiendo qué es Azure AI Language y sus servicios
- [ ] Puedo explicar cómo funciona Sentiment Analysis
- [ ] Conozco los confidence scores y cómo interpretarlos
- [ ] Entiendo la diferencia entre Sentiment y Opinion Mining
- [ ] Sé cuándo usar cada uno
- [ ] Puedo identificar targets y assessments
- [ ] He creado las 10 flashcards

---

# 📝 PREGUNTAS ESTILO EXAMEN MICROSOFT AI-900

## Tema: Azure AI Language - Sentiment Analysis

---

## ❓ PREGUNTA 1 - Escenario de Análisis de Reseñas

**ESCENARIO:**
Una cadena hotelera procesa 5,000 reseñas de huéspedes por semana. Han implementado Azure AI Language para analizar el sentimiento. El servicio retorna el siguiente resultado para una reseña:

```json
{
  "sentiment": "mixed",
  "confidenceScores": {
    "positive": 0.45,
    "neutral": 0.1,
    "negative": 0.45
  }
}
```

**PREGUNTA:**
¿Qué significa este resultado?

**A)** El servicio no pudo determinar el sentimiento con certeza suficiente  
**B)** La reseña contiene tanto comentarios positivos como negativos en proporciones similares  
**C)** Los confidence scores están mal configurados porque no suman 100%  
**D)** El texto debe ser analizado nuevamente porque hay un error en el resultado

<details>
<summary>👉 Ver respuesta correcta</summary>

**RESPUESTA CORRECTA: B) La reseña contiene tanto comentarios positivos como negativos en proporciones similares**

**EXPLICACIÓN:**

- **sentiment: "mixed"** indica que el texto tiene tanto elementos positivos como negativos
- Los **confidence scores** muestran 0.45 positive y 0.45 negative (casi iguales), confirmando que hay balance entre sentimientos opuestos
- Los scores SÍ suman 1.00 (0.45 + 0.10 + 0.45 = 1.00) ✅
- Esto es un resultado válido y esperado cuando una reseña menciona aspectos buenos y malos

**EJEMPLO TÍPICO:**

```
"El hotel tiene hermosas vistas y habitaciones limpias (POSITIVO),
pero el servicio fue terrible y el precio muy alto (NEGATIVO)"
→ Resultado: MIXED con scores similares en positive y negative
```

**Por qué las otras son incorrectas:**

- **A)** FALSO: Los scores altos (0.45) indican alta confianza, no baja
- **C)** FALSO: 0.45 + 0.10 + 0.45 = 1.00 ✅ (suman correctamente)
- **D)** FALSO: Este es un resultado válido, no hay error

**TIP PARA EL EXAMEN:**

- Los 3 confidence scores **SIEMPRE** suman 1.00 (100%)
- **mixed** sentiment es válido cuando hay comentarios positivos Y negativos
- Scores altos (>0.4) indican alta confianza, no error

</details>

---

## ❓ PREGUNTA 2 - Escenario de Opinion Mining

**ESCENARIO:**
Un fabricante de smartphones recibe miles de reseñas de su nuevo modelo. Quieren entender no solo SI los clientes están satisfechos, sino QUÉ aspectos específicos del teléfono les gustan o disgustan (batería, cámara, pantalla, precio, etc.).

**PREGUNTA:**
¿Qué característica de Azure AI Language deberían activar ADEMÁS de Sentiment Analysis?

**A)** Key Phrase Extraction  
**B)** Named Entity Recognition (NER)  
**C)** Opinion Mining  
**D)** Language Detection

<details>
<summary>👉 Ver respuesta correcta</summary>

**RESPUESTA CORRECTA: C) Opinion Mining**

**EXPLICACIÓN:**

- **Opinion Mining** es específicamente diseñado para identificar:
  - **Targets** (aspectos): batería, cámara, pantalla, precio
  - **Assessments** (opiniones): "excelente", "muy lento", "cara"
  - **Sentiment** de cada aspecto: positivo o negativo

**EJEMPLO:**

```
RESEÑA: "La cámara es excelente pero la batería dura muy poco"

SENTIMENT ANALYSIS (básico):
→ MIXED (positivo + negativo)

OPINION MINING (granular):
→ "cámara": POSITIVE ✅
→ "batería": NEGATIVE ❌
```

**VALOR EMPRESARIAL:**

```
DASHBOARD resultante:
✅ Aspectos positivos: cámara (92%), diseño (88%)
❌ Aspectos negativos: batería (75%), precio (68%)

ACCIÓN: Mejorar batería en próximo modelo
```

**Por qué las otras son incorrectas:**

- **A) Key Phrase Extraction**: Extrae temas generales, pero no asocia sentimiento a cada aspecto
- **B) NER**: Identifica entidades como nombres y lugares, no opiniones sobre características
- **D) Language Detection**: Solo identifica el idioma, no analiza sentimiento

**TIP PARA EL EXAMEN:**
Cuando veas "identificar QUÉ aspectos específicos" + "opiniones sobre cada aspecto" → **Opinion Mining**

</details>

---

## ❓ PREGUNTA 3 - Escenario de Confidence Scores

**ESCENARIO:**
Una empresa está procesando comentarios de clientes con Azure AI Language. Un analista revisa los resultados y encuentra esta respuesta:

```json
{
  "sentiment": "positive",
  "confidenceScores": {
    "positive": 0.52,
    "neutral": 0.35,
    "negative": 0.13
  }
}
```

**PREGUNTA:**
¿Cómo debería interpretar el analista este resultado?

**A)** El modelo está muy seguro de que el sentimiento es positivo y el resultado es confiable para tomar decisiones  
**B)** El modelo detectó sentimiento positivo pero con confianza moderada, se recomienda revisión manual  
**C)** El resultado es inválido porque el confidence score es menor a 0.75  
**D)** El texto debe procesarse nuevamente porque los scores no suman correctamente

<details>
<summary>👉 Ver respuesta correcta</summary>

**RESPUESTA CORRECTA: B) El modelo detectó sentimiento positivo pero con confianza moderada, se recomienda revisión manual**

**EXPLICACIÓN:**

**Interpretación de Confidence Scores:**

```
HIGH CONFIDENCE (Alta confianza):
✅ 0.90 - 1.00 → Muy seguro, confiable

MEDIUM CONFIDENCE (Confianza media):
⚠️ 0.60 - 0.89 → Moderadamente seguro

LOW CONFIDENCE (Baja confianza):
❌ 0.00 - 0.59 → Poca certeza
```

En este caso:

- **positive: 0.52** → Confianza BAJA-MEDIA
- El modelo "piensa" que es positivo, pero NO está muy seguro
- Hay un 35% de probabilidad de ser neutral
- **Acción recomendada:** Revisión manual de casos ambiguos

**EJEMPLO de texto que daría estos scores:**

```
"El producto funciona. Está bien, supongo."
→ Ligeramente positivo, pero muy ambiguo
→ Confidence bajo en positive
```

**Por qué las otras son incorrectas:**

- **A)** FALSO: 0.52 NO es "muy seguro", es confianza baja-media
- **C)** FALSO: No hay un "mínimo requerido", 0.52 es válido pero debe interpretarse con cautela
- **D)** FALSO: 0.52 + 0.35 + 0.13 = 1.00 ✅ (suman correctamente)

**TIP PARA EL EXAMEN:**

- Confidence scores bajos (<0.60) indican **ambigüedad** en el texto
- Son resultados VÁLIDOS, pero requieren interpretación cuidadosa
- Scores altos (>0.90) = alta confianza; bajos (<0.60) = revisar manualmente

</details>

---

## ❓ PREGUNTA 4 - Escenario de Análisis Multinivel

**ESCENARIO:**
Una empresa analiza esta reseña de restaurante con Azure AI Language:

```
"El restaurante tiene un ambiente hermoso y la decoración es impresionante.
La comida llegó fría y el servicio fue extremadamente lento.
Los postres estaban deliciosos."
```

El servicio retorna:

- **Documento completo:** sentiment = "mixed"
- **Oración 1:** sentiment = "positive"
- **Oración 2:** sentiment = "negative"
- **Oración 3:** sentiment = "positive"

**PREGUNTA:**
¿Qué demuestra este resultado sobre Azure AI Language?

**A)** El servicio cometió un error porque no todas las oraciones tienen el mismo sentimiento que el documento  
**B)** El análisis es incorrecto y debe reprocessarse con Opinion Mining activado  
**C)** El servicio analiza sentimiento tanto a nivel de documento completo como de cada oración individual  
**D)** El servicio solo puede analizar correctamente textos con un único sentimiento

<details>
<summary>👉 Ver respuesta correcta</summary>

**RESPUESTA CORRECTA: C) El servicio analiza sentimiento tanto a nivel de documento completo como de cada oración individual**

**EXPLICACIÓN:**

**Azure AI Language realiza análisis en DOS niveles:**

#### 📄 **Nivel 1: Documento Completo**

```
Analiza TODO el texto como una unidad:
"Ambiente hermoso... comida fría... postres deliciosos"
→ MIXED (tiene partes positivas Y negativas)
```

#### 📝 **Nivel 2: Cada Oración Individual**

```
Oración 1: "El restaurante tiene un ambiente hermoso..."
→ POSITIVE ✅

Oración 2: "La comida llegó fría y el servicio fue lento."
→ NEGATIVE ❌

Oración 3: "Los postres estaban deliciosos."
→ POSITIVE ✅
```

**¿Por qué es útil?**

- **Identifica QUÉ partes son problemáticas**
- Útil para análisis detallado
- Permite encontrar problemas específicos en texto largo

**Ejemplo práctico:**

```
DASHBOARD:
Sentimiento general: MIXED

Desglose por oración:
✅ Aspectos positivos: ambiente, decoración, postres
❌ Aspectos negativos: temperatura comida, velocidad servicio

ACCIÓN: Mejorar servicio de cocina y velocidad
```

**Por qué las otras son incorrectas:**

- **A)** FALSO: Es NORMAL que las oraciones tengan diferentes sentimientos cuando el documento es "mixed"
- **B)** FALSO: El análisis está correcto; Opinion Mining es opcional y complementario
- **D)** FALSO: Azure AI Language maneja perfectamente sentimientos mixtos

**TIP PARA EL EXAMEN:**

- Azure AI Language **SIEMPRE** analiza en dos niveles: documento Y oraciones
- Es NORMAL que un documento "mixed" tenga oraciones con sentimientos diferentes
- Este análisis multinivel es una **característica**, no un error

</details>

---

## ❓ PREGUNTA 5 - Escenario de Implementación

**ESCENARIO:**
Una startup quiere implementar análisis de sentimiento para sus redes sociales. Reciben tweets en inglés, español, francés y alemán. Tienen un presupuesto limitado y quieren empezar con 10,000 análisis por mes durante la fase de prueba.

**PREGUNTA:**
¿Qué configuración de Azure AI Language es la más apropiada para este escenario?

**A)** Crear 4 recursos separados de Azure AI Language, uno por cada idioma  
**B)** Usar el tier Free que permite 5,000 text records por mes y crear dos recursos Free  
**C)** Usar un único recurso de Azure AI Language con tier Standard y pagar por uso  
**D)** Implementar Custom Text Classification porque necesitan soporte multilingüe

<details>
<summary>👉 Ver respuesta correcta</summary>

**RESPUESTA CORRECTA: B) Usar el tier Free que permite 5,000 text records por mes y crear dos recursos Free**

**EXPLICACIÓN:**

**Análisis del escenario:**

- Necesitan: 10,000 análisis/mes
- Presupuesto: Limitado
- Idiomas: 4 diferentes (inglés, español, francés, alemán)
- Fase: Prueba/desarrollo

**Modelo de Pricing de Azure AI Language:**

```
TIER FREE:
✅ 5,000 text records por mes
✅ GRATIS
✅ Perfecto para desarrollo/testing
❌ Límite: 5,000/mes por recurso

TIER STANDARD:
✅ Ilimitado
❌ Pago por uso ($$)
```

**Solución óptima:**

```
Crear 2 recursos Free:
- Recurso 1: 5,000 text records
- Recurso 2: 5,000 text records
TOTAL: 10,000 text records/mes GRATIS ✅
```

**Sobre multilingüe:**

- **UN SOLO recurso** soporta múltiples idiomas ✅
- NO necesitas recursos separados por idioma
- Azure AI Language detecta el idioma automáticamente

**Por qué las otras son incorrectas:**

- **A)** INNECESARIO: Un solo recurso soporta múltiples idiomas
- **C)** MÁS CARO: Standard cobra por uso; con 2 recursos Free obtienen 10,000 gratis
- **D)** INCORRECTO: Sentiment Analysis pre-built YA soporta múltiples idiomas; Custom Text Classification es para otra cosa

**TIP PARA EL EXAMEN:**

- **Tier Free:** 5,000 text records/mes, ideal para dev/testing
- **Un recurso = múltiples idiomas** (no necesitas recursos separados)
- Para producción con volumen alto → Standard tier
- **1 text record** = 1,000 caracteres

**Cálculo de costos (concepto importante):**

```
TEXTO: "Me encanta este producto" (26 caracteres)
= 1 text record (porque <1,000 caracteres)

TEXTO: Documento de 3,500 caracteres
= 4 text records (redondeado hacia arriba)
```

</details>

---

## 🎯 RESUMEN DE PATRONES PARA EL EXAMEN

### 🔍 Identifica estas palabras clave:

| **Si ves esto...**                            | **Piensa en...**              |
| --------------------------------------------- | ----------------------------- |
| Confidence scores, certeza del modelo         | Valores 0.00-1.00, suman 1.00 |
| Aspectos específicos + opinión sobre cada uno | **Opinion Mining**            |
| Análisis detallado de características         | **Opinion Mining**            |
| Targets, assessments                          | **Opinion Mining**            |
| Sentimiento de documento vs oraciones         | Análisis multinivel           |
| Presupuesto limitado, fase de prueba          | **Tier Free**                 |
| Múltiples idiomas                             | Un solo recurso sirve         |
| Text records, pricing                         | 1 record = 1,000 chars        |

---

## 📊 PUNTUACIÓN

Marca cuántas respondiste correctamente:

- [ ] Pregunta 1 - Confidence Scores Mixtos
- [ ] Pregunta 2 - Opinion Mining
- [ ] Pregunta 3 - Interpretación de Confidence
- [ ] Pregunta 4 - Análisis Multinivel
- [ ] Pregunta 5 - Pricing y Configuración

### Evaluación:

- **5/5 correctas** ✅ ¡Excelente! Dominas Azure AI Language
- **4/5 correctas** 👍 Muy bien, repasa la que fallaste
- **3/5 correctas** 📚 Bien, revisa conceptos de confidence scores
- **2 o menos** 🔄 Repasa la lección de hoy completa

---

## 💡 CONCEPTOS CRÍTICOS DEL EXAMEN

### 1️⃣ **Confidence Scores - MUY PREGUNTADO**

```
SIEMPRE recuerda:
✅ Rango: 0.00 a 1.00
✅ Los 3 scores SIEMPRE suman 1.00
✅ >0.90 = alta confianza
✅ <0.60 = baja confianza, revisar manualmente
```

### 2️⃣ **Sentiment vs Opinion Mining**

```
SENTIMENT ANALYSIS:
→ Vista general (positive/negative/neutral/mixed)
→ Rápido
→ Suficiente para mayoría de casos

OPINION MINING:
→ Vista detallada por aspecto
→ Target + Assessment + Sentiment
→ Cuando necesitas insights accionables
```

### 3️⃣ **Análisis Multinivel**

```
Azure AI Language SIEMPRE analiza:
1. Documento completo
2. Cada oración individual

Esto es NORMAL, no es un error.
```

### 4️⃣ **Pricing - IMPORTANTE**

```
TIER FREE:
- 5,000 text records/mes
- Gratis
- Ideal: dev/testing

TIER STANDARD:
- Pago por uso
- Sin límites
- Ideal: producción
```

---

## 🎓 ESTRATEGIAS PARA EL EXAMEN

### 📋 Checklist mental:

Cuando veas una pregunta de Sentiment Analysis:

1. **¿Habla de confidence scores?**
   - ✅ Verifica que sumen 1.00
   - ✅ Interpreta el nivel de confianza

2. **¿Menciona "aspectos específicos"?**
   - → Opinion Mining

3. **¿Habla de oraciones individuales?**
   - → Análisis multinivel (característica normal)

4. **¿Pregunta sobre pricing/configuración?**
   - → Tier Free para testing
   - → Un recurso sirve para múltiples idiomas

5. **¿Pide comparar servicios?**
   - → Sentiment = general
   - → Opinion Mining = granular

---

## 🔥 ERRORES COMUNES A EVITAR

❌ **Error 1:** Pensar que confidence scores bajos son errores
✅ **Correcto:** Son válidos, indican ambigüedad en el texto

❌ **Error 2:** Creer que necesitas un recurso por idioma
✅ **Correcto:** Un solo recurso soporta múltiples idiomas

❌ **Error 3:** Pensar que "mixed" sentiment es un error
✅ **Correcto:** Es válido cuando hay contenido positivo Y negativo

❌ **Error 4:** Confundir Sentiment Analysis con Opinion Mining
✅ **Correcto:** Sentiment = general, Opinion Mining = por aspecto

❌ **Error 5:** Olvidar que los 3 scores suman 1.00
✅ **Correcto:** SIEMPRE suman 1.00 (positive + neutral + negative)

---

**Siguiente paso:** Practica con el portal de Azure AI Language (hay demos gratuitas online)
**¡Excelente progreso! 🎉**  
**Tiempo total:** ~1.5 horas  
**Progreso:** Semana 4 - Día 2/6 ✅
