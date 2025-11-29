# 📚 AI-900 | SEMANA 4 - VIERNES 29 NOV

## 🎯 Repaso General de NLP + Mini Examen de Práctica

---

## 🎯 OBJETIVOS DEL DÍA

Al finalizar hoy, serás capaz de:

- ✅ Repasar TODOS los conceptos clave de NLP de la semana
- ✅ Identificar rápidamente qué servicio usar en cada escenario
- ✅ Resolver preguntas tipo examen AI-900
- ✅ Identificar tus áreas fuertes y débiles
- ✅ Estar listo para avanzar a la siguiente semana

**Tiempo estimado:** 2 horas  
**Nivel de dificultad:** ⭐⭐⭐⭐⚪ (Alta - Es examen)

---

## 📖 PARTE 1: MAPA MENTAL DE NLP (15 min)

### 🗺️ Todo lo que Aprendiste Esta Semana

```
NATURAL LANGUAGE PROCESSING (NLP)
│
├─── 🎭 ANÁLISIS DE SENTIMIENTO
│    ├─ Sentiment Analysis
│    │  ├─ Positive, Negative, Neutral, Mixed
│    │  ├─ Confidence Scores (0.00-1.00)
│    │  └─ Análisis: Documento + Oraciones
│    │
│    └─ Opinion Mining
│       ├─ Targets (aspectos)
│       ├─ Assessments (opiniones)
│       └─ Sentiment por aspecto
│
├─── 📝 EXTRACCIÓN DE INFORMACIÓN
│    ├─ Key Phrase Extraction
│    │  └─ Temas y conceptos principales
│    │
│    ├─ Named Entity Recognition (NER)
│    │  ├─ Person, Location, Organization
│    │  ├─ DateTime, Quantity, Email
│    │  └─ 9 categorías principales
│    │
│    ├─ Entity Linking
│    │  └─ Vincula entidades a Wikipedia
│    │
│    └─ PII Detection
│       ├─ Detecta información sensible
│       └─ Redacción automática
│
├─── 🌍 IDIOMAS
│    ├─ Language Detection
│    │  └─ Identifica idioma (120+)
│    │
│    └─ Translator
│       ├─ Traducción texto (100+ idiomas)
│       ├─ Detección automática
│       └─ Custom Translator
│
├─── 🗣️ VOZ
│    ├─ Speech-to-Text
│    │  ├─ Transcripción tiempo real
│    │  ├─ Transcripción batch
│    │  └─ Diarización (hablantes)
│    │
│    ├─ Text-to-Speech
│    │  ├─ Voces neurales
│    │  ├─ SSML (control avanzado)
│    │  └─ Estilos de voz
│    │
│    ├─ Speech Translation
│    │  └─ Voz→voz o voz→texto
│    │
│    └─ Speaker Recognition
│       ├─ Verification (¿es quien dice?)
│       └─ Identification (¿quién es?)
│
└─── 🤖 CONVERSATIONAL AI
     ├─ Question Answering
     │  ├─ Knowledge Base
     │  ├─ FAQ automático
     │  ├─ Confidence scores
     │  └─ Active Learning
     │
     ├─ Bot Service
     │  ├─ Múltiples canales
     │  ├─ Adaptive Cards
     │  ├─ Dialogs
     │  └─ State Management
     │
     └─ CLU (Conversational Language Understanding)
        ├─ Intents (intenciones)
        ├─ Entities (entidades)
        └─ Utterances (expresiones)
```

---

## 📖 PARTE 2: REPASO RÁPIDO - CONCEPTOS CLAVE (20 min)

### 🎭 Sentiment Analysis & Opinion Mining

```
SENTIMENT ANALYSIS:
✅ Clasifica: positive, negative, neutral, mixed
✅ Confidence scores suman 1.00
✅ Nivel documento + nivel oración
✅ Uso: Análisis rápido de tono general

OPINION MINING:
✅ Target + Assessment + Sentiment
✅ Granular por aspecto
✅ Uso: Insights accionables detallados

DIFERENCIA CLAVE:
Sentiment: "La reseña es positiva"
Opinion Mining: "Comida: positiva, Servicio: negativa"
```

---

### 📝 Extracción de Información

```
KEY PHRASE EXTRACTION:
✅ Extrae conceptos/temas principales
✅ NO es sentimiento
✅ Uso: Indexación, categorización
❌ NO confundir con NER

NAMED ENTITY RECOGNITION (NER):
✅ Entidades ESPECÍFICAS (nombres, fechas, lugares)
✅ 9 categorías principales
✅ Uso: Extracción de datos estructurados
❌ NO confundir con Key Phrases

ENTITY LINKING:
✅ NER + Wikipedia
✅ Desambiguación
✅ Uso: Contexto adicional

PII DETECTION:
✅ NER especializado en datos sensibles
✅ Redacción automática
✅ Uso: Compliance (GDPR, HIPAA)
❌ NO es Content Moderation
```

---

### 🌍 Idiomas y Traducción

```
LANGUAGE DETECTION:
✅ Identifica idioma (120+)
✅ Primer paso antes de traducir
✅ Uso: Enrutamiento, pre-procesamiento

TRANSLATOR:
✅ Texto entre 100+ idiomas
✅ Detección automática de origen
✅ Custom Translator para terminología
✅ Uso: Sitios multilingües, documentación
```

---

### 🗣️ Servicios de Voz

```
SPEECH-TO-TEXT:
✅ Voz → Texto
✅ Tiempo real o batch
✅ Diarización (múltiples hablantes)
✅ Uso: Subtítulos, transcripciones

TEXT-TO-SPEECH:
✅ Texto → Voz
✅ Voces neurales (naturales)
✅ SSML para control
✅ Uso: Accesibilidad, asistentes

SPEECH TRANSLATION:
✅ Voz en un idioma → Texto/Voz en otro
✅ Tiempo real
✅ Uso: Conferencias, turismo

SPEAKER RECOGNITION:
✅ Verification: ¿es quien dice ser?
✅ Identification: ¿quién es?
✅ Uso: Autenticación biométrica
```

---

### 🤖 Conversational AI

```
QUESTION ANSWERING:
✅ Bots de FAQ sin código
✅ Knowledge Base
✅ Respuestas FIJAS
✅ Uso: FAQs, documentación

BOT SERVICE:
✅ Plataforma completa
✅ 10+ canales
✅ Adaptive Cards, Dialogs
✅ Uso: Interfaz del bot

CLU:
✅ Entiende intenciones
✅ Intents + Entities
✅ Para ACCIONES
✅ Uso: Bots transaccionales

DIFERENCIA CRÍTICA:
QnA: "¿Cuál es el horario?" → "9AM-6PM" (fijo)
CLU: "Quiero reservar" → INTENT: Reservar → ACCIÓN
```

---

## 📖 PARTE 3: TABLA DE DECISIÓN RÁPIDA (10 min)

### 🎯 ¿Qué Servicio Usar?

| Necesidad                   | Servicio              | Palabra Clave                     |
| --------------------------- | --------------------- | --------------------------------- |
| ¿Es positivo/negativo?      | Sentiment Analysis    | "opinión", "satisfacción"         |
| ¿Qué aspecto es bueno/malo? | Opinion Mining        | "aspectos específicos"            |
| ¿De qué habla?              | Key Phrase Extraction | "temas", "categorizar"            |
| ¿Quién/dónde/cuándo?        | NER                   | "extraer nombres/fechas"          |
| ¿Información sensible?      | PII Detection         | "GDPR", "privacidad"              |
| ¿Qué idioma?                | Language Detection    | "enrutar por idioma"              |
| Traducir texto              | Translator            | "multilingüe"                     |
| Voz → Texto                 | Speech-to-Text        | "transcribir", "subtítulos"       |
| Texto → Voz                 | Text-to-Speech        | "narración", "accesibilidad"      |
| Traducir voz                | Speech Translation    | "intérprete tiempo real"          |
| ¿Es esta persona?           | Speaker Recognition   | "autenticación voz"               |
| FAQ automático              | Question Answering    | "preguntas frecuentes"            |
| Entender intención          | CLU                   | "reservar", "cancelar" (acciones) |
| Publicar bot                | Bot Service           | "Teams", "WhatsApp", "canales"    |

---

## 📖 PARTE 4: ERRORES COMUNES A EVITAR (15 min)

### ❌ Error 1: Confundir Sentiment con Opinion Mining

```
INCORRECTO:
"Usar Sentiment Analysis para identificar qué
características del producto no gustan"

CORRECTO:
"Usar Opinion Mining - identifica aspectos específicos
y sentimiento sobre cada uno"
```

---

### ❌ Error 2: Confundir Key Phrases con NER

```
INCORRECTO:
"Usar Key Phrase Extraction para extraer
nombres de personas de contratos"

CORRECTO:
"Usar NER - extrae entidades específicas como
nombres, fechas, montos"

REGLA:
Key Phrases = Conceptos generales
NER = Entidades específicas nombradas
```

---

### ❌ Error 3: Confundir QnA con CLU

```
INCORRECTO:
"Usar Question Answering para un bot que
procesa reservas de vuelos"

CORRECTO:
"Usar CLU - entiende intent 'ReservarVuelo'
y ejecuta acción en sistema de reservas"

REGLA:
QnA = Respuestas informativas fijas
CLU = Entender intenciones para acciones
```

---

### ❌ Error 4: Olvidar Language Detection

```
INCORRECTO:
"Usar Translator directamente en textos de origen desconocido"

CORRECTO:
"Primero Language Detection, luego Translator"

FLUJO:
Texto → Language Detection → Translator → Resultado
```

---

### ❌ Error 5: Confundir PII Detection con Content Moderation

```
INCORRECTO:
"Usar PII Detection para detectar contenido ofensivo"

CORRECTO:
"PII Detection solo para información personal sensible.
Content Moderation para contenido inapropiado"

PII: emails, teléfonos, DNI, tarjetas
Content Moderation: hate speech, violencia, etc.
```

---

### ❌ Error 6: Pensar que Confidence Scores bajos son errores

```
INCORRECTO:
"El confidence score es 0.52, el sistema falló"

CORRECTO:
"Confidence 0.52 es válido pero bajo - indica ambigüedad
en el texto, revisar manualmente casos importantes"

RECUERDA:
Los 3 scores SIEMPRE suman 1.00
Bajos scores = texto ambiguo, NO error
```

---

### ❌ Error 7: Necesitar recurso por idioma

```
INCORRECTO:
"Necesito 5 recursos de Azure AI Language,
uno para cada idioma que uso"

CORRECTO:
"Un solo recurso soporta 120+ idiomas"
```

---

## 🎯 MINI EXAMEN DE PRÁCTICA - NLP (60 min)

### 📋 INSTRUCCIONES

- **30 preguntas** estilo Microsoft AI-900
- **Tiempo sugerido:** 45-60 minutos
- **Formato:** Opción múltiple
- **Puntuación para aprobar:** 21/30 (70%)
- Marca tus respuestas antes de ver las soluciones

---

### ✏️ SECCIÓN 1: SENTIMENT ANALYSIS & OPINION MINING (6 preguntas)

**Pregunta 1:**
Una empresa procesa 10,000 reseñas de productos por día. El equipo de producto quiere saber qué características específicas de cada producto son bien valoradas y cuáles no. ¿Qué servicio de Azure AI Language deben usar?

- [ ] A) Sentiment Analysis  
- [-] B) Opinion Mining  
- [ ] C) Key Phrase Extraction  
- [ ] D) Named Entity Recognition

---

**Pregunta 2:**
Un servicio de Sentiment Analysis devuelve estos confidence scores:

```json
{
  "positive": 0.15,
  "neutral": 0.2,
  "negative": 0.65
}
```

¿Qué indica este resultado?

- [ ] A) Hay un error, los scores deben sumar 100  
- [x] B) El texto tiene sentimiento predominantemente negativo  
- [ ] C) El modelo no pudo determinar el sentimiento  
- [ ] D) El texto contiene igual proporción de sentimientos positivos y negativos

---

**Pregunta 3:**
¿Cuál es la diferencia principal entre Sentiment Analysis y Opinion Mining?

- [ ] A) Sentiment Analysis es más preciso que Opinion Mining  
- [x] B) Opinion Mining identifica sentimiento sobre aspectos específicos, Sentiment Analysis da tono general  
- [ ] C) Sentiment Analysis solo funciona en inglés, Opinion Mining en múltiples idiomas  
- [ ] D) No hay diferencia, son nombres diferentes del mismo servicio

---

**Pregunta 4:**
Azure AI Language analiza esta reseña:
"El hotel es hermoso pero muy caro. La ubicación es perfecta."

¿A qué niveles se analiza el sentimiento?

- [ ] A) Solo nivel de documento completo  
- [ ] B) Solo nivel de cada oración individual  
- [x] C) Nivel de documento Y nivel de cada oración  
- [ ] D) Nivel de palabra individual

---

**Pregunta 5:**
Los tres confidence scores de Sentiment Analysis siempre suman:

- [ ] A) 100  
- [x] B) 1.00  
- [ ] C) Depende del texto analizado  
- [ ] D) 3.00

---

**Pregunta 6:**
Una empresa quiere un dashboard que muestre:

- Batería: 85% menciones positivas
- Pantalla: 60% menciones negativas
- Cámara: 92% menciones positivas

¿Qué característica necesitan activar?

- [ ] A) Sentiment Analysis básico  
- [x] B) Opinion Mining  
- [ ] C) Key Phrase Extraction  
- [ ] D) Named Entity Recognition

---

### ✏️ SECCIÓN 2: EXTRACCIÓN DE INFORMACIÓN (6 preguntas)

**Pregunta 7:**
Un bufete de abogados necesita extraer automáticamente de 500 contratos: nombres de las partes, fechas de firma, montos económicos y ubicaciones de propiedades. ¿Qué servicio deben usar?

- [ ] A) Key Phrase Extraction  
- [ ] B) Sentiment Analysis  
- [x] C) Named Entity Recognition (NER)  
- [ ] D) Language Detection

---

**Pregunta 8:**
¿Cuál es la diferencia principal entre Key Phrase Extraction y Named Entity Recognition?

- [x] A) Key Phrases extrae conceptos generales, NER extrae entidades específicas nombradas  
- [ ] B) No hay diferencia, son el mismo servicio  
- [ ] C) Key Phrases solo funciona en inglés  
- [ ] D) NER requiere entrenamiento custom, Key Phrases no

---

**Pregunta 9:**
Un hospital debe asegurar que los logs de sus aplicaciones no contengan información médica personal de pacientes para cumplir con regulaciones. ¿Qué servicio necesitan?

- [ ] A) Sentiment Analysis  
- [x] B) PII Detection  
- [ ] C) Content Moderation  
- [ ] D) Named Entity Recognition

---
**Pregunta 10:**
¿Qué hace Entity Linking que NER básico NO hace?

- [ ] A) Detecta más tipos de entidades  
- [ ] B) Funciona en más idiomas  
- [x] C) Vincula entidades a Wikipedia para desambiguación  
-[ ] D) Tiene mejor precisión

---
**Pregunta 11:**
Una biblioteca digital con 50,000 artículos académicos quiere crear un sistema de búsqueda por temas principales. ¿Qué servicio es más apropiado?

- [ ] A) Named Entity Recognition  
- [x] B) Key Phrase Extraction  
- [ ] C) Sentiment Analysis  
- [ ] D) PII Detection

---

**Pregunta 12:**
PII Detection puede detectar (selecciona la FALSA):

- [ ] A) Direcciones de email  
- [ ] B) Números de tarjetas de crédito  
- [x] C) Contenido ofensivo  
- [ ] D) Números de teléfono

---

### ✏️ SECCIÓN 3: IDIOMAS Y TRADUCCIÓN (4 preguntas)

**Pregunta 13:**
Un call center global recibe tickets en 15 idiomas diferentes. Necesitan enrutar automáticamente cada ticket al equipo que habla ese idioma. ¿Qué servicio deben implementar PRIMERO?

- [ ] A) Translator  
- [x] B) Language Detection  
- [ ] C) Sentiment Analysis  
- [ ] D) Text-to-Speech

---

**Pregunta 14:**
Una empresa farmacéutica necesita traducir documentación técnica con terminología médica muy específica. ¿Qué característica de Azure Translator deben usar?

- [ ] A) Translator básico es suficiente  
- [x] B) Custom Translator  
- [ ] C) Speech Translation  
- [ ] D) Language Detection

---

**Pregunta 15:**
Azure Translator puede traducir entre aproximadamente:

- [ ] A) 10 idiomas  
- [ ] B) 50 idiomas  
- [x] C) 100+ idiomas  
- [ ] D) Solo idiomas europeos

---

**Pregunta 16:**
¿Cuántos recursos de Azure AI Language necesitas para soportar análisis de sentimiento en 20 idiomas diferentes?

- [x] A) 1 recurso (soporta múltiples idiomas)  
- [ ] B) 20 recursos (uno por idioma)  
- [ ] C) 5 recursos (uno por grupo de idiomas)  
- [ ] D) Depende del volumen de texto

---

### ✏️ SECCIÓN 4: SERVICIOS DE VOZ (5 preguntas)

**Pregunta 17:**
Una plataforma de educación online quiere generar subtítulos automáticos en tiempo real para sus clases en vivo. ¿Qué servicio necesitan?

- [ ] A) Text-to-Speech  
- [x] B) Speech-to-Text  
- [ ] C) Speech Translation  
- [ ] D) Speaker Recognition

---

**Pregunta 18:**
¿Qué es "diarización" en Speech-to-Text?

- [ ] A) Traducción de voz a múltiples idiomas  
- [x] B) Identificación y separación de múltiples hablantes  
- [ ] C) Mejora de calidad de audio  
- [ ] D) Conversión de voz a texto más rápido

---

**Pregunta 19:**
¿Cuál es la diferencia principal entre voces estándar y voces neurales en Text-to-Speech?

- [x] A) Voces neurales suenan mucho más naturales y expresivas  
- [ ] B) Voces estándar son más caras  
- [ ] C) Voces neurales solo funcionan en inglés  
- [ ] D) No hay diferencia de calidad

---

**Pregunta 20:**
Un banco quiere implementar autenticación por voz para transacciones telefónicas. ¿Qué servicio necesitan?

- [ ] A) Speech-to-Text  
- [ ] B) Text-to-Speech  
- [x] C) Speaker Recognition (Verification)  
- [ ] D) Speech Translation

---

**Pregunta 21:**
Speech Translation puede:

- [ ] A) Solo voz→texto traducido  
- [ ] B) Solo voz→voz traducida  
- [x] C) Tanto voz→texto como voz→voz traducida  
- [ ] D) Solo funciona con texto, no voz

---

### ✏️ SECCIÓN 5: CONVERSATIONAL AI (9 preguntas)

**Pregunta 22:**
Una empresa quiere crear un bot que responda preguntas sobre su política de recursos humanos usando el manual de empleados existente. ¿Qué servicio de Azure deben usar?

- [ ] A) Conversational Language Understanding (CLU)  
- [x] B) Question Answering  
- [ ] C) Sentiment Analysis  
- [ ] D) Named Entity Recognition

---

**Pregunta 23:**
¿Qué es un "Knowledge Base" en Question Answering?

- [ ] A) Una base de datos SQL  
- [x] B) Un conjunto de pares pregunta-respuesta  
- [ ] C) Un modelo de machine learning  
- [ ] D) Un servicio de almacenamiento

---

**Pregunta 24:**
¿Cuál es la diferencia principal entre Question Answering y CLU?

- [x] A) Question Answering da respuestas fijas de KB; CLU entiende intenciones para ejecutar acciones  
- [ ] B) CLU es más antiguo que Question Answering  
- [ ] C) Question Answering solo funciona con texto, CLU con voz  
- [ ] D) No hay diferencia

---

**Pregunta 25:**
Azure Bot Service permite publicar un bot en (selecciona la FALSA):

- [ ] A) Microsoft Teams  
- [ ] B) WhatsApp  
- [x] C) Instagram Direct  
- [ ] D) Facebook Messenger


---

**Pregunta 26:**
¿Qué son "Adaptive Cards" en Azure Bot Service?

- [ ] A) Tarjetas de crédito virtuales  
- [x] B) Mensajes ricos e interactivos con botones, imágenes y formularios  
- [ ] C) Algoritmos adaptativos de ML  
- [ ] D) Sistemas de autenticación

---

**Pregunta 27:**
En CLU (Conversational Language Understanding), ¿qué es un "Intent"?

- [ ] A) Una entidad específica mencionada por el usuario  
- [x] B) La intención o acción que el usuario quiere realizar  
- [ ] C) Un idioma soportado  
- [ ] D) Un canal de comunicación

---

 **Pregunta 28:**
 Una aerolínea quiere un bot que permita a usuarios reservar, cancelar y cambiar vuelos. ¿Qué combinación de servicios necesitan?
 
- [ ] A) Solo Question Answering  
- [x] B) CLU + Bot Service  
- [ ] C) Solo Sentiment Analysis  
- [ ] D) Solo Bot Service
 
---
 
**Pregunta 29:**
¿Qué es "Active Learning" en Question Answering?

- [ ] A) Entrenamiento manual constante del modelo  
- [x] B) Sistema aprende automáticamente de preguntas reales de usuarios  
- [ ] C) Actualización diaria de la knowledge base  
- [ ] D) Uso de reinforcement learning

---

**Pregunta 30:**
Un bot necesita recordar el nombre del usuario entre conversaciones diferentes (días diferentes). ¿Qué tipo de estado debe usar?

- [ ] A) Conversation State  
- [x] B) User State  
- [ ] C) Private State  
- [ ] D) Session State

---

## 📊 RESPUESTAS DEL MINI EXAMEN

### ✅ SECCIÓN 1: SENTIMENT ANALYSIS & OPINION MINING

**Pregunta 1: B) Opinion Mining**

- Razón: Necesitan identificar sentimiento sobre características ESPECÍFICAS (batería, pantalla, etc.)
- Opinion Mining identifica Target + Assessment + Sentiment
- Sentiment Analysis solo daría tono general

**Pregunta 2: B) El texto tiene sentimiento predominantemente negativo**

- negative: 0.65 (65%) es el score más alto
- Los scores suman 1.00 correctamente (0.15 + 0.20 + 0.65 = 1.00)
- Score alto en negative indica sentimiento negativo

**Pregunta 3: B) Opinion Mining identifica sentimiento sobre aspectos específicos, Sentiment Analysis da tono general**

- Sentiment: "La reseña es positiva" (general)
- Opinion Mining: "Comida: positiva, Servicio: negativa" (granular)

**Pregunta 4: C) Nivel de documento Y nivel de cada oración**

- Azure AI Language SIEMPRE analiza ambos niveles
- Documento: sentimiento general del texto completo
- Oraciones: sentimiento de cada oración individual

**Pregunta 5: B) 1.00**

- positive + neutral + negative = 1.00 SIEMPRE
- Ejemplo: 0.70 + 0.20 + 0.10 = 1.00

**Pregunta 6: B) Opinion Mining**

- Necesitan sentimiento POR ASPECTO (batería, pantalla, cámara)
- Opinion Mining identifica targets y sentimiento sobre cada uno
- Permite crear dashboard por característica

---

### ✅ SECCIÓN 2: EXTRACCIÓN DE INFORMACIÓN

**Pregunta 7: C) Named Entity Recognition (NER)**

- NER extrae entidades específicas: nombres (Person), fechas (DateTime), montos (Quantity), ubicaciones (Location)
- Perfecto para contratos donde necesitas datos estructurados
- Key Phrases extraería conceptos generales, no datos específicos

**Pregunta 8: A) Key Phrases extrae conceptos generales, NER extrae entidades específicas nombradas**

- Key Phrases: "machine learning", "inteligencia artificial" (temas)
- NER: "Microsoft", "Madrid", "15 de marzo" (entidades específicas)

**Pregunta 9: B) PII Detection**

- PII = Personally Identifiable Information
- Detecta y redacta información médica personal
- Esencial para HIPAA, GDPR compliance
- Content Moderation es para contenido ofensivo, NO para datos personales

**Pregunta 10: C) Vincula entidades a Wikipedia para desambiguación**

- Entity Linking = NER + Wikipedia
- Ejemplo: "Gates" → Bill Gates (persona) vs Gates of Heaven (lugar)
- Desambigua significados múltiples

**Pregunta 11: B) Key Phrase Extraction**

- Extrae temas/conceptos principales de artículos
- Perfecto para indexación y búsqueda por tema
- NER extraería nombres/fechas, no temas conceptuales

**Pregunta 12: C) Contenido ofensivo**

- PII Detection: emails, teléfonos, tarjetas, DNI, direcciones ✅
- Content Moderation: contenido ofensivo (servicio diferente)
- NO confundir PII con moderación de contenido

---

### ✅ SECCIÓN 3: IDIOMAS Y TRADUCCIÓN

**Pregunta 13: B) Language Detection**

- PRIMER paso: identificar idioma
- LUEGO: enrutar al equipo correcto
- Translator vendría después si necesitan traducir

**Pregunta 14: B) Custom Translator**

- Terminología médica específica requiere modelo personalizado
- Custom Translator se entrena con tu glosario/documentación
- Translator básico podría fallar con términos técnicos

**Pregunta 15: C) 100+ idiomas**

- Azure Translator soporta más de 100 idiomas
- Detección automática de idioma origen
- Neural Machine Translation (NMT)

**Pregunta 16: A) 1 recurso (soporta múltiples idiomas)**

- UN solo recurso de Azure AI Language soporta 120+ idiomas
- NO necesitas recursos separados por idioma
- Muy importante para el examen

---

### ✅ SECCIÓN 4: SERVICIOS DE VOZ

**Pregunta 17: B) Speech-to-Text**

- Subtítulos = Transcribir voz a texto
- Tiempo real = Speech-to-Text en modo streaming
- Text-to-Speech es texto→voz, NO voz→texto

**Pregunta 18: B) Identificación y separación de múltiples hablantes**

- Diarización detecta cuántas personas hablan
- Etiqueta quién dijo qué
- Útil en reuniones, entrevistas

**Pregunta 19: A) Voces neurales suenan mucho más naturales y expresivas**

- Neural TTS usa deep learning
- Entonación realista, emociones
- Más costoso pero mucho mejor calidad

**Pregunta 20: C) Speaker Recognition (Verification)**

- Verification: verifica identidad por voz
- "¿Es esta persona quien dice ser?"
- Autenticación biométrica
- Identification sería "¿Quién es?" (diferente)

**Pregunta 21: C) Tanto voz→texto como voz→voz traducida**

- Modo 1: Hablas español → Texto en inglés
- Modo 2: Hablas español → Voz en inglés
- Ambos modos soportados

---

### ✅ SECCIÓN 5: CONVERSATIONAL AI

**Pregunta 22: B) Question Answering**

- Tienen documento existente (manual de RR.HH.)
- Necesitan FAQ automático
- Question Answering perfecto: carga doc → crea KB
- CLU sería para acciones (reservar, cancelar), no FAQs

**Pregunta 23: B) Un conjunto de pares pregunta-respuesta**

- Knowledge Base = Base de conocimientos
- Contiene preguntas y sus respuestas
- Puede crearse desde docs, URLs, o manual

**Pregunta 24: A) Question Answering da respuestas fijas de KB; CLU entiende intenciones para ejecutar acciones**

- QnA: "¿Horario?" → "9-6" (respuesta fija)
- CLU: "Quiero reservar" → INTENT: Reservar → EJECUTA acción

**Pregunta 25: C) Instagram Direct**

- Teams ✅, WhatsApp ✅, Facebook Messenger ✅
- Instagram Direct NO está en canales oficiales
- Slack, Telegram, Web, Email también soportados

**Pregunta 26: B) Mensajes ricos e interactivos con botones, imágenes y formularios**

- Adaptive Cards = UI rica
- Botones, imágenes, formularios
- Mejor que solo texto plano

**Pregunta 27: B) La intención o acción que el usuario quiere realizar**

- Intent = Intención
- Ejemplos: ReservarVuelo, CancelarReserva, ConsultarEstado
- "¿QUÉ quiere hacer el usuario?"

**Pregunta 28: B) CLU + Bot Service**

- Reservar/Cancelar/Cambiar = ACCIONES → CLU
- Bot Service para interfaz y canales
- Question Answering sería solo para FAQs informativos

**Pregunta 29: B) Sistema aprende automáticamente de preguntas reales de usuarios**

- Active Learning mejora el bot con uso
- Sugiere asociaciones de preguntas nuevas
- Sistema se auto-mejora

**Pregunta 30: B) User State**

- User State persiste entre conversaciones
- Conversation State solo dura la conversación actual
- User State: nombre, preferencias, historial

---

## 📊 TABLA DE PUNTUACIÓN

### Calcula tu puntaje:

```
_____ / 30 respuestas correctas

EVALUACIÓN:

28-30 (93-100%): ✅ EXCELENTE - Listo para el examen
25-27 (83-90%):  ✅ MUY BIEN - Pequeño repaso
21-24 (70-83%):  ⚠️ BIEN - Repasa áreas débiles
18-20 (60-69%):  ⚠️ REGULAR - Más estudio necesario
<18 (<60%):      ❌ INSUFICIENTE - Repasa toda la semana

PUNTUACIÓN MÍNIMA PARA APROBAR AI-900 REAL: 700/1000 (70%)
```

---

### 📈 Análisis por Sección:

```
SECCIÓN 1 (Sentiment): ___/6
SECCIÓN 2 (Extracción): ___/6
SECCIÓN 3 (Idiomas): ___/4
SECCIÓN 4 (Voz): ___/5
SECCIÓN 5 (Conversational AI): ___/9

IDENTIFICA TU ÁREA MÁS DÉBIL:
La sección con menos % → REPASA ESA PARTE

Si <4/6 en Sentiment → Repasa lunes-martes
Si <4/6 en Extracción → Repasa complemento
Si <3/4 en Idiomas → Repasa miércoles
Si <3/5 en Voz → Repasa miércoles
Si <6/9 en Conversational → Repasa jueves
```

---

## 📖 PARTE 5: PLAN DE ACCIÓN POST-EXAMEN (15 min)

### ✅ Si sacaste 25+ (83%+)

```
¡EXCELENTE TRABAJO! 🎉

PLAN:
1. Repasa rápido las 2-3 que fallaste
2. Crea flashcards de esos conceptos
3. LISTO para Semana 5 (Generative AI)
4. Confianza alta para AI-900 en NLP

MANTÉN EL RITMO:
✅ Repasa flashcards 10 min/día
✅ Continúa con roadmap
✅ No bajes la guardia
```

---

### ⚠️ Si sacaste 21-24 (70-83%)

```
BIEN, pero hay margen de mejora

PLAN:
1. Identifica tu sección más débil
2. Re-estudia esa lección específica
3. Haz las flashcards de esa sección
4. Toma el examen nuevamente en 2 días

ENFÓCATE EN:
- Diferencias entre servicios
- Cuándo usar cada uno
- Casos de uso específicos
```

---

### ❌ Si sacaste <21 (menos de 70%)

```
NECESITAS MÁS ESTUDIO - No te desanimes

PLAN:
1. Re-estudia TODA la semana 4
2. Ve los videos de Microsoft Learn
3. Haz labs prácticos
4. Crea todas las flashcards
5. Retoma este examen en 3-4 días

RECURSOS ADICIONALES:
- Microsoft Learn: Rutas de AI-900
- Azure AI Language demos online
- Práctica con servicios gratuitos

NO AVANCES a Semana 5 hasta dominar NLP
```

---

## 🎴 FLASHCARDS - CONSOLIDACIÓN FINAL

### Repasa estas 15 flashcards críticas:

**Decisiones Rápidas:**

1. **P:** ¿Sentiment Analysis o Opinion Mining para análisis detallado?  
   **R:** Opinion Mining (sentimiento por aspecto específico)

2. **P:** ¿Key Phrases o NER para extraer nombres de personas?  
   **R:** NER (entidades específicas nombradas)

3. **P:** ¿QnA o CLU para un bot que procesa reservas?  
   **R:** CLU (entiende intenciones y ejecuta acciones)

4. **P:** ¿Primer paso antes de traducir texto desconocido?  
   **R:** Language Detection (identificar idioma)

5. **P:** ¿Speech-to-Text o Text-to-Speech para subtítulos?  
   **R:** Speech-to-Text (voz→texto)

**Datos Clave:**

6. **P:** Confidence scores de Sentiment suman:  
   **R:** 1.00 SIEMPRE

7. **P:** Azure Translator soporta cuántos idiomas:  
   **R:** 100+

8. **P:** Recursos necesarios para 20 idiomas en Azure AI Language:  
   **R:** 1 solo recurso

9. **P:** Categorías principales de NER:  
   **R:** Person, Location, Organization, DateTime, Quantity, Email, Product, Event, Skill

10. **P:** Qué detecta PII Detection:  
    **R:** Información personal sensible (email, teléfono, DNI, tarjetas)

**Diferencias Críticas:**

11. **P:** Diferencia Sentiment vs Opinion Mining:  
    **R:** Sentiment=tono general; Opinion Mining=sentimiento por aspecto

12. **P:** Diferencia Key Phrases vs NER:  
    **R:** Key Phrases=conceptos generales; NER=entidades específicas

13. **P:** Diferencia QnA vs CLU:  
    **R:** QnA=respuestas fijas; CLU=entender intenciones para acciones

14. **P:** Diferencia voces estándar vs neurales:  
    **R:** Neurales=mucho más naturales y expresivas (pero más caras)

15. **P:** Diferencia Speaker Verification vs Identification:  
    **R:** Verification="¿es quien dice?"; Identification="¿quién es?"

---

## ✅ CHECKLIST FINAL DE LA SEMANA 4

Marca todo lo que dominas:

### 📚 Contenido Teórico:

- [ ] Entiendo todos los servicios de Azure AI Language
- [ ] Puedo diferenciar entre servicios similares
- [ ] Conozco casos de uso reales de cada servicio
- [ ] Entiendo cuándo usar cada servicio

### 🎯 Habilidades Prácticas:

- [ ] Puedo resolver preguntas tipo examen
- [ ] Identifico rápidamente el servicio correcto para cada escenario
- [ ] Entiendo arquitecturas de bots
- [ ] Conozco los canales de Bot Service

### 📝 Preparación para Examen:

- [ ] He creado todas las flashcards de la semana (40+)
- [ ] He hecho el mini examen completo
- [ ] Saqué 70%+ en el mini examen
- [ ] Identifiqué y repasé mis áreas débiles

---

## 🎯 PRÓXIMOS PASOS

### 📅 Fin de Semana (30 Nov - 1 Dic):

```
DESCANSO ACTIVO:

Sábado:
- Repasa flashcards: 20 minutos
- Re-toma el mini examen si sacaste <25

Domingo:
- Descanso mental
- Repasa solo las flashcards críticas: 10 min
```

---

### 📅 Semana 5 - Generative AI (2-6 Dic):

```
TEMAS QUE VERÁS:

Lunes: Introducción a IA Generativa
Martes: Azure OpenAI Service
Miércoles: Prompts y Tokens
Jueves: Responsible AI ⭐ (MUY IMPORTANTE)
Viernes: Repaso + Mini Examen GenAI
```

---

## 🎉 CONCLUSIÓN

**¡Felicidades por completar la Semana 4 de NLP!** 🎊

Has cubierto:

- ✅ 7 servicios de Azure AI Language
- ✅ 4 servicios de Azure Speech
- ✅ 3 servicios de Conversational AI
- ✅ 14 conceptos principales
- ✅ 40+ flashcards
- ✅ 30 preguntas de práctica

**Estás listo para:**

- Semana 5: Generative AI y Responsible AI
- Últimas semanas de preparación
- ¡El examen AI-900 real!

---

## 💡 REFLEXIÓN FINAL

**Pregunta para pensar este fin de semana:**

```
Si tuvieras que diseñar un bot para una empresa,
¿qué servicios de Azure combinarías y por qué?

Piensa en:
- ¿Solo FAQ o también acciones?
- ¿Qué canales usarías?
- ¿Necesitas análisis de sentimiento?
- ¿Soporte multilingüe?
```

Practica diseñando soluciones completas, ¡es lo que verás en el examen!

---

**¡Excelente trabajo esta semana! 🚀**  
**Tiempo total hoy:** ~2 horas  
**Progreso:** Semana 4 - ✅ COMPLETA

**¡Descansa y nos vemos el lunes en Generative AI! 💪**
