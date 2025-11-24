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
