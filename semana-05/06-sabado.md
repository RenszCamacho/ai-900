# AI-900 Certification - Semana 5, Día 6

## Mega Repaso General 🎯

**Fecha:** Sábado, Semana 5  
**Duración estimada:** 2-3 horas  
**Nivel:** Repaso completo

---

## 📋 Objetivo del día

Consolidar **TODO** el conocimiento de las 5 semanas de estudio:

- Semana 1: Fundamentos de IA
- Semana 2: Machine Learning
- Semana 3: Computer Vision
- Semana 4: Natural Language Processing
- Semana 5: Generative AI + Responsible AI

---

## 🗂️ Índice de Repaso

1. [Fundamentos de IA](#1-fundamentos-de-ia)
2. [Machine Learning](#2-machine-learning)
3. [Azure Machine Learning](#3-azure-machine-learning)
4. [Computer Vision](#4-computer-vision)
5. [Natural Language Processing](#5-natural-language-processing)
6. [Generative AI](#6-generative-ai)
7. [Azure OpenAI Service](#7-azure-openai-service)
8. [Responsible AI](#8-responsible-ai)
9. [Content Filters](#9-content-filters)
10. [Conceptos Transversales](#10-conceptos-transversales)

---

## 1. Fundamentos de IA

### ¿Qué es Inteligencia Artificial?

**Definición:** Sistemas que simulan inteligencia humana para realizar tareas que normalmente requieren cognición humana.

### Tipos de IA

| Tipo                     | Descripción                  | Ejemplo               |
| ------------------------ | ---------------------------- | --------------------- |
| **IA Débil (Narrow AI)** | Específica para una tarea    | Reconocimiento facial |
| **IA General (AGI)**     | Inteligencia humana completa | No existe aún         |
| **IA Super**             | Supera inteligencia humana   | Ciencia ficción       |

### Categorías de workloads de IA

**1. Machine Learning (ML)**

- Aprender de datos sin programación explícita
- Tipos: Supervisado, No supervisado, Refuerzo

**2. Computer Vision**

- Análisis e interpretación de imágenes/video
- Ejemplos: Detección de objetos, OCR, análisis facial

**3. Natural Language Processing (NLP)**

- Procesamiento y comprensión de lenguaje humano
- Ejemplos: Traducción, análisis de sentimiento, chatbots

**4. Generative AI**

- Creación de contenido nuevo
- Ejemplos: GPT (texto), DALL-E (imágenes)

---

## 2. Machine Learning

### Tipos de Machine Learning

#### Supervised Learning (Aprendizaje Supervisado)

**Características:**

- Datos etiquetados (labels)
- Aprende de ejemplos conocidos
- Objetivo: predecir labels de datos nuevos

**Tipos principales:**

**Regresión:**

- Predice valores numéricos continuos
- Ejemplo: Predecir precio de casa ($250,000)
- Algoritmos: Linear Regression, Decision Trees

**Clasificación:**

- Predice categorías/clases
- **Binaria**: 2 clases (spam/no spam)
- **Multiclase**: 3+ clases (perro/gato/pájaro)
- Algoritmos: Logistic Regression, Random Forest, SVM

#### Unsupervised Learning (Aprendizaje No Supervisado)

**Características:**

- Datos NO etiquetados
- Encuentra patrones ocultos
- No hay "respuesta correcta"

**Tipos:**

**Clustering:**

- Agrupa datos similares
- Ejemplo: Segmentación de clientes
- Algoritmo: K-Means

#### Reinforcement Learning (Aprendizaje por Refuerzo)

**Características:**

- Agente aprende mediante prueba y error
- Recibe recompensas/penalizaciones
- Ejemplo: AlphaGo, vehículos autónomos

### Métricas de Evaluación

#### Para Regresión:

**MAE (Mean Absolute Error):**

- Promedio de errores absolutos
- Fórmula: `MAE = (1/n) Σ|actual - predicted|`
- Menor es mejor

**MSE (Mean Squared Error):**

- Penaliza errores grandes más fuertemente
- Fórmula: `MSE = (1/n) Σ(actual - predicted)²`

**R² (R-squared):**

- Qué tan bien el modelo explica la varianza
- Rango: 0 a 1 (1 = perfecto)

#### Para Clasificación:

**Accuracy (Precisión):**

- % predicciones correctas
- Fórmula: `(TP + TN) / Total`
- Problema: Misleading con datos desbalanceados

**Precision:**

- De las predicciones positivas, cuántas son correctas
- Fórmula: `TP / (TP + FP)`
- Importante cuando FP es costoso

**Recall (Sensibilidad):**

- De los positivos reales, cuántos detectamos
- Fórmula: `TP / (TP + FN)`
- Importante cuando FN es costoso

**F1-Score:**

- Media armónica de Precision y Recall
- Fórmula: `2 × (Precision × Recall) / (Precision + Recall)`
- Balance entre ambos

**Confusion Matrix:**

```
                Predicted
              Pos    Neg
Actual  Pos   TP     FN
        Neg   FP     TN
```

---

## 3. Azure Machine Learning

### Componentes Principales

**1. Workspace:**

- Recurso top-level en Azure
- Contiene todos los assets de ML
- Centraliza experimentos, modelos, datos

**2. Compute:**

- **Compute Instances**: VM para desarrollo/notebooks
- **Compute Clusters**: Clusters escalables para entrenamiento
- **Inference Clusters**: Para despliegue de modelos (AKS)

**3. Datasets:**

- Referencia a datos de entrenamiento
- Versionados y rastreables
- Pueden ser tabulares o archivos

**4. Experiments:**

- Agrupación de training runs
- Tracking de métricas y parámetros

**5. Models:**

- Modelo entrenado registrado
- Versionado
- Puede desplegarse como servicio web

**6. Pipelines:**

- Workflow de pasos ML
- Reproducible y reutilizable
- Ejemplo: Preparar datos → Entrenar → Evaluar

### Azure Machine Learning Studio

**Interfaz web** para:

- Crear y gestionar recursos
- Designer (ML visual, drag-and-drop)
- Automated ML (AutoML)
- Notebooks

### Automated Machine Learning (AutoML)

**¿Qué es?**

- Automatiza selección de algoritmo y hiperparámetros
- Prueba múltiples modelos automáticamente
- Selecciona el mejor basándose en métrica objetivo

**Tipos de tareas:**

- Classification
- Regression
- Time-series forecasting

**Pasos:**

1. Seleccionar dataset
2. Elegir tipo de tarea (classification/regression/forecasting)
3. Seleccionar métrica objetivo (accuracy, AUC, R², etc.)
4. Configurar constraints (tiempo, iteraciones)
5. Ejecutar
6. Revisar mejor modelo

**Beneficios:**

- No requiere expertise profundo en ML
- Experimenta con múltiples algoritmos
- Feature engineering automático
- Ahorra tiempo

---

## 4. Computer Vision

### Servicios de Azure AI Vision

#### 1. Image Analysis (Análisis de Imágenes)

**Capacidades:**

- **Tagging**: Identificar objetos, escenas, acciones
- **Object Detection**: Detectar y localizar objetos (bounding boxes)
- **Caption Generation**: Descripción en lenguaje natural
- **Dense Captions**: Múltiples descripciones para regiones
- **Read (OCR)**: Extraer texto impreso/manuscrito
- **Smart Cropping**: Recorte inteligente manteniendo contenido clave
- **Background Removal**: Eliminar fondo de imágenes

**Ejemplo de uso:**

```json
{
  "tags": ["outdoor", "building", "sky"],
  "objects": [
    {
      "object": "car",
      "confidence": 0.93,
      "rectangle": { "x": 100, "y": 150, "w": 200, "h": 150 }
    }
  ],
  "description": "A red car parked in front of a building"
}
```

#### 2. Face API

**Capacidades:**

- **Face Detection**: Detectar rostros en imágenes
- **Face Verification**: ¿Son la misma persona? (1:1)
- **Face Identification**: ¿Quién es? (1:N) - Requiere registro previo
- **Facial Attributes**: Edad, emoción, accesorios, etc.

**Nota de acceso limitado:**

- Microsoft requiere **solicitud de acceso** para Face API
- Solo para casos de uso aprobados
- Cumplimiento con Responsible AI

#### 3. Custom Vision

**¿Qué es?**

- Entrenar modelos personalizados de visión
- No requiere expertise en ML

**Tipos de proyectos:**

- **Classification**: Clasificar imagen completa
  - Multiclass: Una etiqueta por imagen
  - Multilabel: Múltiples etiquetas por imagen
- **Object Detection**: Detectar y localizar múltiples objetos

**Proceso:**

1. Crear proyecto en Custom Vision portal
2. Subir y etiquetar imágenes de entrenamiento (mínimo 15-50 por clase)
3. Entrenar modelo
4. Evaluar rendimiento (Precision, Recall, mAP)
5. Publicar como API
6. Consumir desde aplicaciones

**Métricas:**

- **Precision**: De detecciones, cuántas correctas
- **Recall**: De objetos reales, cuántos detectados
- **mAP (mean Average Precision)**: Métrica global para object detection

#### 4. Video Analysis

**Capacidades:**

- Indexación de video (caras, texto, objetos)
- Detección de escenas
- Moderación de contenido
- Transcripción de audio
- Traducción automática

---

## 5. Natural Language Processing

### Servicios de Azure AI Language

#### 1. Text Analytics

**Análisis de Sentimiento:**

- Positivo, Negativo, Neutral, Mixed
- Confidence scores por sentimiento
- Sentence-level sentiment

**Key Phrase Extraction:**

- Extraer frases clave de texto
- Identificar temas principales

**Named Entity Recognition (NER):**

- Identificar entidades: Personas, Lugares, Organizaciones, Fechas, etc.
- Linked entities (Wikipedia links)

**Language Detection:**

- Detectar idioma del texto
- Soporta 120+ idiomas

**Ejemplo de respuesta:**

```json
{
  "sentiment": "positive",
  "confidenceScores": {
    "positive": 0.89,
    "neutral": 0.08,
    "negative": 0.03
  },
  "keyPhrases": ["great service", "quick delivery"],
  "entities": [
    { "text": "Microsoft", "category": "Organization", "confidence": 0.95 }
  ]
}
```

#### 2. Question Answering

**¿Qué es?**

- Crear knowledge base de preguntas y respuestas
- Extraer Q&A de documentos (FAQs, manuales)
- Responder preguntas en lenguaje natural

**Proceso:**

1. Crear knowledge base en Language Studio
2. Importar FAQs o agregar manualmente Q&A pairs
3. Entrenar
4. Publicar
5. Integrar en chatbot

#### 3. Conversational Language Understanding (CLU)

**¿Qué es?**

- Entender intención del usuario (intent)
- Extraer información relevante (entities)

**Componentes:**

- **Intents**: Qué quiere hacer el usuario
  - Ejemplo: BookFlight, CancelReservation, GetWeather
- **Entities**: Información específica
  - Ejemplo: Ciudad, Fecha, Número de vuelo

**Ejemplo:**

```
Usuario: "Quiero volar a Madrid el próximo martes"

Intent: BookFlight (confidence: 0.92)
Entities:
  - Destination: Madrid
  - Date: próximo martes
```

#### 4. Translator

**Capacidades:**

- Traducción de texto (90+ idiomas)
- Traducción de documentos
- Detección automática de idioma fuente
- Transliteración (cambio de alfabeto)
- Custom translation (dominios específicos)

#### 5. Speech Services

**Speech-to-Text (STT):**

- Transcribir audio a texto
- Real-time o batch
- Custom speech (entrenar con vocabulario específico)

**Text-to-Speech (TTS):**

- Convertir texto a audio natural
- Múltiples voces y idiomas
- Neural TTS (más natural)
- SSML (Speech Synthesis Markup Language) para control

**Speech Translation:**

- Traducir audio en tiempo real
- Ejemplo: Español hablado → Inglés texto

---

## 6. Generative AI

### ¿Qué es IA Generativa?

**Definición:** IA que crea contenido nuevo y original (texto, imágenes, audio, video, código).

### Diferencias: IA Tradicional vs Generativa

| Aspecto     | IA Tradicional            | IA Generativa             |
| ----------- | ------------------------- | ------------------------- |
| **Función** | Analizar y predecir       | Crear y generar           |
| **Input**   | Datos para clasificar     | Prompts/Instrucciones     |
| **Output**  | Labels, números           | Contenido nuevo           |
| **Ejemplo** | "Esta imagen es un perro" | "Crea imagen de un perro" |

### Large Language Models (LLMs)

**Características:**

- Entrenados en cantidades masivas de texto
- Cientos de miles de millones de parámetros
- Capacidades emergentes (no programadas explícitamente)

**Ejemplos:**

- GPT-4, GPT-5 (OpenAI)
- Claude (Anthropic)
- Gemini (Google)
- LLaMA (Meta)

### Conceptos Fundamentales

#### Tokens

- Unidades básicas de procesamiento
- ~4 caracteres en inglés = 1 token
- ~3-4 caracteres en español = 1 token
- Los modelos tienen límites de tokens (context window)

#### Context Window

- Cantidad máxima de tokens que el modelo puede procesar
- Incluye prompt + respuesta
- Ejemplos:
  - GPT-3.5-turbo: 4K-16K tokens
  - GPT-4: 8K-128K tokens
  - GPT-5: 256K-400K tokens

#### Temperature

- Controla aleatoriedad/creatividad
- Rango: 0.0 - 2.0
- **Baja (0.0-0.3)**: Determinista, predecible
- **Media (0.5-0.8)**: Balance
- **Alta (1.0-2.0)**: Muy creativo, variado

#### Embeddings

- Representaciones vectoriales de texto
- Capturan significado semántico
- Usos: Búsqueda semántica, clustering, recomendaciones

### Limitaciones de IA Generativa

**Alucinaciones:**

- Generar información falsa pero convincente
- Mitigación: Grounding con datos reales, revisión humana

**Sesgos:**

- Reflejar sesgos de datos de entrenamiento
- Mitigación: Datos diversos, fine-tuning, evaluación continua

**Falta de razonamiento real:**

- Reconocen patrones, no "entienden" verdaderamente
- No tienen sentido común real

---

## 7. Azure OpenAI Service

### ¿Qué es?

Azure OpenAI Service proporciona acceso REST API a modelos avanzados de OpenAI con seguridad empresarial de Azure.

### Ventajas sobre OpenAI directo

✅ Seguridad empresarial de Azure  
✅ SLA 99.9%  
✅ Control de región (residencia de datos)  
✅ Integración con Azure AD / Microsoft Entra ID  
✅ Private endpoints  
✅ Datos NO se usan para reentrenar modelos  
✅ Cumplimiento: GDPR, HIPAA, ISO, SOC

### Modelos Disponibles

#### GPT-5 (Agosto 2025) - MÁS RECIENTE ⭐

**Variantes:**

- **gpt-5**: Modelo principal (requiere registro)
- **gpt-5-mini**: Ligero y económico
- **gpt-5-nano**: Optimizado para baja latencia
- **gpt-5-chat**: Conversaciones avanzadas multimodales

**Características:**

- Model Router inteligente (automático)
- 45% menos alucinaciones que GPT-4o
- Context window: 256K-400K tokens
- reasoning_effort parameter (low/medium/high)

#### GPT-4

**Versiones:**

- gpt-4 (8K)
- gpt-4-32k (32K)
- gpt-4-turbo (128K)
- gpt-4o (optimizado, multimodal)

#### GPT-3.5-Turbo

- Más rápido y económico
- Ideal para tareas simples
- 4K-16K context window

#### Otros Modelos

**Embeddings:**

- text-embedding-ada-002
- text-embedding-3-small/large

**DALL-E:**

- dall-e-2
- dall-e-3
- Generación de imágenes desde texto

**Whisper:**

- Transcripción de audio (speech-to-text)
- Múltiples idiomas

### Arquitectura

```
Azure Subscription
  └── Resource Group
      └── Azure OpenAI Resource
          ├── Endpoint
          ├── API Keys
          └── Deployments
              ├── gpt-5-mini-deployment
              ├── gpt-4-deployment
              └── embeddings-deployment
```

### Deployment

**¿Qué es un deployment?**

- Instancia específica de un modelo
- Tiene nombre único
- Configuración de capacidad (TPM - Tokens Per Minute)

**Ejemplo:**

```
Modelo: gpt-5-mini
Deployment name: "production-chatbot"
TPM: 20,000
Region: East US 2
```

### TPM (Tokens Per Minute)

- Define capacidad de procesamiento
- Ejemplo: 20K TPM = 20,000 tokens/minuto
- Si excedes: Error 429 (rate limiting)

### Azure OpenAI Studio

**Interfaz web para:**

- Crear/gestionar deployments
- Playground (probar modelos)
- Model Router configuration (GPT-5)
- Content filters
- Métricas y costos

### Estructura de llamada API

**Roles de mensajes:**

- **system**: Define comportamiento global
- **user**: Mensajes del usuario
- **assistant**: Respuestas previas (para contexto)

**Parámetros importantes:**

- **temperature**: Creatividad (0.0-2.0)
- **max_tokens**: Límite de respuesta
- **top_p**: Nucleus sampling (0.0-1.0)
- **reasoning_effort**: Solo GPT-5 (low/medium/high)

### Autenticación

**Opciones:**

1. **API Keys**: Fácil pero menos seguro
2. **Microsoft Entra ID (Azure AD)**: Recomendado
3. **Managed Identity**: Para servicios Azure-to-Azure

---

## 8. Responsible AI

### Los 6 Principios de Microsoft

#### 1️⃣ Fairness (Equidad)

- Tratar a todos de manera justa
- Sin discriminación por género, etnia, edad, etc.
- **Herramienta**: Fairlearn

**Ejemplo:**

- ❌ Sistema de contratación sesgado hacia hombres
- ✅ Evaluar rendimiento por grupos demográficos

#### 2️⃣ Reliability & Safety (Confiabilidad)

- Funcionar consistentemente
- Manejar errores apropiadamente
- Testing exhaustivo

**Ejemplo:**

- ✅ Vehículo autónomo con múltiples sensores redundantes
- ✅ Chatbot con fallback a humano si baja confianza

#### 3️⃣ Privacy & Security (Privacidad)

- Proteger datos personales
- Cumplir regulaciones (GDPR, HIPAA)
- Encriptación, control de acceso

**GDPR:**

- Derecho a ser olvidado
- Consentimiento explícito
- Notificación de brechas (72 horas)

**Ejemplo:**

- ✅ Encriptar datos médicos
- ✅ Managed Identity en lugar de API keys expuestas

#### 4️⃣ Inclusiveness (Inclusividad)

- Accesible para todos
- Personas con discapacidades
- Múltiples idiomas, culturas

**Ejemplo:**

- ✅ Compatible con lectores de pantalla
- ✅ Reconocimiento de voz con diferentes acentos
- ❌ App solo en inglés (excluye otros idiomas)

#### 5️⃣ Transparency (Transparencia)

- Usuarios entienden cómo funciona el sistema
- Divulgar cuando interactúan con IA
- Explicar limitaciones

**Transparency Notes:**

- Documentos de Microsoft por cada servicio
- Explican: capacidades, limitaciones, casos de uso

**Ejemplo:**

- ✅ "Soy un asistente de IA, no un humano"
- ✅ Explicar por qué un préstamo fue rechazado
- **Herramienta**: InterpretML

#### 6️⃣ Accountability (Responsabilidad)

- Supervisión humana
- Responsabilidad clara
- Human-in-the-loop para decisiones críticas

**Ejemplo:**

- ✅ Médico revisa diagnóstico de IA antes de tomar decisión
- ✅ Gerente de RRHH aprueba contrataciones, no solo IA

### Tipos de Sesgos

**1. Sesgo en datos de entrenamiento:**

- Datos históricos reflejan discriminación pasada
- Solución: Balancear dataset

**2. Sesgo de etiquetado:**

- Humanos etiquetan con sesgos inconscientes
- Solución: Múltiples etiquetadores, guidelines claros

**3. Sesgo de medición:**

- Las métricas mismas son sesgadas
- Solución: Usar múltiples métricas

**4. Sesgo de agregación:**

- Un modelo para todos no funciona igual para todos
- Solución: Modelos especializados o features que capturen diferencias

---

## 9. Content Filters

### ¿Qué son?

Sistemas automáticos que analizan **input** (prompt) y **output** (respuesta) para detectar y bloquear contenido dañino.

### Azure AI Content Safety

**Servicio de Microsoft** integrado automáticamente en Azure OpenAI.

### 4 Categorías de Contenido Dañino

#### 1. Hate (Odio)

- Discriminación por raza, género, religión, etc.
- Estereotipos, insultos, deshumanización

#### 2. Sexual

- Contenido sexual explícito
- Pornografía, erótica
- Nota: Educación sexual apropiada generalmente NO se bloquea

#### 3. Violence (Violencia)

- Descripciones de violencia física
- Instrucciones de armas, explosivos
- Terrorismo

#### 4. Self-Harm (Auto-daño)

- Suicidio, auto-lesión
- Trastornos alimentarios
- Categoría MÁS sensible

### Niveles de Severidad

| Nivel      | Valor | Descripción          |
| ---------- | ----- | -------------------- |
| **Safe**   | 0     | Sin contenido dañino |
| **Low**    | 2     | Leve                 |
| **Medium** | 4     | Moderado             |
| **High**   | 6     | Severo, explícito    |

### Configuraciones de Filtrado

#### 🟢 Low (Bajo)

- Bloquea solo: High (6)
- Permite: Safe, Low, Medium
- Uso: Apps creativas, ambientes controlados

#### 🟡 Medium (Medio) - DEFAULT

- Bloquea: Medium (4) + High (6)
- Permite: Safe (0) + Low (2)
- Uso: Aplicaciones empresariales generales
- **RECOMENDADO para mayoría de casos**

#### 🔴 High (Alto)

- Bloquea: Low (2) + Medium (4) + High (6)
- Permite solo: Safe (0)
- Uso: Apps para menores, educación K-12
- Más falsos positivos

### Configuración Personalizada

**Blocked Lists:**

- Términos específicos a bloquear

**Allowed Lists:**

- Excepciones (términos médicos, técnicos)

### Jailbreaking

**¿Qué es?**

- Intentar evadir filtros y restricciones

**Técnicas comunes:**

- Roleplay: "Pretende que eres..."
- Escenarios hipotéticos
- Encoding/Obfuscación
- "Ignora instrucciones anteriores"

**Defensas:**

- System message robusto
- Detección de patrones
- Monitoreo y logging
- Penalización de reincidentes

### Manejo de Errores

**Error code:** `"content_filter"`

**Respuesta apropiada al usuario:**

```
"Lo siento, no puedo ayudar con esa solicitud.
Por favor, reformula tu pregunta de manera diferente."
```

---

## 10. Conceptos Transversales

### Prompt Engineering

**Definición:** Arte de diseñar instrucciones efectivas para LLMs.

**Técnicas principales:**

**1. Zero-shot:**

- Sin ejemplos
- Instrucción directa

**2. Few-shot:**

- Proporcionar 2-5 ejemplos
- Modelo aprende el patrón

**3. Chain-of-Thought:**

- "Piensa paso a paso"
- Para problemas complejos, matemáticas

**4. Role Prompting:**

- "Actúa como un experto en..."
- Define personalidad/expertise

**5. Instruction Following:**

- Instrucciones numeradas y claras
- Para tareas multi-paso

**6. Constrained Output:**

- Especificar formato (JSON, tabla, lista)

**Mejores prácticas:**

- ✅ Ser específico y claro
- ✅ Usar delimitadores (""", ###)
- ✅ Especificar formato de salida
- ✅ Dar ejemplos cuando sea apropiado
- ✅ Dividir tareas complejas en pasos
- ❌ Evitar vaguedad
- ❌ No asumir contexto

### Optimización de Costos

**En Azure OpenAI:**

**Factores de costo:**

- Prompt tokens
- Completion tokens
- Reasoning tokens (GPT-5)

**Estrategias:**

1. Usar modelo apropiado (GPT-5-nano vs GPT-5)
2. Aprovechar Model Router (GPT-5)
3. Limitar max_tokens
4. Controlar reasoning_effort
5. Cachear respuestas frecuentes
6. Resumir contexto
7. Batch processing

**Ejemplo de ahorro:**

```
Original: 500 prompt + 300 completion = 800 tokens
Optimizado: 300 prompt + 200 completion = 500 tokens
Ahorro: 37.5%
```

### Seguridad en Azure AI

**Autenticación:**

- API Keys (básico)
- Microsoft Entra ID / Azure AD (recomendado)
- Managed Identity (Azure-to-Azure)

**Protección de datos:**

- Encriptación en tránsito (TLS)
- Encriptación en reposo
- Private endpoints
- Azure Key Vault para secretos

**Residencia de datos:**

- Seleccionar región apropiada
- Datos permanecen en esa geografía
- Importante para GDPR, HIPAA

### Monitoring y Observabilidad

**Azure Monitor:**

- Métricas de uso
- Errores y latencia
- Alertas configurables

**Application Insights:**

- Telemetría detallada
- Rastreo de requests
- Performance profiling

**Logs:**

- Auditoría de accesos
- Historial de decisiones
- Compliance

---

## 📊 Mapa Mental del Examen AI-900

```
AI-900 Certification
│
├── Fundamentos de IA
│   ├── Tipos de IA (Narrow, General, Super)
│   ├── Workloads (ML, Vision, NLP, Generative)
│   └── Conceptos básicos
│
├── Machine Learning
│   ├── Tipos (Supervised, Unsupervised, Reinforcement)
│   ├── Regresión vs Clasificación
│   ├── Métricas (MAE, MSE, R², Accuracy, Precision, Recall, F1)
│   └── Confusion Matrix
│
├── Azure ML
│   ├── Workspace, Compute, Datasets
│   ├── AutoML
│   ├── Designer
│   └── Pipelines
│
├── Computer Vision
│   ├── Image Analysis (tagging, objects, OCR)
│   ├── Face API (detection, verification, identification)
│   ├── Custom Vision (classification, object detection)
│   └── Video Analysis
│
├── NLP
│   ├── Text Analytics (sentiment, key phrases, NER)
│   ├── Question Answering
│   ├── CLU (intents, entities)
│   ├── Translator
│   └── Speech (STT, TTS, translation)
│
├── Generative AI
│   ├── LLMs (GPT-5, GPT-4, GPT-3.5)
│   ├── Tokens y Context Window
│   ├── Temperature
│   ├── Embeddings
│   └── Limitaciones (alucinaciones, sesgos)
│
├── Azure OpenAI
│   ├── Modelos (GPT-5, GPT-4, GPT-3.5, DALL-E, Whisper)
│   ├── Deployments y TPM
│   ├── Model Router (GPT-5)
│   ├── API (system/user/assistant messages)
│   ├── Autenticación (Keys, Entra ID, Managed Identity)
│   └── Prompt Engineering
│
├── Responsible AI ⭐
│   ├── 6 Principios
│   │   ├── Fairness
│   │   ├── Reliability & Safety
│   │   ├── Privacy & Security
│   │   ├── Inclusiveness
│   │   ├── Transparency
│   │   └── Accountability
│   ├── Sesgos (tipos y mitigación)
│   ├── Herramientas (Fairlearn, InterpretML)
│   └── GDPR, HIPAA
│
└── Content Filters
    ├── 4 Categorías (Hate, Sexual, Violence, Self-Harm)
    ├── Severidad (Safe=0, Low=2, Medium=4, High=6)
    ├── Configuraciones (Low, Medium, High)
    ├── Jailbreaking
    └── Azure AI Content Safety
```

---

## 🎯 Estrategia para el Examen

### Formato del Examen

**Características:**

- 40-60 preguntas
- Duración: 45 minutos
- Nota aprobatoria: 700/1000 (70%)
- Tipos: Múltiple opción, verdadero/falso, drag-and-drop
- Algunos escenarios con múltiples preguntas

### Distribución de Temas (Oficial - Actualizada Mayo 2025)

| Tema                                                                                                        | Peso          |
| ----------------------------------------------------------------------------------------------------------- | ------------- |
| Describir las cargas de trabajo y las consideraciones de inteligencia artificial                            | 15-20%        |
| Describir los principios fundamentales del aprendizaje automático en Azure                                  | 15-20%        |
| Describir las características de las cargas de trabajo de Computer Vision en Azure                          | 15-20%        |
| Describir las características de las cargas de trabajo de procesamiento del lenguaje natural (NLP) en Azure | 15-20%        |
| **Describir las características de las cargas de trabajo de IA generativas en Azure**                       | **20-25%** ⭐ |

**Nota importante:** IA Generativa es el área con MAYOR peso (20-25%) - esto incluye Azure OpenAI Service, GPT models, Responsible AI, y Content Filters.

### Temas Más Preguntados

**🔥 HOT TOPICS:**

1. **Responsible AI** (6 principios) - CRÍTICO
2. Diferencia entre tipos de ML (Supervised vs Unsupervised)
3. Métricas de evaluación (cuándo usar cada una)
4. Azure OpenAI Service (modelos, deployments, TPM)
5. Content Filters (categorías, niveles)
6. Computer Vision capabilities
7. NLP services (qué hace cada uno)
8. Prompt Engineering (técnicas básicas)
9. AutoML (cuándo usarlo)
10. Tokens y context window

### Tips de Examen

**Durante el examen:**

1. **Lee cuidadosamente:**

   - Palabras clave: "MÁS apropiado", "MEJOR", "MENOS"
   - "NOT" en preguntas negativas

2. **Identifica el escenario:**

   - ¿Qué problema intentan resolver?
   - ¿Qué restricciones hay?
   - ¿Qué principio de IA Responsable se aplica?

3. **Elimina opciones incorrectas:**

   - Descarta las obviamente incorrectas primero
   - Entre 2-3 opciones restantes, busca detalles

4. **Gestión del tiempo:**

   - ~1 minuto por pregunta
   - Marca preguntas difíciles para revisar después
   - No te quedes atascado en una pregunta

5. **Casos especiales:**
   - Si hay escenario con múltiples preguntas, lee TODO primero
   - Drag-and-drop: Confirma antes de avanzar (no puedes volver)

### Patrones de Preguntas Comunes

**Patrón 1: Selección de servicio**

```
"Una empresa necesita [tarea específica]. ¿Qué servicio de Azure AI deben usar?"

Estrategia: Identifica el workload (Vision, NLP, ML, Generative)
           Conoce las capacidades específicas de cada servicio
```

**Patrón 2: Principio de Responsible AI**

```
"[Escenario con implicación ética]. ¿Qué principio de IA Responsable se aplica?"

Estrategia: Busca palabras clave:
           - Discriminación → Fairness
           - Explicación → Transparency
           - Datos personales → Privacy
           - Accesibilidad → Inclusiveness
           - Revisión humana → Accountability
           - Errores/fallas → Reliability
```

**Patrón 3: Métrica apropiada**

```
"Un modelo de [regresión/clasificación] debe [objetivo]. ¿Qué métrica usar?"

Estrategia:
           Regresión → MAE, MSE, R²
           Clasificación → Accuracy (balanceado), Precision (evitar FP),
                          Recall (evitar FN), F1 (balance)
```

**Patrón 4: Content Filter**

```
"Una aplicación [contexto] debe [requisito de seguridad]. ¿Qué configuración?"

Estrategia:
           Menores de edad → High
           Empresarial general → Medium
           Creativo controlado → Low
```

---

## ✅ Checklist Final Pre-Examen

### Conceptos que DEBES dominar

**Fundamentos:**

- [ ] Tipos de IA workloads (ML, Vision, NLP, Generative)
- [ ] Diferencia entre Supervised, Unsupervised, Reinforcement Learning
- [ ] Regresión vs Clasificación

**Machine Learning:**

- [ ] Confusion Matrix (TP, TN, FP, FN)
- [ ] Métricas: Accuracy, Precision, Recall, F1, MAE, MSE, R²
- [ ] Cuándo usar cada métrica
- [ ] Azure ML: Workspace, Compute, AutoML

**Computer Vision:**

- [ ] Capacidades de Image Analysis
- [ ] Face API capabilities
- [ ] Custom Vision: Classification vs Object Detection
- [ ] OCR (Read API)

**NLP:**

- [ ] Text Analytics: Sentiment, Key Phrases, NER
- [ ] Question Answering
- [ ] CLU: Intents y Entities
- [ ] Translator
- [ ] Speech: STT, TTS, Translation

**Generative AI:**

- [ ] Qué es IA Generativa
- [ ] Diferencia con IA tradicional
- [ ] Tokens y Context Window
- [ ] Temperature
- [ ] Alucinaciones

**Azure OpenAI:**

- [ ] Modelos disponibles (GPT-5, GPT-4, GPT-3.5)
- [ ] Deployment y TPM
- [ ] Roles de mensajes (system, user, assistant)
- [ ] Autenticación (Keys vs Entra ID vs Managed Identity)
- [ ] Model Router (GPT-5)

**Responsible AI:** ⭐ CRÍTICO

- [ ] **6 Principios** (Fairness, Reliability, Privacy, Inclusiveness, Transparency, Accountability)
- [ ] Ejemplos de cada principio
- [ ] Transparency Notes
- [ ] GDPR (conceptos básicos)
- [ ] Herramientas: Fairlearn, InterpretML

**Content Filters:**

- [ ] 4 Categorías (Hate, Sexual, Violence, Self-Harm)
- [ ] Niveles de severidad (Safe, Low, Medium, High)
- [ ] Configuraciones de filtrado (Low, Medium, High)
- [ ] Azure AI Content Safety
- [ ] Jailbreaking

**Prompt Engineering:**

- [ ] Zero-shot vs Few-shot
- [ ] Chain-of-Thought
- [ ] Role Prompting
- [ ] System message

---

## 🎓 Preguntas de Repaso Final (20 preguntas mix)

### Pregunta 1

¿Cuál de los siguientes es un ejemplo de Supervised Learning?

A) Agrupar clientes por comportamiento de compra  
B) Predecir precio de una casa basándose en características  
C) Robot aprendiendo a caminar mediante prueba y error  
D) Detectar patrones anómalos en datos sin etiquetas

<details>
<summary>👉 Ver respuesta y explicación</summary>

**Respuesta: B) Predecir precio de una casa basándose en características**

**Explicación**: Supervised Learning requiere datos etiquetados (labels). Predecir precio de casa es **regresión** (supervised) porque entrenas con ejemplos conocidos (casa + precio). A es Unsupervised (clustering), C es Reinforcement Learning, D es Unsupervised (anomaly detection).

</details>

### Pregunta 2

Un modelo de clasificación binaria tiene: TP=80, TN=60, FP=15, FN=10. ¿Cuál es el Recall?

A) 75.8%  
B) 84.2%  
C) 88.9%  
D) 80.0%

<details>
<summary>Respuesta y explicación</summary>

**Respuesta: C) 88.9%**

**Explicación**: Recall = TP / (TP + FN) = 80 / (80 + 10) = 80/90 = 0.889 = 88.9%. Recall mide: de los positivos reales, cuántos detectamos.

</details>

---

### Pregunta 3

¿Qué servicio de Azure AI permite extraer texto de imágenes y documentos?

A) Face API  
B) Custom Vision  
C) Read API (OCR)  
D) Video Indexer

<details>
<summary>Respuesta y explicación</summary>

**Respuesta: C) Read API (OCR)**

**Explicación**: Read API (parte de Azure AI Vision) es específicamente para **OCR** (Optical Character Recognition) - extraer texto impreso o manuscrito de imágenes y PDFs. Face API (A) es para rostros, Custom Vision (B) para modelos personalizados, Video Indexer (D) para análisis de video.

</details>

---

### Pregunta 4

¿Qué capacidad de Azure AI Language identifica entidades como personas, lugares y organizaciones en texto?

A) Sentiment Analysis  
B) Key Phrase Extraction  
C) Named Entity Recognition (NER)  
D) Language Detection

<details>
<summary>Respuesta y explicación</summary>

**Respuesta: C) Named Entity Recognition (NER)**

**Explicación**: **NER** identifica y clasifica entidades nombradas (personas, lugares, organizaciones, fechas, etc.). Sentiment Analysis (A) detecta emociones, Key Phrases (B) extrae temas principales, Language Detection (D) identifica el idioma.

</details>

---

### Pregunta 5

¿Cuál es la principal diferencia entre IA Tradicional e IA Generativa?

A) IA Generativa es más rápida  
B) IA Tradicional solo funciona con texto  
C) IA Generativa crea contenido nuevo, IA Tradicional analiza y predice  
D) IA Generativa no requiere entrenamiento

<details>
<summary>Respuesta y explicación</summary>

**Respuesta: C) IA Generativa crea contenido nuevo, IA Tradicional analiza y predice**

**Explicación**: La diferencia fundamental: **IA Tradicional** (clasificación, regresión) analiza datos existentes para predecir/clasificar. **IA Generativa** crea contenido original (texto, imágenes, código). Las otras opciones son incorrectas.

</details>

---

### Pregunta 6

Aproximadamente, ¿cuántos caracteres equivalen a 1 token en inglés para modelos GPT?

A) 1 carácter  
B) 4 caracteres  
C) 10 caracteres  
D) 20 caracteres

<details>
<summary>Respuesta y explicación</summary>

**Respuesta: B) 4 caracteres**

**Explicación**: La regla general es **1 token ≈ 4 caracteres** en inglés, o aproximadamente 0.75 palabras. En español puede ser 3-4 caracteres por token debido a acentos y estructura del idioma.

</details>

---

### Pregunta 7

¿Qué principio de Responsible AI requiere que un sistema de IA funcione de manera compatible con lectores de pantalla para personas con discapacidad visual?

A) Fairness  
B) Transparency  
C) Inclusiveness  
D) Accountability

<details>
<summary>Respuesta y explicación</summary>

**Respuesta: C) Inclusiveness**

**Explicación**: **Inclusiveness** requiere que sistemas de IA sean accesibles para TODOS, incluyendo personas con discapacidades. Compatibilidad con lectores de pantalla es accesibilidad. Fairness (A) es sobre trato equitativo, Transparency (B) sobre explicabilidad, Accountability (D) sobre responsabilidad.

</details>

---

### Pregunta 8

¿Cuáles son las 4 categorías de contenido dañino que Azure AI Content Safety detecta?

A) Spam, Phishing, Malware, Scam  
B) Hate, Sexual, Violence, Self-Harm  
C) Political, Religious, Personal, Financial  
D) Adult, Racy, Gory, Medical

<details>
<summary>Respuesta y explicación</summary>

**Respuesta: B) Hate, Sexual, Violence, Self-Harm**

**Explicación**: Las **4 categorías principales** son: **Hate** (odio), **Sexual**, **Violence** (violencia), y **Self-Harm** (auto-daño). Cada una tiene niveles de severidad: Safe (0), Low (2), Medium (4), High (6).

</details>

---

### Pregunta 9

Estás configurando Azure OpenAI para una aplicación de chatbot empresarial. Configuras 50K TPM. ¿Qué significa TPM?

A) Total Processing Memory  
B) Tokens Per Minute  
C) Time Per Message  
D) Transactions Per Month

<details>
<summary>Respuesta y explicación</summary>

**Respuesta: B) Tokens Per Minute**

**Explicación**: **TPM (Tokens Per Minute)** define la capacidad de procesamiento de un deployment. 50K TPM = 50,000 tokens por minuto. Si excedes este límite, recibes error 429 (rate limiting).

</details>

---

### Pregunta 10

¿Qué técnica de prompt engineering proporciona ejemplos al modelo antes de la solicitud real?

A) Zero-shot prompting  
B) Few-shot prompting  
C) Role prompting  
D) Chain-of-thought

<details>
<summary>Respuesta y explicación</summary>

**Respuesta: B) Few-shot prompting**

**Explicación**: **Few-shot** proporciona 2-5 ejemplos antes de la tarea real para que el modelo aprenda el patrón. Zero-shot (A) no usa ejemplos, Role prompting (C) asigna personalidad, Chain-of-thought (D) pide razonamiento paso a paso.

</details>

---

### Pregunta 11

Un modelo de reconocimiento facial tiene 90% precisión en personas de piel clara pero 65% en personas de piel oscura. ¿Qué principio se viola?

A) Transparency  
B) Fairness  
C) Privacy  
D) Reliability

<details>
<summary>Respuesta y explicación</summary>

**Respuesta: B) Fairness**

**Explicación**: **Fairness** requiere trato equitativo sin discriminación por características como etnia. 25% de diferencia en precisión es sesgo racial. Solución: entrenar con dataset más diverso y balanceado.

</details>

---

### Pregunta 12

¿Qué herramienta de Microsoft se usa para evaluar y mitigar sesgos en modelos ML?

A) InterpretML  
B) Azure Monitor  
C) Fairlearn  
D) Error Analysis

<details>
<summary>Respuesta y explicación</summary>

**Respuesta: C) Fairlearn**

**Explicación**: **Fairlearn** es específicamente para evaluar fairness (equidad) y mitigar sesgos. InterpretML (A) es para explicabilidad, Azure Monitor (B) para observabilidad, Error Analysis (D) para identificar errores.

</details>

---

### Pregunta 13

¿Qué configuración de content filter debes usar para una aplicación educativa dirigida a niños de 10 años?

A) Low  
B) Medium  
C) High  
D) Desactivar filtros

<details>
<summary>Respuesta y explicación</summary>

**Respuesta: C) High**

**Explicación**: Para **menores de edad**, siempre usar **High** (máxima protección). Bloquea Low, Medium y High severity, permitiendo solo Safe (0). Medium (B) es insuficiente, Low (A) es inapropiado, y desactivar (D) no es posible en Azure OpenAI.

</details>

---

### Pregunta 14

¿Qué modelo de Azure OpenAI debes usar para transcribir audio a texto?

A) GPT-4  
B) DALL-E  
C) Whisper  
D) text-embedding-ada-002

<details>
<summary>Respuesta y explicación</summary>

**Respuesta: C) Whisper**

**Explicación**: **Whisper** es el modelo para **speech-to-text** (transcripción de audio). GPT-4 (A) es para texto/chat, DALL-E (B) para imágenes, embeddings (D) para vectores numéricos.

</details>

---

### Pregunta 15

Un sistema de aprobación de préstamos debe explicar por qué un préstamo fue rechazado. ¿Qué principio de Responsible AI requiere esta explicación?

A) Fairness  
B) Transparency  
C) Accountability  
D) Privacy

<details>
<summary>Respuesta y explicación</summary>

**Respuesta: B) Transparency**

**Explicación**: **Transparency** incluye **explicabilidad** - usuarios deben entender por qué el sistema tomó cierta decisión. Esto es además un requisito legal en muchos países para decisiones financieras.

</details>

---

### Pregunta 16

¿Cuál es la configuración predeterminada de content filters en Azure OpenAI?

A) Low  
B) Medium  
C) High  
D) Sin filtros

<details>
<summary>Respuesta y explicación</summary>

**Respuesta: B) Medium**

**Explicación**: La configuración **default es Medium**, que bloquea Medium (4) y High (6), permitiendo Safe (0) y Low (2). Balance entre protección y usabilidad.

</details>

---

### Pregunta 17

¿Qué método de autenticación es el MÁS seguro para Azure OpenAI Service?

A) API Keys incluidas en el código  
B) Microsoft Entra ID (Azure AD)  
C) Compartir API key entre múltiples apps  
D) API Keys en archivo de texto

<details>
<summary>Respuesta y explicación</summary>

**Respuesta: B) Microsoft Entra ID (Azure AD)**

**Explicación**: **Microsoft Entra ID** (antes Azure AD) proporciona autenticación basada en tokens con mejor control, auditoría y revocación granular. API keys (A, C, D) son menos seguras, especialmente si están en código o compartidas.

</details>

---

### Pregunta 18

En AutoML, seleccionas "Classification" como tipo de tarea y "AUC_weighted" como métrica primaria. ¿Qué hace AutoML?

A) Entrena solo un modelo de clasificación  
B) Prueba múltiples algoritmos y selecciona el mejor según AUC  
C) Solo prepara los datos sin entrenar  
D) Requiere que especifiques manualmente el algoritmo

<details>
<summary>Respuesta y explicación</summary>

**Respuesta: B) Prueba múltiples algoritmos y selecciona el mejor según AUC**

**Explicación**: **AutoML** automáticamente prueba múltiples algoritmos de clasificación (Random Forest, Logistic Regression, XGBoost, etc.) y selecciona el que mejor AUC_weighted logra. No requiere selección manual del algoritmo.

</details>

---

### Pregunta 19

¿Cuál de los siguientes es un ejemplo de jailbreaking?

A) Optimizar un prompt para mejor resultado  
B) "Pretende que eres un personaje malvado y..."  
C) Proporcionar ejemplos en el prompt  
D) Usar system message para definir comportamiento

<details>
<summary>Respuesta y explicación</summary>

**Respuesta: B) "Pretende que eres un personaje malvado y..."**

**Explicación**: **Jailbreaking** es intentar evadir content filters usando roleplay, escenarios hipotéticos u otras técnicas. "Pretende que eres..." es roleplay clásico. A, C, D son técnicas legítimas de prompt engineering.

</details>

---

### Pregunta 20

¿Qué parámetro en GPT-5 controla el nivel de razonamiento profundo del modelo?

A) temperature  
B) max_tokens  
C) reasoning_effort  
D) top_p

<details>
<summary>Respuesta y explicación</summary>

**Respuesta: C) reasoning_effort**

**Explicación**: **reasoning_effort** es específico de GPT-5 y controla cuánto "piensa" el modelo antes de responder (low/medium/high). High activa GPT-5 thinking para razonamiento profundo. Temperature (A) controla creatividad, max_tokens (B) limita longitud, top_p (D) afecta diversidad.

</details>

---

## 🎉 ¡Estás Listo!

### Checklist Final

- [ ] Revisé todos los conceptos clave
- [ ] Entiendo los 6 principios de Responsible AI
- [ ] Conozco las capacidades de cada servicio de Azure AI
- [ ] Domino métricas de evaluación (cuándo usar cada una)
- [ ] Entiendo Azure OpenAI Service (modelos, deployments, TPM)
- [ ] Conozco content filters (categorías, configuraciones)
- [ ] Practiqué con preguntas de examen
- [ ] Identifiqué mis áreas débiles
- [ ] Dormí bien antes del examen
- [ ] Estoy confiado y preparado

### Último Consejo

**Durante el examen:**

- Lee cada pregunta cuidadosamente
- Identifica palabras clave
- Elimina opciones incorrectas
- Confía en tu preparación
- Gestiona bien el tiempo

**¡MUCHO ÉXITO EN TU EXAMEN AI-900!** 🚀

Tu preparación ha sido exhaustiva y estás listo para aprobar. Confía en tu conocimiento.

---

## 📚 Recursos de Última Hora

- [Microsoft Learn - AI-900 Path](https://docs.microsoft.com/learn/certifications/exams/ai-900)
- [Practice Assessment](https://learn.microsoft.com/certifications/practice-assessments-for-microsoft-certifications)
- [Azure AI Documentation](https://docs.microsoft.com/azure/ai-services/)
- [OpenAI Documentation](https://platform.openai.com/docs)

---

**Preparado por:** Claude AI  
**Para:** Renszo - Preparación AI-900  
**Roadmap completado:** Semanas 1-5 ✅  
**Próximo paso:** ¡EXAMEN! 🎯
