# AI-900 Certification - Semana 5, Día 3

## Prompts y Tokens

**Fecha:** Miércoles, Semana 5  
**Duración estimada:** 45-60 minutos  
**Nivel:** Fundamental

---

## 📋 Objetivos del día

- Comprender qué son los tokens y cómo funcionan
- Aprender técnicas efectivas de prompt engineering
- Conocer estrategias para optimizar el uso de tokens
- Entender el concepto de context window
- Dominar los elementos de un buen prompt

---

## 1. ¿Qué son los Tokens?

### Definición

Los **tokens** son las unidades básicas de procesamiento de texto en los modelos de lenguaje. Un token puede ser:
- Una palabra completa
- Parte de una palabra
- Un carácter especial
- Espacios y puntuación

### ¿Cómo funciona la tokenización?

Los modelos no procesan texto directamente, sino que lo dividen en tokens primero.

**Ejemplos de tokenización:**

```
Texto: "Hola mundo"
Tokens: ["Hola", " mundo"]
Total: 2 tokens

Texto: "OpenAI es increíble"
Tokens: ["Open", "AI", " es", " incre", "íble"]
Total: 5 tokens

Texto: "¡Fantástico!"
Tokens: ["¡", "Fant", "ást", "ico", "!"]
Total: 5 tokens

Texto: "AI-900"
Tokens: ["AI", "-", "900"]
Total: 3 tokens
```

### Reglas generales de tokenización

**Para inglés:**
- ~1 token ≈ 4 caracteres
- ~1 token ≈ 0.75 palabras
- ~100 tokens ≈ 75 palabras

**Para español:**
- ~1 token ≈ 3-4 caracteres
- ~1 token ≈ 0.65 palabras
- ~100 tokens ≈ 65 palabras

**Nota:** El español y otros idiomas no ingleses tienden a usar más tokens por palabra debido a:
- Acentos y caracteres especiales
- Palabras más largas
- Menor representación en datos de entrenamiento

### ¿Por qué importan los tokens?

1. **Límites del modelo**: Cada modelo tiene un límite máximo de tokens (context window)
2. **Costos**: Se cobra por token procesado (input + output)
3. **Rendimiento**: Más tokens = más tiempo de procesamiento

### Herramientas para contar tokens

**OpenAI Tokenizer:**
- https://platform.openai.com/tokenizer
- Permite ver exactamente cómo se tokeniza tu texto

**Ejemplo práctico:**
```
Entrada: "Azure OpenAI Service es una plataforma empresarial"
Vista tokenizada: ["Azure", " Open", "AI", " Service", " es", " una", " plat", "aforma", " empres", "arial"]
Total tokens: 10
```

---

## 2. Context Window (Ventana de Contexto)

### Definición

El **context window** es la cantidad máxima de tokens que un modelo puede procesar en una sola solicitud (prompt + respuesta).

### Límites por modelo

| Modelo | Context Window | Aproximado en palabras |
|--------|----------------|------------------------|
| GPT-3.5-turbo | 4,096 tokens | ~3,000 palabras |
| GPT-3.5-turbo-16k | 16,384 tokens | ~12,000 palabras |
| GPT-4 | 8,192 tokens | ~6,000 palabras |
| GPT-4-32k | 32,768 tokens | ~24,000 palabras |
| GPT-4-turbo | 128,000 tokens | ~96,000 palabras |
| GPT-5 (ChatGPT) | 256,000 tokens | ~190,000 palabras |
| GPT-5 (API) | 400,000 tokens | ~300,000 palabras |

### Distribución de tokens

El context window se comparte entre:
- **Prompt tokens** (tu entrada)
- **Completion tokens** (respuesta del modelo)

**Ejemplo:**
```
Context window: 4,096 tokens
Prompt: 500 tokens
Max respuesta disponible: 3,596 tokens
```

### ¿Qué pasa si excedes el límite?

El modelo:
1. Trunca (corta) el texto que excede
2. Retorna un error indicando límite excedido
3. En conversaciones largas, olvida mensajes antiguos

**Estrategias si excedes:**
- Resumir información previa
- Dividir el contenido en múltiples solicitudes
- Usar un modelo con mayor context window
- Implementar técnicas de chunking (dividir documentos)

---

## 3. Prompt Engineering Fundamentals

### ¿Qué es Prompt Engineering?

El **prompt engineering** es el arte y ciencia de diseñar instrucciones efectivas para obtener los mejores resultados de un modelo de IA.

### Anatomía de un buen prompt

**Componentes principales:**

1. **Instrucción** (obligatorio): Qué quieres que haga
2. **Contexto** (opcional): Información de fondo
3. **Datos de entrada** (opcional): Información específica a procesar
4. **Formato de salida** (opcional): Cómo quieres la respuesta

**Ejemplo estructurado:**
```
[INSTRUCCIÓN]
Actúa como un experto en marketing digital.

[CONTEXTO]
Nuestra empresa vende software de gestión de proyectos para equipos remotos.

[DATOS DE ENTRADA]
Producto: TaskFlow Pro
Precio: $29/mes
Características principales: Colaboración en tiempo real, reportes automáticos, integraciones

[FORMATO DE SALIDA]
Genera 3 tweets promocionales, cada uno de máximo 280 caracteres.
```

---

## 4. Técnicas de Prompt Engineering

### 1. Zero-Shot Prompting

**Descripción**: Dar la instrucción directamente sin ejemplos.

**Cuándo usar**: Tareas simples y directas.

**Ejemplo:**
```
Prompt: "Clasifica el siguiente texto como positivo, negativo o neutral: 
'El servicio al cliente fue excelente y respondieron rápidamente.'"

Respuesta: "Positivo"
```

### 2. Few-Shot Prompting (Con ejemplos)

**Descripción**: Proporcionar ejemplos antes de la tarea real.

**Cuándo usar**: Tareas específicas o formatos particulares.

**Ejemplo:**
```
Prompt: 
"Clasifica los sentimientos de los siguientes textos:

Texto: 'Me encanta este producto'
Sentimiento: Positivo

Texto: 'Terrible experiencia, nunca volveré'
Sentimiento: Negativo

Texto: 'El paquete llegó en la fecha estimada'
Sentimiento: Neutral

Texto: 'El servicio superó mis expectativas'
Sentimiento:"

Respuesta: "Positivo"
```

### 3. Chain-of-Thought (Cadena de Pensamiento)

**Descripción**: Pedir al modelo que explique su razonamiento paso a paso.

**Cuándo usar**: Problemas complejos, matemáticas, lógica.

**Ejemplo:**
```
Prompt: 
"Un tren viaja 120 km en 2 horas. ¿Cuánto tiempo tardará en recorrer 300 km a la misma velocidad?

Piensa paso a paso:"

Respuesta esperada:
"Paso 1: Calcular la velocidad del tren
Velocidad = 120 km / 2 horas = 60 km/h

Paso 2: Calcular el tiempo para 300 km
Tiempo = 300 km / 60 km/h = 5 horas

Respuesta: 5 horas"
```

### 4. Role Prompting (Asignación de Rol)

**Descripción**: Asignar un rol o personalidad específica al modelo.

**Cuándo usar**: Para respuestas con expertise o tono específico.

**Ejemplo:**
```
Prompt: 
"Actúa como un pediatra con 20 años de experiencia. 
Explica de manera comprensible para padres primerizos qué es la fiebre y cuándo deben preocuparse."
```

### 5. Instruction Following (Seguimiento de Instrucciones)

**Descripción**: Dar instrucciones claras, específicas y numeradas.

**Cuándo usar**: Tareas multi-paso o con requisitos específicos.

**Ejemplo:**
```
Prompt:
"Analiza el siguiente email y realiza estas tareas:
1. Identifica el remitente y el asunto
2. Resume el contenido en máximo 2 oraciones
3. Clasifica la urgencia como: Alta, Media o Baja
4. Sugiere una acción de seguimiento

[Email aquí]"
```

### 6. Constrained Output (Salida Restringida)

**Descripción**: Limitar el formato o contenido de la respuesta.

**Cuándo usar**: Cuando necesitas formato específico (JSON, tabla, lista).

**Ejemplo:**
```
Prompt:
"Extrae la siguiente información del texto y devuélvela SOLO en formato JSON:
- nombre
- edad
- ciudad

Texto: 'Juan Pérez tiene 32 años y vive en Madrid.'

Responde ÚNICAMENTE con el JSON, sin texto adicional."

Respuesta esperada:
{
  "nombre": "Juan Pérez",
  "edad": 32,
  "ciudad": "Madrid"
}
```

---

## 5. Mejores Prácticas de Prompt Engineering

### ✅ DO (Hacer)

**1. Ser específico y claro**
```
❌ Malo: "Háblame de Azure"
✅ Bueno: "Explica en 3 párrafos qué es Azure OpenAI Service y sus principales beneficios para empresas"
```

**2. Usar delimitadores para separar secciones**
```
Usa """ para el texto a analizar:
"""
[Texto aquí]
"""

Usa ### para instrucciones especiales:
###
Responde en español formal
###
```

**3. Especificar el formato de salida**
```
✅ "Responde en formato de lista numerada"
✅ "Genera una tabla con columnas: Nombre, Precio, Características"
✅ "Devuelve solo JSON válido, sin explicaciones adicionales"
```

**4. Dar ejemplos (few-shot)**
```
✅ Proporciona 2-3 ejemplos del formato deseado
✅ Muestra el patrón que quieres que siga
```

**5. Dividir tareas complejas**
```
✅ En lugar de: "Analiza, resume, traduce y formatea este documento"
✅ Mejor: Hacer en pasos separados:
   1. Primero analizar
   2. Luego resumir
   3. Después traducir
   4. Finalmente formatear
```

**6. Usar "Piensa paso a paso" para razonamiento**
```
✅ "Resuelve este problema matemático. Piensa paso a paso y muestra tu razonamiento."
```

### ❌ DON'T (Evitar)

**1. Ser vago o ambiguo**
```
❌ "Dame información"
❌ "Ayúdame con esto"
❌ "¿Qué opinas?"
```

**2. Asumir conocimiento de contexto**
```
❌ "Continúa con lo anterior" (sin proporcionar contexto)
❌ "Como mencioné antes..." (en nueva conversación)
```

**3. Instrucciones contradictorias**
```
❌ "Sé breve pero proporciona todos los detalles posibles"
❌ "Usa lenguaje técnico pero explícalo para principiantes"
```

**4. Prompts excesivamente largos sin estructura**
```
❌ Un párrafo gigante de 500 palabras sin organización
✅ Usar secciones claras con encabezados
```

---

## 6. Optimización de Tokens

### Estrategias para reducir uso de tokens

#### 1. Ser conciso en instrucciones
```
❌ (15 tokens): "Me gustaría que por favor me ayudaras a generar un resumen de este texto"
✅ (7 tokens): "Resume este texto:"
```

#### 2. Evitar repeticiones
```
❌ Repetir el mismo contexto en cada mensaje de la conversación
✅ Proporcionar contexto una vez, referenciar después
```

#### 3. Usar abreviaciones cuando sea apropiado
```
Original: "Microsoft Azure OpenAI Service" (6 tokens)
Abreviado: "Azure OpenAI" (3 tokens)
```

#### 4. Limitar max_tokens en la respuesta
```python
{
  "max_tokens": 150,  # Limita la longitud de respuesta
  "temperature": 0.7
}
```

#### 5. Resumir conversaciones largas
```
En lugar de mantener 50 mensajes en el historial:
✅ Resumir mensajes antiguos cada 10-15 intercambios
✅ Mantener solo el resumen + últimos 5 mensajes
```

### Cálculo de costos basado en tokens

**Ejemplo con GPT-4:**
- Precio: $0.03 / 1K prompt tokens
- Precio: $0.06 / 1K completion tokens

**Escenario:**
```
Prompt: 500 tokens
Respuesta: 300 tokens

Costo:
- Prompt: (500/1000) × $0.03 = $0.015
- Completion: (300/1000) × $0.06 = $0.018
- Total: $0.033 por llamada

Con 1,000 llamadas/día:
$0.033 × 1,000 = $33/día = ~$1,000/mes
```

**Optimización:**
```
Reducir prompt a 300 tokens (-40%)
Limitar respuesta a 200 tokens (-33%)

Nuevo costo:
- Prompt: (300/1000) × $0.03 = $0.009
- Completion: (200/1000) × $0.06 = $0.012
- Total: $0.021 por llamada

Con 1,000 llamadas/día:
$0.021 × 1,000 = $21/día = ~$630/mes

Ahorro: $370/mes (37%)
```

---

## 7. Casos de Uso Prácticos

### Caso 1: Extracción de Información

**Objetivo**: Extraer datos estructurados de texto libre.

**Prompt optimizado:**
```
Extrae la siguiente información del email y devuelve solo JSON:
- remitente
- fecha
- asunto
- prioridad (Alta/Media/Baja)

Email:
"""
De: maria.lopez@empresa.com
Fecha: 2025-12-03
Asunto: URGENTE - Sistema caído

El servidor principal no responde desde las 09:00 AM.
"""

JSON:
```

**Tokens aproximados**: 60 tokens (prompt) + 30 tokens (respuesta) = 90 tokens

---

### Caso 2: Clasificación de Sentimientos

**Objetivo**: Clasificar reviews de productos.

**Prompt optimizado:**
```
Clasifica estos reviews (Positivo/Negativo/Neutral):

1. "Excelente producto, superó expectativas" →
2. "No funciona como esperaba" →
3. "Entrega puntual, producto correcto" →
```

**Tokens aproximados**: 35 tokens (prompt) + 10 tokens (respuesta) = 45 tokens

---

### Caso 3: Generación de Código

**Objetivo**: Crear función Python específica.

**Prompt optimizado:**
```
Crea una función Python que:
1. Reciba una lista de números
2. Retorne la mediana
3. Maneje lista vacía

Solo código, sin explicaciones.
```

**Tokens aproximados**: 30 tokens (prompt) + 80 tokens (respuesta) = 110 tokens

---

### Caso 4: Resumen de Documentos

**Objetivo**: Resumir documento largo.

**Prompt optimizado:**
```
Resume en 3 puntos clave:
"""
[Documento aquí - 2000 tokens]
"""

Formato:
1. [Punto clave 1]
2. [Punto clave 2]
3. [Punto clave 3]
```

**Tokens aproximados**: 2,050 tokens (prompt) + 50 tokens (respuesta) = 2,100 tokens

---

## 8. Técnicas Avanzadas

### System Message vs User Message

**System Message**: Define comportamiento global
```json
{
  "role": "system",
  "content": "Eres un asistente de programación experto en Python. Siempre proporcionas código limpio y comentado."
}
```

**User Message**: La solicitud específica
```json
{
  "role": "user",
  "content": "Crea una función para calcular factorial"
}
```

**Ventaja**: El system message se procesa una vez, ahorrando tokens en conversaciones largas.

---

### Prompt Chaining (Encadenamiento)

**Concepto**: Dividir tarea compleja en pasos secuenciales.

**Ejemplo:**
```
Paso 1: "Extrae los nombres de todos los clientes mencionados"
Paso 2: "Para cada cliente, identifica sus compras"
Paso 3: "Calcula el total gastado por cada cliente"
Paso 4: "Genera reporte en formato tabla"
```

**Beneficios:**
- Más preciso que un prompt gigante
- Permite verificar cada paso
- Reduce uso de tokens al enfocarse en una tarea a la vez

---

### Retrieval-Augmented Generation (RAG)

**Concepto**: Combinar búsqueda de información con generación.

**Flujo:**
```
1. Usuario hace pregunta
2. Buscar información relevante en base de datos (embeddings)
3. Incluir solo información relevante en el prompt
4. Generar respuesta basada en esa información

Beneficio: Reduce tokens al incluir solo lo necesario
```

---

## ✅ Puntos Clave para el Examen

- **Tokens** son unidades básicas de procesamiento (~4 caracteres en inglés, ~3-4 en español)
- **Context window** es el límite máximo de tokens (prompt + respuesta)
- GPT-5 tiene el context window más grande (256K-400K tokens)
- **Prompt engineering** es diseñar instrucciones efectivas para mejores resultados
- Técnicas principales: Zero-shot, Few-shot, Chain-of-Thought, Role Prompting
- **System message** define comportamiento global del asistente
- **Few-shot prompting** proporciona ejemplos para mejorar resultados
- **Delimitadores** (""", ###, ---) ayudan a estructurar prompts
- Optimizar tokens reduce costos: ser conciso, evitar repeticiones, limitar max_tokens
- **Chain-of-Thought** mejora razonamiento en problemas complejos
- Especificar formato de salida (JSON, tabla, lista) para respuestas estructuradas
- Los costos se calculan por: (prompt tokens + completion tokens) × precio por token

---

## 🎯 Preguntas Estilo Examen Microsoft AI-900

### Pregunta 1
Estás usando GPT-4 con un context window de 8,192 tokens. Tu prompt usa 7,000 tokens. ¿Cuántos tokens tiene disponibles el modelo para la respuesta?

- [ ] A) 8,192 tokens  
- [ ] B) 7,000 tokens  
- [-] C) 1,192 tokens  
- [ ] D) 15,192 tokens

**Respuesta correcta: C) 1,192 tokens**

**Explicación**: El **context window** se comparte entre el prompt y la respuesta. Si el context window es 8,192 tokens y el prompt usa 7,000 tokens, quedan 8,192 - 7,000 = 1,192 tokens disponibles para la respuesta del modelo. No se suman (D es incorrecto), y las opciones A y B no consideran la resta necesaria.

---

### Pregunta 2
¿Cuál de las siguientes técnicas de prompt engineering proporciona ejemplos al modelo antes de hacer la solicitud real?

- [ ] A) Zero-shot prompting  
- [-] B) Few-shot prompting  
- [ ] C) Chain-of-thought  
- [ ] D) Role prompting

**Respuesta correcta: B) Few-shot prompting**

**Explicación**: **Few-shot prompting** consiste en proporcionar algunos ejemplos (típicamente 2-5) antes de la tarea real para que el modelo entienda el patrón deseado. Zero-shot (A) no usa ejemplos, Chain-of-thought (C) enfoca en razonamiento paso a paso, y Role prompting (D) asigna un rol o personalidad.

---

### Pregunta 3
Necesitas que el modelo explique su razonamiento paso a paso para resolver un problema matemático complejo. ¿Qué técnica deberías usar?

- [ ] A) Few-shot prompting  
- [ ] B) Zero-shot prompting  
- [-] C) Chain-of-thought prompting  
- [ ] D) Constrained output

**Respuesta correcta: C) Chain-of-thought prompting**

**Explicación**: **Chain-of-thought (cadena de pensamiento)** es específicamente para obtener razonamiento paso a paso, ideal para matemáticas, lógica y problemas complejos. Típicamente se activa con frases como "piensa paso a paso" o "explica tu razonamiento". Few-shot (A) usa ejemplos, Zero-shot (B) es directo, y Constrained output (D) limita el formato de salida.

---

### Pregunta 4
¿Qué rol de mensaje debes usar para definir el comportamiento general y la personalidad del asistente en una conversación?

- [ ] A) user  
- [ ] B) assistant  
- [-] C) system  
- [ ] D) function

**Respuesta correcta: C) system**

**Explicación**: El mensaje con rol **system** define el comportamiento global, personalidad y reglas que el asistente debe seguir durante toda la conversación (ej: "Eres un experto en medicina"). El rol **user** es para mensajes del usuario, **assistant** para respuestas previas del modelo, y **function** para llamadas a funciones externas.

---

### Pregunta 5
Aproximadamente, ¿cuántos caracteres equivalen a un token en inglés?

- [ ] A) 1 carácter  
- [-] B) 4 caracteres  
- [ ] C) 10 caracteres  
- [ ] D) 20 caracteres

**Respuesta correcta: B) 4 caracteres**

**Explicación**: En inglés, la regla general es que **1 token ≈ 4 caracteres** o aproximadamente 0.75 palabras. Esta es una estimación útil para calcular tokens. En español y otros idiomas puede ser ligeramente diferente (3-4 caracteres por token) debido a acentos y estructura del idioma.

---

## 📖 Recursos Adicionales

- [OpenAI Tokenizer](https://platform.openai.com/tokenizer)
- [Prompt Engineering Guide](https://www.promptingguide.ai/)
- [Azure OpenAI Best Practices](https://learn.microsoft.com/azure/cognitive-services/openai/how-to/best-practices)
- [OpenAI Prompt Engineering Documentation](https://platform.openai.com/docs/guides/prompt-engineering)
