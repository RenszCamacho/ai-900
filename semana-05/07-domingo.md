# AI-900 Certification - Contenido Complementario

## Temas Actualizados Mayo 2025

**Fecha:** Complemento al Mega Repaso  
**Duración estimada:** 30-45 minutos  
**Nivel:** Fundamental

---

## 📋 Objetivo

Cubrir temas nuevos/actualizados en la guía oficial de AI-900 (actualizada mayo 2025):

1. Azure AI Foundry (antes Azure AI Studio)
2. Catálogo de modelos de Azure AI Foundry
3. Arquitectura Transformer
4. Actualizaciones terminológicas importantes

---

## 1. Azure AI Foundry (Antes Azure AI Studio)

### ¿Qué es Azure AI Foundry?

**Azure AI Foundry** es el nuevo nombre del portal unificado de Microsoft para desarrollo de aplicaciones de IA. Anteriormente conocido como "Azure AI Studio" y "Azure Machine Learning Studio".

**Nombre oficial actual:** Azure AI Foundry

### Componentes Principales

#### 1. Portal Unificado

**Azure AI Foundry Portal** incluye:

- **Projects**: Espacios de trabajo para organizar recursos de IA
- **Hubs**: Colecciones de recursos compartidos entre proyectos
- **Deployments**: Gestión de modelos desplegados
- **Playground**: Interfaz interactiva para probar modelos
- **Model Catalog**: Catálogo de modelos disponibles

#### 2. Capabilities (Capacidades)

**Azure AI Foundry proporciona:**

✅ **Desarrollo unificado:**

- Un solo lugar para todos los servicios de Azure AI
- Interfaz consistente para diferentes tipos de modelos
- Integración con VS Code y GitHub

✅ **Model deployment:**

- Despliegue de modelos con pocos clics
- Configuración de endpoints
- Escalado automático
- Monitoreo integrado

✅ **Prompt engineering:**

- Playground interactivo
- Testing de prompts
- Comparación de modelos
- Export de código (Python, C#, JavaScript)

✅ **Safety & Responsible AI:**

- Content filters configurables
- Evaluación de riesgos
- Transparency tools
- Responsible AI dashboard

✅ **Data & Fine-tuning:**

- Subir datasets personalizados
- Fine-tune de modelos
- Evaluación de rendimiento
- Gestión de versiones

### Azure AI Foundry vs Azure OpenAI Studio

**Relación:**

- Azure OpenAI Studio está **dentro** de Azure AI Foundry
- Azure AI Foundry es más amplio (incluye todos los servicios de Azure AI)
- Azure OpenAI Studio se enfoca específicamente en modelos OpenAI

```
Azure AI Foundry (Portal completo)
    ├── Azure OpenAI Service
    │   └── GPT-5, GPT-4, DALL-E, Whisper
    ├── Azure AI Vision
    ├── Azure AI Language
    ├── Azure AI Speech
    ├── Azure Machine Learning
    └── Model Catalog (otros modelos)
```

### Acceso a Azure AI Foundry

**URL:** https://ai.azure.com

**Requisitos:**

- Suscripción de Azure
- Permisos apropiados (Contributor o Owner)
- Recursos de Azure AI creados

### Flujo de Trabajo Típico en Azure AI Foundry

**Paso 1: Crear Hub**

```
Azure AI Foundry → Create Hub
- Nombre del hub
- Región
- Resource group
- Azure OpenAI connection (opcional)
```

**Paso 2: Crear Project**

```
Hub → Create Project
- Nombre del proyecto
- Asociado al hub
```

**Paso 3: Seleccionar Modelo**

```
Project → Model Catalog
- Explorar modelos disponibles
- Seleccionar modelo (ej: GPT-5)
```

**Paso 4: Desplegar Modelo**

```
Model → Deploy
- Nombre del deployment
- Configurar TPM
- Región
```

**Paso 5: Probar en Playground**

```
Deployment → Open Playground
- Escribir prompts
- Ajustar parámetros
- Ver resultados
```

**Paso 6: Integrar en Aplicación**

```
Playground → View Code
- Copiar código de ejemplo
- Usar en tu app (Python, C#, JS)
```

---

## 2. Catálogo de Modelos de Azure AI Foundry

### ¿Qué es el Model Catalog?

El **Model Catalog** (Catálogo de Modelos) es una colección curada de modelos de IA disponibles en Azure AI Foundry.

### Tipos de Modelos en el Catálogo

#### 1. Modelos de Microsoft

**Azure OpenAI models:**

- GPT-5 (y variantes: mini, nano, chat)
- GPT-4 (y variantes: turbo, o)
- GPT-3.5-turbo
- DALL-E 2, DALL-E 3
- Whisper
- text-embedding-ada-002
- text-embedding-3-small/large

**Azure AI models:**

- Phi-3 (Small Language Model de Microsoft)
- Florence (Vision-Language model)
- Orca (Reasoning model)

#### 2. Modelos Open Source

**Meta (Facebook):**

- Llama 2 (7B, 13B, 70B)
- Llama 3 (8B, 70B, 405B)
- Code Llama (programación)

**Mistral AI:**

- Mistral 7B
- Mixtral 8x7B
- Mistral Large

**Otros:**

- Cohere Command
- AI21 Jurassic
- Stable Diffusion (imágenes)
- Falcon

#### 3. Modelos de Socios (Partners)

**Hugging Face:**

- Acceso a miles de modelos de Hugging Face Hub
- Integración directa

**NVIDIA:**

- Modelos optimizados para GPUs NVIDIA
- Nemotron

### Características del Model Catalog

#### Información de Modelos

Para cada modelo, el catálogo proporciona:

**1. Descripción:**

- Qué hace el modelo
- Casos de uso apropiados
- Limitaciones conocidas

**2. Especificaciones técnicas:**

- Tamaño del modelo (parámetros)
- Context window
- Input/Output types
- Idiomas soportados

**3. Licencia:**

- MIT, Apache 2.0, Commercial, etc.
- Restricciones de uso

**4. Pricing:**

- Pay-as-you-go
- PTU (Provisioned Throughput Units)
- Free tier (algunos modelos)

**5. Disponibilidad:**

- Regiones donde está disponible
- Requisitos de acceso

#### Deployment Options

**Deployment types disponibles:**

**1. Serverless API:**

- Sin infraestructura que gestionar
- Pay-per-use
- Escalado automático
- Ideal para: Experimentación, desarrollo

**2. Managed Online Endpoints:**

- Control sobre compute
- Dedicated resources
- SLA garantizado
- Ideal para: Producción

**3. Batch Endpoints:**

- Procesamiento por lotes
- Más económico para grandes volúmenes
- No real-time
- Ideal para: Procesamiento masivo

### Cómo Usar el Model Catalog

#### Explorar Modelos

**Filtros disponibles:**

- **Task type**: Text generation, Vision, Speech, etc.
- **Publisher**: Microsoft, Meta, Mistral, etc.
- **License**: Open source, Commercial
- **Deployment option**: Serverless, Managed

**Ejemplo de búsqueda:**

```
Task: "Text generation"
Publisher: "Meta"
License: "Open source"

Resultado: Llama 3 models
```

#### Comparar Modelos

**Métricas de comparación:**

- Performance (benchmarks)
- Context window
- Cost per token
- Latency
- Capabilities

**Ejemplo:**

```
GPT-4 vs Llama 3 70B:
- Performance: GPT-4 superior en razonamiento
- Context window: GPT-4 128K, Llama 3 8K
- Cost: Llama 3 más económico
- Latency: Similar
```

#### Desplegar desde el Catálogo

**Pasos:**

1. Model Catalog → Seleccionar modelo
2. "Deploy" button
3. Elegir deployment type (Serverless/Managed)
4. Configurar:
   - Deployment name
   - Region
   - Compute size (si Managed)
5. Deploy
6. Obtener endpoint y key

---

## 3. Arquitectura Transformer

### ¿Qué es la Arquitectura Transformer?

**Transformer** es la arquitectura de red neuronal que revolucionó el procesamiento de lenguaje natural y es la base de modelos como GPT, BERT, y la mayoría de LLMs modernos.

### Historia Breve

**2017:** Paper "Attention is All You Need" (Google)

- Introduce la arquitectura Transformer
- Reemplaza RNNs y LSTMs

**2018-2019:** Explosión de modelos basados en Transformer

- BERT (Google)
- GPT-2 (OpenAI)

**2020-presente:** Era de LLMs

- GPT-3, GPT-4, GPT-5
- Transformers domina NLP, Vision, Multimodal

### Componentes Clave de Transformer

#### 1. Attention Mechanism (Mecanismo de Atención)

**Concepto:**

- El modelo "presta atención" a diferentes partes del input
- Determina qué palabras son relevantes para cada palabra

**Ejemplo:**

```
Frase: "El gato comió el pescado porque tenía hambre"

Al procesar "tenía", el modelo atiende a:
- "gato" (alta atención) ← sujeto
- "comió" (media atención) ← verbo relacionado
- "pescado" (baja atención) ← objeto

Conclusión: "tenía" se refiere al gato, no al pescado
```

**Self-Attention:**

- Cada palabra atiende a todas las demás palabras
- Captura relaciones y dependencias
- Procesamiento en paralelo (no secuencial)

#### 2. Multi-Head Attention

**Concepto:**

- Múltiples "attention heads" trabajando en paralelo
- Cada head puede aprender diferentes tipos de relaciones

**Ejemplo:**

```
Head 1: Relaciones sintácticas (sujeto-verbo)
Head 2: Relaciones semánticas (sinónimos, conceptos)
Head 3: Relaciones posicionales (cerca/lejos)
...
Head 8: Otras relaciones

Resultado combinado: Comprensión rica y multidimensional
```

#### 3. Positional Encoding

**Problema:**

- Transformers procesan todo en paralelo
- No tienen noción inherente de orden/posición

**Solución:**

- Positional encodings añaden información de posición
- Cada token recibe un vector que representa su posición

**Resultado:**

- El modelo sabe qué palabra viene antes/después

#### 4. Feed-Forward Networks

**Función:**

- Procesar la información de attention
- Aplicar transformaciones no lineales
- Añadir capacidad de aprendizaje

#### 5. Layer Normalization y Residual Connections

**Propósito:**

- Estabilizar entrenamiento
- Permitir redes más profundas
- Prevenir vanishing gradients

### Arquitecturas Basadas en Transformer

#### 1. Encoder-Only (Solo Codificador)

**Ejemplo:** BERT

**Uso:**

- Comprensión de lenguaje
- Clasificación
- Named Entity Recognition
- Question Answering

**Características:**

- Procesa input completo
- Bidireccional (mira adelante y atrás)
- Mejor para entender contexto

#### 2. Decoder-Only (Solo Decodificador)

**Ejemplo:** GPT (GPT-3, GPT-4, GPT-5)

**Uso:**

- Generación de texto
- Chatbots
- Completación de código
- Traducción

**Características:**

- Genera texto token por token
- Unidireccional (solo mira hacia atrás)
- Autoregresivo (predice siguiente token)

#### 3. Encoder-Decoder (Codificador-Decodificador)

**Ejemplo:** T5, BART

**Uso:**

- Traducción
- Resumen
- Tareas sequence-to-sequence

**Características:**

- Encoder procesa input
- Decoder genera output
- Mejor para transformaciones complejas

### Por Qué Transformers Son Importantes

#### Ventajas sobre arquitecturas anteriores

**vs RNNs/LSTMs:**
✅ Paralelización (más rápido de entrenar)
✅ Captura dependencias largas mejor
✅ Más escalable

**vs CNNs (para NLP):**
✅ Mejor para secuencias largas
✅ Captura contexto global
✅ Más flexible

#### Aplicaciones Modernas

**NLP:**

- ChatGPT, Claude, Gemini
- Traducción automática
- Resumen de documentos

**Computer Vision:**

- Vision Transformers (ViT)
- DALL-E, Stable Diffusion
- Detección de objetos

**Multimodal:**

- GPT-4 Vision
- Flamingo
- CLIP

**Audio:**

- Whisper (transcripción)
- AudioLM (generación)

### Conceptos Clave para el Examen

**Lo que DEBES saber:**

✅ Transformer es la arquitectura base de modelos como GPT  
✅ Attention mechanism permite al modelo enfocarse en partes relevantes del input  
✅ Self-attention captura relaciones entre todas las palabras  
✅ Multi-head attention aprende diferentes tipos de relaciones  
✅ Transformers procesan en paralelo (más rápido que RNNs)  
✅ GPT usa decoder-only architecture (genera texto)  
✅ Transformers se usan en NLP, Vision, Audio, Multimodal

**Lo que NO necesitas saber para AI-900:**
❌ Implementación matemática detallada  
❌ Código de implementación  
❌ Detalles de backpropagation  
❌ Optimizaciones específicas

---

## 4. Actualizaciones Terminológicas Importantes

### Cambios de Nombres de Servicios

| Nombre Anterior        | Nombre Actual                                   | Notas                       |
| ---------------------- | ----------------------------------------------- | --------------------------- |
| Azure AI Studio        | **Azure AI Foundry**                            | Portal principal            |
| Cognitive Services     | **Azure AI Services**                           | Nombre general de servicios |
| Azure Active Directory | **Microsoft Entra ID**                          | Servicio de identidad       |
| LUIS                   | **Conversational Language Understanding (CLU)** | Parte de Azure AI Language  |

### Nuevos Términos

**Azure AI Foundry Hub:**

- Colección de recursos compartidos
- Nivel organizacional superior a Projects

**Model Router (GPT-5):**

- Sistema que selecciona automáticamente entre modelo rápido y de razonamiento
- Optimiza costo y rendimiento

**Reasoning Tokens:**

- Tokens usados en proceso de razonamiento interno (GPT-5)
- Se cobran aparte de prompt/completion tokens

**Provisioned Throughput Units (PTU):**

- Alternativa a pay-per-token
- Capacidad reservada y predecible

---

## 5. Temas Específicos de la Guía Actualizada

### Identificar características de la arquitectura transformer

**Pregunta típica de examen:**
"¿Qué característica de la arquitectura transformer permite que el modelo determine qué partes del input son más relevantes?"

**Respuesta:** Attention mechanism (Mecanismo de atención)

### Describir las funcionalidades de Azure AI Foundry

**Temas a dominar:**

- Qué es Azure AI Foundry (portal unificado)
- Projects y Hubs
- Model Catalog
- Deployment options (Serverless, Managed)
- Playground
- Integration con desarrollo

### Describir las funcionalidades del catálogo de modelos

**Temas a dominar:**

- Qué modelos están disponibles
- Microsoft vs Open Source vs Partner models
- Cómo comparar modelos
- Deployment types
- Licensing considerations

---

## ✅ Puntos Clave para el Examen

### Azure AI Foundry

- [ ] Azure AI Foundry es el portal unificado para desarrollo de IA en Azure
- [ ] Incluye Projects, Hubs, Model Catalog, Playground
- [ ] Reemplaza/incluye lo que antes era Azure AI Studio
- [ ] URL: https://ai.azure.com
- [ ] Permite desplegar modelos con Serverless o Managed endpoints

### Model Catalog

- [ ] Catálogo curado de modelos de IA disponibles
- [ ] Incluye: Microsoft models, Open Source, Partners
- [ ] Ejemplos: GPT-5, Llama 3, Mistral, Phi-3
- [ ] Información por modelo: descripción, specs, licencia, pricing
- [ ] Deployment options: Serverless API, Managed Endpoints, Batch

### Arquitectura Transformer

- [ ] Base de modelos modernos como GPT
- [ ] Attention mechanism es componente clave
- [ ] Self-attention captura relaciones entre palabras
- [ ] Multi-head attention aprende diferentes relaciones
- [ ] Procesamiento en paralelo (ventaja vs RNNs)
- [ ] Decoder-only para generación (GPT)
- [ ] Encoder-only para comprensión (BERT)

### Terminología Actualizada

- [ ] Azure AI Foundry (antes Azure AI Studio)
- [ ] Microsoft Entra ID (antes Azure AD)
- [ ] CLU (antes LUIS)
- [ ] Model Router (GPT-5)
- [ ] PTU (Provisioned Throughput Units)

---

## 🎯 Preguntas de Práctica - Temas Nuevos

### Pregunta 1

¿Qué portal de Azure proporciona acceso unificado a modelos de IA, incluyendo GPT, Llama, y otros modelos open source?

A) Azure Portal  
B) Azure AI Foundry  
C) Azure DevOps  
D) Azure Marketplace

**Respuesta correcta: B) Azure AI Foundry**

**Explicación**: **Azure AI Foundry** (ai.azure.com) es el portal unificado para desarrollo de aplicaciones de IA que incluye acceso al Model Catalog con modelos de Microsoft, open source y partners. Azure Portal (A) es el portal general de Azure, DevOps (C) es para CI/CD, y Marketplace (D) es para soluciones comerciales.

---

### Pregunta 2

En el Model Catalog de Azure AI Foundry, encuentras el modelo "Llama 3 70B". ¿Qué tipo de modelo es este?

A) Modelo propietario de Microsoft  
B) Modelo open source de Meta  
C) Modelo de Azure OpenAI  
D) Modelo de Azure AI Vision

**Respuesta correcta: B) Modelo open source de Meta**

**Explicación**: **Llama 3** es un modelo de lenguaje open source desarrollado por Meta (Facebook). El Model Catalog incluye modelos de múltiples proveedores: Microsoft (A es incorrecto), OpenAI (C es solo para modelos GPT/DALL-E), y otros. No es un modelo de Vision (D).

---

### Pregunta 3

¿Qué componente de la arquitectura transformer permite al modelo determinar qué palabras son más relevantes al procesar una oración?

A) Recurrent layers  
B) Convolutional filters  
C) Attention mechanism  
D) Pooling layers

**Respuesta correcta: C) Attention mechanism**

**Explicación**: El **attention mechanism** (mecanismo de atención) es el componente clave de transformers que permite al modelo "prestar atención" a diferentes partes del input y determinar cuáles son más relevantes. Transformers NO usan recurrent layers (A) ni convolutional filters (B) - esas son de arquitecturas anteriores. Pooling (D) es más común en CNNs.

---

### Pregunta 4

Estás desplegando un modelo desde el Model Catalog de Azure AI Foundry. Necesitas una solución pay-per-use sin gestionar infraestructura. ¿Qué tipo de deployment debes elegir?

A) Batch Endpoints  
B) Managed Online Endpoints  
C) Serverless API  
D) On-premises deployment

**Respuesta correcta: C) Serverless API**

**Explicación**: **Serverless API** proporciona deployment pay-per-use sin necesidad de gestionar infraestructura, con escalado automático. Batch Endpoints (A) es para procesamiento por lotes, Managed Online Endpoints (B) requiere configurar compute resources, y On-premises (D) no es una opción en el Model Catalog.

---

### Pregunta 5

¿Cuál es la principal ventaja de la arquitectura transformer sobre las RNNs (Recurrent Neural Networks) para procesamiento de lenguaje?

A) Transformers son más pequeños en tamaño  
B) Transformers pueden procesar en paralelo, siendo más rápidos de entrenar  
C) Transformers solo funcionan con inglés  
D) Transformers no requieren datos de entrenamiento

**Respuesta correcta: B) Transformers pueden procesar en paralelo, siendo más rápidos de entrenar**

**Explicación**: La principal ventaja de **Transformers** es el **procesamiento en paralelo** gracias al attention mechanism, vs RNNs que procesan secuencialmente. Esto hace el entrenamiento mucho más rápido y escalable. Transformers suelen ser más grandes (A es falso), funcionan con múltiples idiomas (C es falso), y SÍ requieren datos (D es falso).

---

### Pregunta 6

En Azure AI Foundry, ¿qué es un "Hub"?

A) Un tipo de modelo de IA  
B) Una colección de recursos compartidos entre proyectos  
C) Un algoritmo de machine learning  
D) Un tipo de deployment endpoint

**Respuesta correcta: B) Una colección de recursos compartidos entre proyectos**

**Explicación**: Un **Hub** en Azure AI Foundry es un nivel organizacional que contiene recursos compartidos (connections, compute, data) que pueden ser usados por múltiples Projects. No es un modelo (A), algoritmo (C), ni endpoint (D).

---

### Pregunta 7

¿Qué modelo del Model Catalog de Azure AI Foundry usarías para transcripción de audio a texto?

A) GPT-4  
B) DALL-E 3  
C) Whisper  
D) Llama 3

**Respuesta correcta: C) Whisper**

**Explicación**: **Whisper** es el modelo de OpenAI específicamente diseñado para speech-to-text (transcripción de audio). GPT-4 (A) es para texto/chat, DALL-E (B) para imágenes, y Llama 3 (D) es un modelo de lenguaje general de Meta.

---

### Pregunta 8

¿Qué arquitectura de transformer usa GPT-5 para generación de texto?

A) Encoder-only  
B) Decoder-only  
C) Encoder-Decoder  
D) Convolutional

**Respuesta correcta: B) Decoder-only**

**Explicación**: GPT (Generative Pre-trained Transformer) usa arquitectura **decoder-only** que es autoregresiva - genera texto token por token mirando solo hacia atrás. Encoder-only (A) es usado por BERT para comprensión, Encoder-Decoder (C) por modelos como T5, y Convolutional (D) no es una arquitectura transformer.

---

### Pregunta 9

En el Model Catalog, ves que un modelo tiene licencia "MIT". ¿Qué significa esto?

A) El modelo es propietario y requiere pago  
B) El modelo es open source y puede usarse libremente con atribución  
C) El modelo solo funciona en Microsoft Azure  
D) El modelo está restringido solo para educación

**Respuesta correcta: B) El modelo es open source y puede usarse libremente con atribución**

**Explicación**: **Licencia MIT** es una licencia open source muy permisiva que permite uso comercial y modificación con mínimas restricciones (principalmente atribución). No requiere pago (A es falso), funciona en cualquier plataforma (C es falso), y no está restringido a educación (D es falso).

---

### Pregunta 10

¿Qué característica de transformers les permite capturar relaciones entre palabras que están lejos unas de otras en una oración?

A) Recurrent connections  
B) Self-attention mechanism  
C) Convolutional windows  
D) Pooling layers

**Respuesta correcta: B) Self-attention mechanism**

**Explicación**: **Self-attention** permite que cada palabra "atienda" a todas las demás palabras en la secuencia, capturando dependencias de largo alcance sin importar la distancia. RNNs con recurrent connections (A) tienen dificultad con dependencias largas, y CNNs (C, D) tienen ventanas locales limitadas.

---

## 📚 Recursos Adicionales

- [Azure AI Foundry Documentation](https://learn.microsoft.com/azure/ai-foundry/)
- [Model Catalog Overview](https://learn.microsoft.com/azure/ai-foundry/how-to/model-catalog)
- [Transformer Architecture Explained](https://arxiv.org/abs/1706.03762) (Paper original)
- [Attention is All You Need - Paper](https://proceedings.neurips.cc/paper/2017/file/3f5ee243547dee91fbd053c1c4a845aa-Paper.pdf)

---

## 🎓 Resumen Final

### Lo NUEVO en AI-900 (Mayo 2025)

1. ✅ **Azure AI Foundry** reemplaza terminología de Azure AI Studio
2. ✅ **Model Catalog** es testable - conoce los tipos de modelos
3. ✅ **Arquitectura Transformer** es un nuevo tema - entiende conceptos básicos
4. ✅ **IA Generativa tiene el mayor peso** del examen (20-25%)

### Preparación Final

- [ ] Revisa estos temas complementarios
- [ ] Practica preguntas sobre Azure AI Foundry
- [ ] Entiende attention mechanism a nivel conceptual
- [ ] Familiarízate con términos del Model Catalog
- [ ] Conoce la diferencia entre deployment types

---

**¡Con este contenido complementario estás 100% cubierto para el examen actualizado!** 🚀
