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

#### 1️⃣ **Pre-built Features (Características Pre-construidas)**

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

#### 2️⃣ **Custom Features (Características Personalizables)**

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

#### 1️⃣ **Targets (Objetivos)**

Los aspectos o características mencionadas

```
EJEMPLO: "La batería dura mucho pero la pantalla es pequeña"

TARGETS identificados:
- "batería"
- "pantalla"
```

#### 2️⃣ **Assessments (Evaluaciones)**

Las opiniones expresadas sobre cada target

```
ASSESSMENTS:
- "dura mucho" (sobre batería)
- "es pequeña" (sobre pantalla)
```

#### 3️⃣ **Sentiments**

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

**¡Excelente progreso! 🎉**  
**Tiempo total:** ~1.5 horas  
**Progreso:** Semana 4 - Día 2/6 ✅
