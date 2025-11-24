# 📚 AI-900 | SEMANA 4 - LUNES 25 NOV

## 🗣️ Fundamentos de Natural Language Processing (NLP)

---

## 🎯 OBJETIVOS DEL DÍA

Al finalizar hoy, serás capaz de:

- ✅ Explicar qué es NLP y por qué es importante
- ✅ Identificar las tareas principales de NLP
- ✅ Diferenciar entre análisis sintáctico y semántico
- ✅ Entender los desafíos del lenguaje natural
- ✅ Conocer aplicaciones reales de NLP

**Tiempo estimado:** 1.5 horas  
**Nivel de dificultad:** ⭐⭐⚪⚪⚪ (Media-Baja)

---

## 📖 PARTE 1: ¿QUÉ ES NLP? (15 min)

### 🤔 Definición simple

**Natural Language Processing (NLP)** es la capacidad de las computadoras para **entender, interpretar y generar lenguaje humano** de forma útil.

```
EJEMPLO DIARIO:
Tú escribes: "¿Qué tiempo hará mañana en Madrid?"

NLP hace esto detrás de escena:
1. Tokenización: ["Qué", "tiempo", "hará", "mañana", "en", "Madrid"]
2. Análisis: Detecta que es una pregunta sobre clima
3. Extrae: ubicación = "Madrid", tiempo = "mañana"
4. Genera respuesta apropiada
```

### 🌟 ¿Por qué es difícil para las máquinas?

El lenguaje humano es **ambiguo, contextual y lleno de excepciones**:

**Ejemplo 1 - Ambigüedad:**

```
"Vi al hombre con el telescopio"
   ¿Quién tiene el telescopio?
   → ¿Yo usé un telescopio para verlo?
   → ¿Él tenía un telescopio?
```

**Ejemplo 2 - Contexto:**

```
"Hace frío aquí"
   Significado literal: temperatura baja
   Significado implícito: "¿Puedes cerrar la ventana?"
```

**Ejemplo 3 - Sarcasmo:**

```
"¡Qué día tan maravilloso!" (durante una tormenta)
   Las palabras dicen positivo
   El significado real es negativo
```

### 🎯 Objetivo de NLP

Permitir que las máquinas:

- **Entiendan** lo que los humanos dicen o escriben
- **Extraigan** información útil del texto
- **Generen** lenguaje natural coherente
- **Traduzcan** entre idiomas
- **Respondan** de forma apropiada

---

## 📖 PARTE 2: TAREAS PRINCIPALES DE NLP (25 min)

### 1️⃣ : **Análisis de Sentimiento**

Determinar si un texto expresa sentimiento positivo, negativo o neutral.

```
EJEMPLOS:

✅ Positivo: "¡Me encanta este producto! Superó mis expectativas"
   Sentimiento: POSITIVO (confianza: 98%)

❌ Negativo: "Terrible servicio, nunca volveré"
   Sentimiento: NEGATIVO (confianza: 95%)

😐 Neutral: "El producto llegó el martes por la tarde"
   Sentimiento: NEUTRAL (confianza: 92%)

🤔 Mixto: "El hotel es hermoso pero muy caro"
   Sentimiento: MIXTO (positivo + negativo)
```

**Casos de uso reales:**

- Monitorear reseñas de productos
- Analizar menciones en redes sociales
- Medir satisfacción del cliente
- Detectar crisis de reputación temprano

---

### 2️⃣:: **Reconocimiento de Entidades Nombradas (NER)**

Identificar y clasificar elementos importantes en el texto.

```
TEXTO: "Renszo trabaja en Microsoft en Madrid y usa React"

ENTIDADES DETECTADAS:
- Persona: "Renszo"
- Organización: "Microsoft"
- Ubicación: "Madrid"
- Tecnología: "React"
```

**Tipos de entidades comunes:**

- 👤 **Personas**: "Juan Pérez", "María García"
- 🏢 **Organizaciones**: "Google", "ONU", "Real Madrid"
- 📍 **Ubicaciones**: "España", "Calle Mayor", "Europa"
- 📅 **Fechas/Tiempo**: "25 de noviembre", "mañana", "2025"
- 💰 **Cantidades**: "100 euros", "50%", "3 metros"
- 🏛️ **Eventos**: "Mundial 2022", "Revolución Francesa"

**Casos de uso:**

- Extracción de información de contratos
- Análisis de noticias
- Búsqueda avanzada en documentos
- Categorización automática

---

### 3️⃣:: **Extracción de Frases Clave**

Identificar los conceptos o temas más importantes en un texto.

```
TEXTO:
"La inteligencia artificial está transformando la medicina moderna.
Los algoritmos de machine learning pueden detectar enfermedades
en imágenes médicas con precisión superior a los especialistas."

FRASES CLAVE EXTRAÍDAS:
- "inteligencia artificial"
- "medicina moderna"
- "algoritmos de machine learning"
- "imágenes médicas"
- "detección de enfermedades"
```

**Casos de uso:**

- Resúmenes automáticos de documentos
- Indexación de contenido
- Búsqueda y recuperación de información
- Categorización de artículos

---

### 4️⃣ : **Detección de Idioma**

Identificar en qué idioma está escrito un texto.

```
EJEMPLOS:

"Hello, how are you?" → 🇬🇧 Inglés (confianza: 99%)
"Hola, ¿cómo estás?" → 🇪🇸 Español (confianza: 99%)
"Bonjour, ça va?" → 🇫🇷 Francés (confianza: 98%)
```

**Casos de uso:**

- Enrutamiento de mensajes de soporte
- Análisis de contenido multilingüe
- Sistemas de traducción automática

---

### 5️⃣:: **Traducción Automática**

Convertir texto de un idioma a otro manteniendo el significado.

```
ESPAÑOL → INGLÉS:
"Me gustaría reservar una mesa para dos personas"
→ "I would like to book a table for two people"

RETOS:
- Modismos: "Estar en las nubes" ≠ "To be in the clouds"
- Contexto cultural
- Gramática diferente
```

---

### 6️⃣:: **Question Answering (Respuesta a Preguntas)**

Encontrar respuestas específicas en un texto dado.

```
CONTEXTO:
"Microsoft fue fundada en 1975 por Bill Gates y Paul Allen en Albuquerque.
La compañía se mudó a Redmond, Washington en 1979."

PREGUNTA: "¿Cuándo se fundó Microsoft?"
RESPUESTA: "1975"

PREGUNTA: "¿Dónde está la sede de Microsoft?"
RESPUESTA: "Redmond, Washington"
```

**Casos de uso:**

- Chatbots de soporte
- Asistentes virtuales
- Búsqueda en documentación
- FAQ automáticos

---

## 📖 PARTE 3: NIVELES DE ANÁLISIS DE TEXTO (20 min)

### 🔤 Nivel 1: Análisis Léxico

**Procesar palabras individuales**

```
TOKENIZACIÓN:
"Hola, ¿cómo estás?"
→ ["Hola", ",", "¿", "cómo", "estás", "?"]

NORMALIZACIÓN:
"ESCRIBIR", "escribir", "Escribir"
→ Todas se convierten a "escribir"

STEMMING (raíces):
"corriendo", "corrió", "correr"
→ Todas reducidas a "corr"
```

---

### 🔗 Nivel 2: Análisis Sintáctico

**Entender la estructura gramatical**

```
EJEMPLO:
"El gato persigue al ratón"

ANÁLISIS:
- Sujeto: "El gato"
- Verbo: "persigue"
- Objeto: "al ratón"

ÁRBOL SINTÁCTICO:
         [persigue]
            /    \
      [El gato]  [al ratón]
```

**¿Por qué importa?**
Ayuda a entender **quién hace qué a quién**.

---

### 🧠 Nivel 3: Análisis Semántico

**Entender el significado**

```
EJEMPLO 1:
"El banco está cerrado"
¿Qué "banco"?
   → ¿Institución financiera?
   → ¿Asiento en el parque?

Contexto: "Necesito sacar dinero pero el banco está cerrado"
→ AH! Es institución financiera

EJEMPLO 2:
"Tengo que romper el hielo"
   Significado literal: quebrar agua congelada ❌
   Significado real: iniciar conversación incómoda ✅
```

---

### 💭 Nivel 4: Análisis Pragmático

**Entender la intención y el contexto**

```
EJEMPLO:
Usuario: "Hace frío aquí"

ANÁLISIS DE NIVELES:
- Sintáctico: Oración declarativa simple ✅
- Semántico: Afirmación sobre temperatura ✅
- Pragmático: Petición indirecta de "cierra la ventana" ✅

La IA debe entender: "No solo informa, está PIDIENDO algo"
```

---

## 📖 PARTE 4: DESAFÍOS DE NLP (15 min)

### ⚠️ Desafío 1: Ambigüedad

```
EJEMPLO:
"Los expertos dicen que el virus es peligroso"

PREGUNTAS:
- ¿Qué expertos?
- ¿Qué virus?
- ¿Peligroso para quién?
- ¿Cuándo lo dijeron?
```

---

### ⚠️ Desafío 2: Cambios de Idioma

```
El español cambia:
- España 🇪🇸: "móvil", "ordenador", "coche"
- México 🇲🇽: "celular", "computadora", "carro"
- Argentina 🇦🇷: "celular", "computadora", "auto"
```

---

### ⚠️ Desafío 3: Neologismos y Jerga

```
PALABRAS NUEVAS:
2020: "COVID", "cuarentena", "videollamada"
2023: "ChatGPT", "prompt", "RAG"
2024: "IA generativa", "GPT-4"

¿Cómo enseñas esto a una máquina?
```

---

### ⚠️ Desafío 4: Contexto Cultural

```
MODISMO ESPAÑOL:
"Estar en la luna" = No prestar atención

Si traduces literalmente a inglés:
"To be on the moon" → No tiene sentido ❌

Traducción correcta:
"To have your head in the clouds" ✅
```

---

### ⚠️ Desafío 5: Sarcasmo e Ironía

```
TWEET durante lluvia intensa:
"¡Qué día tan perfecto para ir a la playa! ☀️😍"

ANÁLISIS ERRÓNEO:
Palabras positivas → Sentimiento positivo ❌

ANÁLISIS CORRECTO:
Contexto + ironía → Sentimiento negativo ✅
```

---

## 📖 PARTE 5: APLICACIONES REALES DE NLP (10 min)

### 📧 1. Email y Productividad

- **Gmail**: Respuestas inteligentes sugeridas
- **Outlook**: Detección de intención en emails
- **Grammarly**: Corrección gramatical y de estilo

---

### 🛍️ 2. E-commerce

- **Amazon**: Análisis de reseñas de productos
- **Chatbots**: Atención al cliente 24/7
- **Búsqueda semántica**: "zapatos deportivos rojos talla 42"

---

### 💼 3. Empresarial

- **Análisis de contratos**: Extracción de cláusulas importantes
- **Resúmenes ejecutivos**: De reportes largos
- **Clasificación de tickets**: Soporte técnico automático

---

### 🏥 4. Salud

- **Transcripción médica**: De consultas
- **Análisis de literatura médica**: Papers científicos
- **Detección de síntomas**: En descripciones de pacientes

---

### 📱 5. Redes Sociales

- **Moderación de contenido**: Detectar spam/hate speech
- **Análisis de tendencias**: Qué temas son populares
- **Monitoreo de marca**: Menciones y sentiment

---

## 🎯 CONCEPTOS CLAVE PARA EL EXAMEN AI-900

### ✅ DEBES SABER:

1. **NLP** = Natural Language Processing = Procesamiento de Lenguaje Natural

2. **Tareas principales:**
   - Análisis de sentimiento
   - Reconocimiento de entidades (NER)
   - Extracción de frases clave
   - Detección de idioma
   - Traducción
   - Question Answering

3. **Niveles de análisis:**
   - Léxico (palabras)
   - Sintáctico (gramática)
   - Semántico (significado)
   - Pragmático (intención)

4. **Desafíos:**
   - Ambigüedad
   - Variaciones de idioma
   - Contexto cultural
   - Sarcasmo/ironía
   - Neologismos

---

## 📝 EJERCICIO PRÁCTICO (15 min)

### Tarea 1: Identificar tareas de NLP

Para cada ejemplo, identifica qué tarea de NLP se está usando:

```
1. "Esta película es horrible" → Detecta: NEGATIVO
   RESPUESTA: _________________

2. "Apple lanzó iPhone en California el 9 de enero"
   Detecta: Apple (empresa), iPhone (producto), California (lugar)
   RESPUESTA: _________________

3. "Hello" → Detecta: Inglés
   RESPUESTA: _________________

4. "IA, machine learning, deep learning, neural networks"
   RESPUESTA: _________________

5. "I love programming" → "Me encanta programar"
   RESPUESTA: _________________
```

**RESPUESTAS:**

1. Análisis de sentimiento
2. Reconocimiento de entidades nombradas (NER)
3. Detección de idioma
4. Extracción de frases clave
5. Traducción automática

---

### Tarea 2: Análisis de niveles

Para esta frase: **"El banco cerró la cuenta"**

1. **Análisis léxico**: ¿Cuántas palabras?
2. **Análisis sintáctico**: ¿Quién es el sujeto?
3. **Análisis semántico**: ¿Qué "banco"? (Necesitas contexto)
4. **Análisis pragmático**: ¿Por qué lo dice el usuario?

---

## 🎴 FLASHCARDS PARA HOY

Crea estas 10 flashcards:

1. **P:** ¿Qué es NLP?  
   **R:** Natural Language Processing - capacidad de las máquinas para entender y generar lenguaje humano

2. **P:** ¿Qué es análisis de sentimiento?  
   **R:** Determinar si un texto expresa sentimiento positivo, negativo o neutral

3. **P:** ¿Qué es NER?  
   **R:** Named Entity Recognition - identificar y clasificar entidades como personas, lugares, organizaciones

4. **P:** ¿Qué es extracción de frases clave?  
   **R:** Identificar los conceptos o temas más importantes en un texto

5. **P:** ¿Cuáles son los 4 niveles de análisis de texto?  
   **R:** Léxico, sintáctico, semántico y pragmático

6. **P:** ¿Qué es tokenización?  
   **R:** Dividir texto en unidades más pequeñas (palabras, caracteres, subpalabras)

7. **P:** ¿Por qué es difícil NLP?  
   **R:** Ambigüedad, contexto, sarcasmo, variaciones de idioma, contexto cultural

8. **P:** ¿Qué es Question Answering?  
   **R:** Encontrar respuestas específicas a preguntas dentro de un texto dado

9. **P:** ¿Qué hace la traducción automática?  
   **R:** Convertir texto de un idioma a otro manteniendo el significado

10. **P:** Ejemplo de ambigüedad en NLP  
    **R:** "Vi al hombre con el telescopio" - ¿Quién tiene el telescopio?

---

## 📚 RECURSOS ADICIONALES

### 🔗 Microsoft Learn (GRATIS):

- "Analyze text with Azure AI Language"
- "Introduction to Natural Language Processing"
- "Text Analytics Overview"

### 📖 Lectura complementaria:

- Documentación de Azure AI Language: https://learn.microsoft.com/azure/ai-services/language-service/

---

## ✅ CHECKLIST DE HOY

Antes de terminar, verifica:

- [ ] Entiendo qué es NLP y por qué es importante
- [ ] Puedo nombrar al menos 5 tareas de NLP
- [ ] Entiendo los 4 niveles de análisis de texto
- [ ] Conozco los principales desafíos de NLP
- [ ] Puedo dar ejemplos de aplicaciones reales
- [ ] He creado las 10 flashcards
- [ ] He completado los ejercicios prácticos

---

# 📝 PREGUNTAS ESTILO EXAMEN MICROSOFT AI-900

## Tema: Fundamentos de NLP

---

## ❓ PREGUNTA 1 - Escenario de E-commerce

**ESCENARIO:**
Una empresa de comercio electrónico recibe miles de reseñas de productos diariamente. Quieren automatizar el proceso de identificar qué reseñas son positivas, negativas o neutras para priorizar la atención al cliente en casos negativos.

**PREGUNTA:**
¿Qué capacidad de Azure AI Language deberían usar?

**A)** Named Entity Recognition (NER)  
**B)** Key Phrase Extraction  
**C)** Sentiment Analysis  
**D)** Language Detection

<details>
<summary>👉 Ver respuesta correcta</summary>

**RESPUESTA CORRECTA: C) Sentiment Analysis**

**EXPLICACIÓN:**

- **Sentiment Analysis** (Análisis de sentimiento) es la capacidad de NLP que determina si un texto expresa sentimiento positivo, negativo o neutral
- Es perfecta para analizar reseñas de productos y clasificarlas automáticamente
- Permite priorizar respuestas a clientes insatisfechos (sentimiento negativo)

**Por qué las otras son incorrectas:**

- **A) NER**: Identifica entidades como nombres, lugares, fechas - no determina sentimiento
- **B) Key Phrase Extraction**: Extrae temas principales pero no determina si son positivos o negativos
- **D) Language Detection**: Solo identifica el idioma del texto, no el sentimiento

**TIP PARA EL EXAMEN:**
Cuando veas escenarios sobre "opiniones", "satisfacción", "positivo/negativo", "reseñas" → piensa en **Sentiment Analysis**

</details>

---

## ❓ PREGUNTA 2 - Escenario de Documentos Legales

**ESCENARIO:**
Un bufete de abogados necesita procesar cientos de contratos y extraer automáticamente información específica como: nombres de las partes involucradas, fechas de firma, montos económicos, y ubicaciones de las propiedades mencionadas.

**PREGUNTA:**
¿Qué tarea de NLP es la más apropiada para este escenario?

**A)** Sentiment Analysis  
**B)** Named Entity Recognition (NER)  
**C)** Translation  
**D)** Key Phrase Extraction

<details>
<summary>👉 Ver respuesta correcta</summary>

**RESPUESTA CORRECTA: B) Named Entity Recognition (NER)**

**EXPLICACIÓN:**

- **Named Entity Recognition** identifica y clasifica entidades específicas en el texto:
  - **Personas**: "Juan Pérez", "María García"
  - **Fechas**: "15 de marzo de 2025"
  - **Cantidades monetarias**: "50,000 euros"
  - **Ubicaciones**: "Madrid", "Calle Principal 123"
- Es ideal para **extracción de información estructurada** de documentos

**Por qué las otras son incorrectas:**

- **A) Sentiment Analysis**: Detecta emociones, no extrae información específica
- **C) Translation**: Traduce entre idiomas, no extrae datos
- **D) Key Phrase Extraction**: Extrae temas generales, pero no clasifica tipos específicos de entidades

**TIP PARA EL EXAMEN:**
Cuando veas escenarios sobre "extraer nombres, fechas, lugares, cantidades" → piensa en **Named Entity Recognition (NER)**

</details>

---

## ❓ PREGUNTA 3 - Escenario de Soporte Multilingüe

**ESCENARIO:**
Una empresa global recibe tickets de soporte de clientes en múltiples idiomas (inglés, español, francés, alemán, japonés). Necesitan enrutar automáticamente cada ticket al equipo de soporte que habla ese idioma específico.

**PREGUNTA:**
¿Qué capacidad de Azure AI Language deben implementar PRIMERO?

**A)** Language Detection  
**B)** Translation  
**C)** Sentiment Analysis  
**D)** Entity Recognition

<details>
<summary>👉 Ver respuesta correcta</summary>

**RESPUESTA CORRECTA: A) Language Detection**

**EXPLICACIÓN:**

- **Language Detection** identifica en qué idioma está escrito un texto
- Es el **primer paso necesario** antes de poder enrutar o traducir
- Permite clasificar y dirigir automáticamente cada ticket al equipo correcto
- Azure AI Language puede detectar más de 120 idiomas

**Por qué las otras son incorrectas:**

- **B) Translation**: Útil después, pero primero necesitas SABER qué idioma es
- **C) Sentiment Analysis**: Ayuda a priorizar urgencia, pero no resuelve el enrutamiento por idioma
- **D) Entity Recognition**: Extrae información, pero no identifica el idioma

**TIP PARA EL EXAMEN:**
Cuando veas "enrutar por idioma", "clasificar por lenguaje", "soporte multilingüe" → piensa en **Language Detection** como primer paso

</details>

---

## ❓ PREGUNTA 4 - Escenario de Análisis de Documentos

**ESCENARIO:**
Una universidad necesita analizar miles de trabajos de investigación para crear un sistema de búsqueda. Quieren que los usuarios puedan buscar papers por tema principal sin tener que leer todo el documento. Por ejemplo, si buscan "inteligencia artificial", el sistema debería devolver papers donde IA sea un tema central.

**PREGUNTA:**
¿Qué característica de Azure AI Language es la más adecuada?

**A)** Sentiment Analysis  
**B)** Language Detection  
**C)** Key Phrase Extraction  
**D)** Named Entity Recognition

<details>
<summary>👉 Ver respuesta correcta</summary>

**RESPUESTA CORRECTA: C) Key Phrase Extraction**

**EXPLICACIÓN:**

- **Key Phrase Extraction** identifica los temas y conceptos principales de un texto
- Extrae automáticamente las frases más importantes sin necesidad de leer todo
- Perfecto para:
  - Indexación de documentos
  - Sistemas de búsqueda por tema
  - Categorización automática
  - Generación de etiquetas (tags)

**Ejemplo:**

```
TEXTO: "La inteligencia artificial está transformando la medicina.
Los algoritmos de machine learning detectan enfermedades en imágenes."

KEY PHRASES EXTRAÍDAS:
- "inteligencia artificial"
- "medicina"
- "algoritmos de machine learning"
- "detección de enfermedades"
```

**Por qué las otras son incorrectas:**

- **A) Sentiment Analysis**: Detecta emociones, no temas principales
- **B) Language Detection**: Solo identifica el idioma
- **D) NER**: Extrae entidades específicas (nombres, fechas), no temas conceptuales

**TIP PARA EL EXAMEN:**
Cuando veas "temas principales", "conceptos clave", "indexación", "categorización" → piensa en **Key Phrase Extraction**

</details>

---

## ❓ PREGUNTA 5 - Escenario de Chatbot FAQ

**ESCENARIO:**
Una empresa quiere crear un chatbot que responda preguntas frecuentes de los clientes. El chatbot debe poder leer una base de conocimientos (documentación, manuales, FAQs) y encontrar la respuesta específica cuando un cliente hace una pregunta.

Ejemplo:

- **Cliente pregunta:** "¿Cuál es el horario de atención?"
- **El bot busca en la documentación** y encuentra: "Nuestro horario de atención es de lunes a viernes de 9:00 a 18:00"
- **El bot responde:** "De lunes a viernes de 9:00 a 18:00"

**PREGUNTA:**
¿Qué capacidad de Azure AI necesitan implementar?

**A)** Sentiment Analysis  
**B)** Question Answering  
**C)** Key Phrase Extraction  
**D)** Language Translation

<details>
<summary>👉 Ver respuesta correcta</summary>

**RESPUESTA CORRECTA: B) Question Answering**

**EXPLICACIÓN:**

- **Question Answering** (anteriormente QnA Maker) es específicamente diseñado para:
  - Buscar respuestas en una base de conocimientos
  - Extraer la respuesta exacta a una pregunta
  - Crear chatbots y asistentes virtuales
  - Mantener una base de pares pregunta-respuesta

**Cómo funciona:**

```
1. Cargas tu documentación/FAQs
2. El servicio indexa el contenido
3. Usuario hace pregunta
4. El sistema encuentra la respuesta más relevante
5. Devuelve la respuesta con un "confidence score"
```

**Por qué las otras son incorrectas:**

- **A) Sentiment Analysis**: Detecta emociones, no responde preguntas
- **C) Key Phrase Extraction**: Extrae temas, pero no busca respuestas específicas
- **D) Translation**: Traduce idiomas, no responde preguntas

**TIP PARA EL EXAMEN:**
Cuando veas "chatbot", "FAQ", "responder preguntas", "base de conocimientos" → piensa en **Question Answering**

</details>

---

## 🎯 RESUMEN DE PATRONES PARA EL EXAMEN

### 🔍 Identifica estas palabras clave:

| **Si ves esto...**                                           | **Piensa en...**                   |
| ------------------------------------------------------------ | ---------------------------------- |
| Opiniones, reseñas, positivo/negativo, satisfacción          | **Sentiment Analysis**             |
| Nombres, fechas, lugares, cantidades, organizaciones         | **Named Entity Recognition (NER)** |
| Temas principales, conceptos, indexación, categorización     | **Key Phrase Extraction**          |
| Detectar idioma, enrutar por lenguaje, clasificar por idioma | **Language Detection**             |
| Traducir, convertir entre idiomas                            | **Translation**                    |
| Chatbot, FAQ, responder preguntas, base de conocimientos     | **Question Answering**             |

---

## 📊 PUNTUACIÓN

Marca cuántas respondiste correctamente:

- [ ] Pregunta 1 - E-commerce (Sentiment Analysis)
- [ ] Pregunta 2 - Documentos Legales (NER)
- [ ] Pregunta 3 - Soporte Multilingüe (Language Detection)
- [ ] Pregunta 4 - Análisis de Documentos (Key Phrase Extraction)
- [ ] Pregunta 5 - Chatbot FAQ (Question Answering)

### Evaluación:

- **5/5 correctas** ✅ ¡Excelente! Dominas los conceptos
- **4/5 correctas** 👍 Muy bien, repasa la que fallaste
- **3/5 correctas** 📚 Bien, revisa los conceptos principales
- **2 o menos** 🔄 Repasa la lección de hoy

---

## 💡 TIPS FINALES PARA EL EXAMEN

### 1️⃣:: **Lee el escenario COMPLETO**

No te apresures. Microsoft pone información clave en todo el texto.

### 2️⃣:: **Identifica el OBJETIVO principal**

Pregúntate: ¿Qué problema están tratando de resolver?

### 3️⃣:: **Busca palabras clave**

"opinión" → Sentiment  
"extraer nombres/fechas" → NER  
"temas" → Key Phrases  
"responder preguntas" → Question Answering

### 4️⃣:: **Elimina opciones obviamente incorrectas**

Reduce las opciones antes de decidir.

### 5️⃣:: **En caso de duda**

Pregunta: ¿Cuál es la tarea MÁS ESPECÍFICA para este problema?

---

## 🎓 PARA PRACTICAR MÁS

**Crea tus propios escenarios:**

1. Piensa en un caso de uso real
2. Pregúntate: ¿Qué tarea de NLP necesito?
3. Verifica tu respuesta con los patrones de arriba

**Ejemplos:**

- "Analizar tweets sobre una marca" → ¿Qué usarías?
- "Extraer direcciones de correos" → ¿Qué usarías?
- "Traducir un sitio web" → ¿Qué usarías?

---

**¡Sigue practicando! Estas preguntas son muy similares a las del examen real. 💪**

## 🎯 PARA MAÑANA (Martes 26 Nov)

**Tema:** Azure AI Language - Análisis de texto y sentimiento

Prepárate para:

- Conocer Azure AI Language service
- Entender análisis de sentimiento en profundidad
- Aprender sobre detección de opiniones
- Ver ejemplos de uso real

---

## 💡 REFLEXIÓN FINAL

**Pregunta para pensar:**
¿Qué tarea de NLP usarías para analizar comentarios de clientes en tu empresa y detectar automáticamente quejas urgentes?

---

**¡Excelente trabajo hoy! 🎉**  
Has dado el primer paso en el mundo de NLP. Mañana profundizaremos en Azure AI Language.

**Tiempo total:** ~1.5 horas  
**Progreso:** Semana 4 - Día 1/6 ✅
