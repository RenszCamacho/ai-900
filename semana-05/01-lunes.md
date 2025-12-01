# AI-900 Certification - Semana 5, Día 1

## Introducción a la IA Generativa (Generative AI)

**Fecha:** Lunes, Semana 5  
**Duración estimada:** 45-60 minutos  
**Nivel:** Fundamental

---

## 📋 Objetivos del día

- Comprender qué es la IA Generativa y cómo funciona
- Conocer los tipos de modelos generativos
- Entender las diferencias entre IA tradicional vs IA Generativa
- Identificar casos de uso comunes de IA Generativa
- Conocer los conceptos fundamentales de Large Language Models (LLMs)

---

## 1. ¿Qué es la IA Generativa?

### Definición

La **IA Generativa** es un tipo de inteligencia artificial que puede crear contenido nuevo y original, incluyendo:
- Texto (artículos, código, emails)
- Imágenes (arte, fotografías, diseños)
- Audio (música, voz, efectos de sonido)
- Video (animaciones, clips)
- Código (programas, scripts)

### ¿Cómo funciona?

Los modelos generativos aprenden patrones de grandes cantidades de datos de entrenamiento y luego pueden generar contenido similar pero nuevo.

**Proceso básico:**
1. **Entrenamiento**: El modelo analiza millones de ejemplos
2. **Aprendizaje de patrones**: Identifica estructuras, estilos, relaciones
3. **Generación**: Crea contenido nuevo basado en esos patrones
4. **Refinamiento**: Ajusta la salida según instrucciones (prompts)

---

## 2. IA Tradicional vs IA Generativa

### IA Tradicional (Predictiva/Analítica)

**Propósito**: Analizar, clasificar, predecir

**Ejemplos:**
- Clasificación de emails (spam vs no spam)
- Predicción de ventas
- Detección de fraude
- Reconocimiento de objetos en imágenes

**Salida**: Etiquetas, categorías, números, predicciones

**Ejemplo práctico:**
```
Input: Imagen de un gato
Output: "Gato" (clasificación)
```

### IA Generativa

**Propósito**: Crear, generar, sintetizar

**Ejemplos:**
- Generar artículos o historias
- Crear imágenes a partir de descripciones
- Escribir código
- Componer música

**Salida**: Contenido nuevo y original

**Ejemplo práctico:**
```
Input: "Escribe un poema sobre el océano"
Output: Un poema completo y único sobre el océano
```

### Comparación visual

| Aspecto | IA Tradicional | IA Generativa |
|---------|----------------|---------------|
| **Función principal** | Analizar y predecir | Crear y generar |
| **Entrada** | Datos para clasificar | Prompts/Instrucciones |
| **Salida** | Etiquetas, números | Contenido nuevo |
| **Ejemplo** | "Esta imagen es un perro" | "Crea una imagen de un perro" |
| **Modelos típicos** | Random Forest, SVM | GPT, DALL-E, Stable Diffusion |

---

## 3. Tipos de Modelos Generativos

### 1. Large Language Models (LLMs)

**Descripción**: Modelos entrenados en enormes cantidades de texto

**Ejemplos:**
- **GPT (Generative Pre-trained Transformer)**: GPT-3.5, GPT-4
- **BERT**: Bidirectional Encoder Representations
- **LLaMA**: Meta's Large Language Model

**Capacidades:**
- Generación de texto coherente
- Traducción de idiomas
- Resumen de documentos
- Respuesta a preguntas
- Generación de código

**Caso de uso:**
```
Prompt: "Explica la fotosíntesis para un niño de 8 años"
Output: Respuesta adaptada al nivel apropiado
```

### 2. Modelos de Generación de Imágenes

**Descripción**: Crean imágenes a partir de descripciones de texto

**Ejemplos:**
- **DALL-E**: OpenAI
- **Stable Diffusion**: Stability AI
- **Midjourney**: Midjourney Inc.

**Capacidades:**
- Generación de arte digital
- Modificación de imágenes existentes
- Creación de variaciones
- Inpainting (rellenar partes faltantes)

**Caso de uso:**
```
Prompt: "Un astronauta montando un caballo en Marte, estilo acuarela"
Output: Imagen generada según descripción
```

### 3. Modelos Multimodales

**Descripción**: Trabajan con múltiples tipos de datos (texto, imagen, audio)

**Ejemplos:**
- **GPT-4 Vision**: Texto + Imágenes
- **CLIP**: Relaciona imágenes y texto
- **Flamingo**: Múltiples modalidades

**Capacidades:**
- Describir imágenes
- Generar imágenes desde texto
- Responder preguntas sobre imágenes
- Análisis de contenido multimedia

---

## 4. Conceptos Fundamentales de LLMs

### Tokens

**¿Qué son?**
Los tokens son las unidades básicas de procesamiento de texto en LLMs.

**Ejemplos de tokenización:**
```
"Hola mundo" → ["Hola", " mundo"] = 2 tokens
"OpenAI" → ["Open", "AI"] = 2 tokens
"¡Fantástico!" → ["¡", "Fant", "ástico", "!"] = 4 tokens
```

**Regla general**: 
- En inglés: ~1 token = 4 caracteres = 0.75 palabras
- En español: ~1 token = 3-4 caracteres

**Importancia**: 
- Los modelos tienen límites de tokens (ej: GPT-4 = 8k, 32k, 128k tokens)
- El costo de uso se calcula por tokens

### Context Window (Ventana de Contexto)

**Definición**: Cantidad máxima de tokens que un modelo puede procesar a la vez

**Ejemplos:**
- GPT-3.5: 4,096 tokens (~3,000 palabras)
- GPT-4: 8,192 - 128,000 tokens
- Claude 2: 100,000 tokens

**Implicación práctica:**
Si un documento tiene más tokens que la ventana de contexto, el modelo no puede procesarlo completo en una sola solicitud.

### Temperatura

**Definición**: Parámetro que controla la aleatoriedad/creatividad de las respuestas

**Escala**: 0.0 - 2.0

**Comportamiento:**
- **Temperatura baja (0.0 - 0.3)**: 
  - Respuestas más predecibles y deterministas
  - Útil para: Tareas técnicas, clasificación, extracción de datos
  
- **Temperatura media (0.5 - 0.8)**:
  - Balance entre creatividad y coherencia
  - Útil para: Conversación general, escritura
  
- **Temperatura alta (1.0 - 2.0)**:
  - Respuestas muy creativas y variadas
  - Útil para: Brainstorming, contenido creativo, arte

**Ejemplo:**
```
Prompt: "Termina la frase: El cielo es..."

Temperatura 0.0: "azul" (siempre la misma)
Temperatura 0.7: "azul", "hermoso", "infinito" (variado pero sensato)
Temperatura 1.5: "un lienzo de sueños", "esperanza líquida" (muy creativo)
```

### Embeddings

**Definición**: Representaciones numéricas (vectores) de texto que capturan significado semántico

**Características:**
- Palabras similares tienen embeddings similares
- Permiten buscar por significado, no solo por palabras exactas
- Útiles para: búsqueda semántica, recomendaciones, clustering

**Ejemplo conceptual:**
```
"perro" → [0.2, 0.8, 0.1, 0.9, ...]
"gato"  → [0.3, 0.7, 0.2, 0.8, ...] (similar)
"carro" → [0.8, 0.1, 0.9, 0.2, ...] (diferente)
```

---

## 5. Casos de Uso Comunes

### Generación de Contenido
- Artículos de blog
- Descripciones de productos
- Posts para redes sociales
- Guiones de video

### Asistencia al Cliente
- Chatbots inteligentes
- Respuestas automáticas a emails
- FAQs dinámicas
- Soporte multilingüe

### Desarrollo de Software
- Generación de código
- Documentación automática
- Debugging y explicación de código
- Refactorización

### Creación de Contenido Visual
- Prototipos de diseño
- Arte generativo
- Edición de imágenes
- Creación de avatares

### Educación
- Tutores virtuales personalizados
- Generación de ejercicios
- Explicaciones adaptadas al nivel
- Traducción de materiales educativos

### Análisis y Resumen
- Resumen de documentos largos
- Extracción de información clave
- Análisis de sentimientos
- Síntesis de reuniones

---

## 6. Limitaciones de la IA Generativa

### Alucinaciones (Hallucinations)

**Problema**: Los modelos pueden generar información falsa pero convincente

**Ejemplo:**
```
Pregunta: "¿Quién ganó el Premio Nobel de Literatura en 2025?"
Respuesta incorrecta: "María García lo ganó por su novela 'El Tiempo Perdido'"
(Inventa nombres y datos que suenan plausibles)
```

**Mitigación:**
- Verificar información crítica
- Usar grounding (anclar a datos reales)
- Pedir fuentes y referencias

### Sesgos

**Problema**: Los modelos reflejan sesgos presentes en datos de entrenamiento

**Ejemplos:**
- Sesgos de género en profesiones
- Sesgos culturales o raciales
- Representación desigual de idiomas

**Mitigación:**
- Datos de entrenamiento diversos
- Fine-tuning responsable
- Revisión humana

### Falta de Razonamiento Verdadero

**Problema**: Los modelos reconocen patrones, no "entienden" realmente

**Limitaciones:**
- No tienen conocimiento del mundo real actualizado
- No pueden razonar causalmente de forma confiable
- No tienen sentido común verdadero

### Costos y Recursos

**Consideraciones:**
- Entrenamiento requiere recursos computacionales masivos
- Inferencia (uso) también consume recursos significativos
- Costos por token en APIs comerciales

---

## ✅ Puntos Clave para el Examen

- IA Generativa **crea contenido nuevo**, IA tradicional **analiza y predice**
- **LLMs** (Large Language Models) son modelos entrenados en texto masivo
- **Tokens** son unidades básicas de procesamiento (~4 caracteres en inglés)
- **Context Window** es el límite de tokens que un modelo puede procesar
- **Temperatura** controla creatividad (baja = predecible, alta = creativo)
- **Embeddings** son representaciones vectoriales que capturan significado
- **Alucinaciones** = información falsa pero convincente generada por el modelo
- Casos de uso: generación de contenido, chatbots, código, imágenes, resúmenes
- Limitaciones: alucinaciones, sesgos, falta de razonamiento real, costos

---

## 🎯 Preguntas Estilo Examen Microsoft AI-900

### Pregunta 1
¿Cuál de las siguientes afirmaciones describe MEJOR la diferencia entre IA tradicional e IA generativa?

A) La IA tradicional es más rápida que la IA generativa  
B) La IA tradicional analiza y predice, mientras que la IA generativa crea contenido nuevo  
C) La IA generativa solo funciona con texto  
D) La IA tradicional requiere más datos de entrenamiento

**Respuesta correcta: B) La IA tradicional analiza y predice, mientras que la IA generativa crea contenido nuevo**

**Explicación**: La diferencia fundamental es el propósito: la IA tradicional (clasificación, regresión) analiza datos existentes para hacer predicciones o clasificaciones. La IA generativa crea contenido nuevo (texto, imágenes, código) basándose en patrones aprendidos. Las opciones A, C y D no representan las diferencias fundamentales entre ambos tipos de IA.

---

### Pregunta 2
Estás configurando un modelo de lenguaje para generar respuestas de servicio al cliente. Necesitas que las respuestas sean consistentes y predecibles. ¿Qué valor de temperatura deberías usar?

A) 2.0  
B) 1.5  
C) 0.8  
D) 0.2

**Respuesta correcta: D) 0.2**

**Explicación**: Para respuestas consistentes y predecibles, necesitas una temperatura **baja** (cercana a 0). Valores bajos como 0.2 hacen que el modelo seleccione las opciones más probables, resultando en respuestas deterministas y confiables. Temperaturas altas (1.5, 2.0) generan respuestas más creativas pero menos predecibles, inapropiado para servicio al cliente donde la consistencia es clave.

---

### Pregunta 3
Un modelo de lenguaje genera la siguiente respuesta: "El Monte Everest está ubicado en Japón y tiene una altura de 12,000 metros." ¿Qué problema está demostrando este modelo?

A) Baja temperatura  
B) Alucinaciones (Hallucinations)  
C) Falta de tokens  
D) Contexto insuficiente

**Respuesta correcta: B) Alucinaciones (Hallucinations)**

**Explicación**: Las **alucinaciones** ocurren cuando un modelo genera información falsa pero convincente. El Everest está en Nepal/Tibet (no Japón) y mide ~8,849 metros (no 12,000). El modelo está inventando "hechos" plausibles pero incorrectos. Esto es diferente de problemas de temperatura (controla creatividad), falta de tokens (límite de procesamiento), o contexto insuficiente (información de entrada limitada).

---

### Pregunta 4
¿Qué son los "tokens" en el contexto de Large Language Models?

A) Medidas de la calidad del modelo  
B) Unidades básicas de procesamiento de texto  
C) Nombres de los modelos de IA  
D) Parámetros de configuración del modelo

**Respuesta correcta: B) Unidades básicas de procesamiento de texto**

**Explicación**: Los **tokens** son las unidades fundamentales en las que los LLMs dividen el texto para procesarlo. Una palabra puede ser uno o varios tokens dependiendo de su longitud y composición. Por ejemplo, "Hola" = 1 token, "Fantástico" = 2-3 tokens. Los tokens determinan los límites de procesamiento del modelo (context window) y los costos de uso. No son medidas de calidad, nombres de modelos, ni parámetros de configuración.

---

### Pregunta 5
Una empresa quiere usar IA generativa para crear descripciones únicas de productos basadas en especificaciones técnicas. ¿Cuál de los siguientes es un caso de uso apropiado para IA generativa?

A) Clasificar productos en categorías existentes  
B) Predecir la demanda futura de productos  
C) Generar textos descriptivos creativos y únicos para cada producto  
D) Analizar sentimientos de reviews de clientes

**Respuesta correcta: C) Generar textos descriptivos creativos y únicos para cada producto**

**Explicación**: La IA generativa es ideal para **crear contenido nuevo y original**, como descripciones de productos. Las otras opciones son tareas de IA tradicional: clasificación (A), predicción (B), y análisis de sentimientos (D) son tareas de IA predictiva/analítica que no requieren generar contenido nuevo, solo analizar y categorizar datos existentes.

---

## 📚 Tarea para mañana

Mañana profundizaremos en **Azure OpenAI Service**: deployment de modelos, APIs, Studio, y casos de uso prácticos.

---

## 📖 Recursos Adicionales

- [Microsoft Learn - AI-900 Learning Path](https://docs.microsoft.com/learn/certifications/exams/ai-900)
- [Azure AI Services Documentation](https://docs.microsoft.com/azure/cognitive-services/)
- [Responsible AI Resources](https://www.microsoft.com/ai/responsible-ai)
- [Transparency Notes](https://docs.microsoft.com/azure/cognitive-services/transparency-note)

---

**Semana:** 5 de 6  
**Próximo tema:** Azure OpenAI Service
