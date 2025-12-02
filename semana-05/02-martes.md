# AI-900 Certification - Semana 5, Día 2

## Azure OpenAI Service

**Fecha:** Martes, Semana 5  
**Duración estimada:** 45-60 minutos  
**Nivel:** Fundamental

---

## 📋 Objetivos del día

- Comprender qué es Azure OpenAI Service y sus capacidades
- Conocer los modelos disponibles en Azure OpenAI
- Entender cómo implementar y usar Azure OpenAI Service
- Aprender sobre Azure OpenAI Studio
- Conocer casos de uso empresariales

---

## 1. ¿Qué es Azure OpenAI Service?

### Definición

**Azure OpenAI Service** es un servicio de Azure que proporciona acceso REST API a los modelos de lenguaje avanzados de OpenAI, incluyendo:
- GPT-4 y GPT-3.5
- Embeddings
- DALL-E (generación de imágenes)
- Whisper (speech-to-text)

### Diferencia clave: OpenAI vs Azure OpenAI

| Aspecto | OpenAI (openai.com) | Azure OpenAI Service |
|---------|---------------------|----------------------|
| **Hosting** | Servidores de OpenAI | Infraestructura de Azure |
| **Seguridad** | Estándares de OpenAI | Seguridad empresarial de Azure |
| **Integración** | API independiente | Integrado con servicios Azure |
| **Cumplimiento** | Básico | GDPR, HIPAA, ISO, SOC |
| **SLA** | No garantizado | 99.9% disponibilidad |
| **Redes privadas** | No disponible | Virtual Network, Private Link |
| **Identidad** | API keys | Azure AD, Managed Identity |
| **Región de datos** | Global | Control de región específica |

### Ventajas de Azure OpenAI

✅ **Seguridad empresarial**: Datos no se usan para reentrenar modelos  
✅ **Cumplimiento**: Certificaciones empresariales y de salud  
✅ **Control de red**: Endpoints privados, firewall  
✅ **Integración nativa**: Con servicios Azure (Storage, Cognitive Search, etc.)  
✅ **Content filtering**: Filtros de contenido incorporados  
✅ **Soporte empresarial**: SLA y soporte técnico de Microsoft  

---

## 2. Modelos Disponibles en Azure OpenAI

### GPT-4 (Generative Pre-trained Transformer 4)

**Características:**
- Modelo más avanzado de OpenAI
- Mejor razonamiento y comprensión
- Capacidad multimodal (texto + imágenes en algunas versiones)
- Context window: hasta 128K tokens

**Casos de uso:**
- Análisis complejo de documentos
- Generación de código avanzado
- Razonamiento lógico
- Tareas que requieren máxima precisión

**Versiones comunes:**
- `gpt-4` (8K context)
- `gpt-4-32k` (32K context)
- `gpt-4-turbo` (128K context)

### GPT-3.5-Turbo

**Características:**
- Versión optimizada de GPT-3.5
- Más rápido y económico que GPT-4
- Excelente para la mayoría de tareas
- Context window: 4K-16K tokens

**Casos de uso:**
- Chatbots conversacionales
- Resumen de textos
- Traducción
- Clasificación de texto
- Q&A básico

**Versiones comunes:**
- `gpt-35-turbo` (4K context)
- `gpt-35-turbo-16k` (16K context)

### Embeddings

**Modelos:**
- `text-embedding-ada-002`
- `text-embedding-3-small`
- `text-embedding-3-large`

**Propósito:**
Convertir texto en vectores numéricos que representan significado semántico

**Casos de uso:**
- Búsqueda semántica
- Sistemas de recomendación
- Clustering de documentos
- Detección de similitud
- RAG (Retrieval-Augmented Generation)

### DALL-E

**Versiones:**
- `dall-e-2`
- `dall-e-3`

**Capacidades:**
- Generación de imágenes desde texto
- Edición de imágenes existentes
- Variaciones de imágenes
- Inpainting (rellenar partes faltantes)

**Casos de uso:**
- Creación de contenido visual
- Prototipos de diseño
- Marketing y publicidad
- Arte generativo

### Whisper

**Propósito:** Transcripción de audio a texto (speech-to-text)

**Capacidades:**
- Transcripción en múltiples idiomas
- Traducción automática a inglés
- Alta precisión en ambientes ruidosos

**Casos de uso:**
- Transcripción de reuniones
- Subtítulos automáticos
- Análisis de llamadas de servicio al cliente

---

## 3. Arquitectura y Componentes

### Jerarquía de Recursos

```
Suscripción de Azure
    └── Resource Group
        └── Azure OpenAI Resource
            └── Deployments (Modelos desplegados)
                ├── gpt-4-deployment
                ├── gpt-35-turbo-deployment
                └── embeddings-deployment
```

### Componentes Clave

#### 1. Azure OpenAI Resource
- Recurso principal en Azure Portal
- Contiene endpoint y keys
- Define región y configuración de red
- Maneja facturación

#### 2. Deployment (Implementación)
- Una instancia específica de un modelo
- Puedes tener múltiples deployments del mismo modelo
- Cada deployment tiene:
  - Nombre único
  - Modelo base
  - Capacidad (TPM - Tokens Per Minute)

**Ejemplo:**
```
Modelo: gpt-4
Deployment name: "gpt4-production"
Capacity: 10K TPM
```

#### 3. Endpoint
URL base para hacer llamadas API

**Formato:**
```
https://{resource-name}.openai.azure.com/
```

#### 4. API Keys
- Key 1 (Primary)
- Key 2 (Secondary)
- Puedes regenerar keys sin afectar la otra

---

## 4. Azure OpenAI Studio

### ¿Qué es?

**Azure OpenAI Studio** es una interfaz web para:
- Explorar modelos disponibles
- Crear y probar deployments
- Experimentar con prompts (Playground)
- Ver uso y métricas
- Gestionar content filters

### Secciones principales

#### 1. Deployments
- Crear nuevos deployments
- Ver deployments existentes
- Gestionar capacidad (TPM)
- Eliminar deployments

#### 2. Playground

**Chat Playground:**
- Interfaz tipo chatbot
- Configurar system message
- Ajustar parámetros (temperature, max tokens)
- Probar conversaciones
- Ver código de ejemplo (Python, C#, curl)

**Completions Playground:**
- Modo de completación de texto
- Útil para tareas específicas
- Menos conversacional

**DALL-E Playground:**
- Generar imágenes desde prompts
- Editar imágenes
- Crear variaciones

#### 3. Content Filters
- Configurar niveles de filtrado
- Detectar contenido dañino
- Personalizar políticas de contenido

#### 4. Data & Monitoring
- Ver uso de tokens
- Métricas de rendimiento
- Costos por deployment
- Logs de llamadas API

---

## 5. Uso de la API

### Estructura básica de una llamada API

#### Endpoint
```
POST https://{resource-name}.openai.azure.com/openai/deployments/{deployment-name}/chat/completions?api-version=2024-02-15-preview
```

#### Headers
```
Content-Type: application/json
api-key: {your-api-key}
```

#### Body (Request)
```json
{
  "messages": [
    {
      "role": "system",
      "content": "Eres un asistente útil que responde preguntas sobre Azure."
    },
    {
      "role": "user",
      "content": "¿Qué es Azure OpenAI Service?"
    }
  ],
  "max_tokens": 800,
  "temperature": 0.7,
  "top_p": 0.95
}
```

#### Response
```json
{
  "choices": [
    {
      "message": {
        "role": "assistant",
        "content": "Azure OpenAI Service es un servicio de Azure que proporciona acceso..."
      },
      "finish_reason": "stop",
      "index": 0
    }
  ],
  "usage": {
    "prompt_tokens": 25,
    "completion_tokens": 150,
    "total_tokens": 175
  }
}
```

### Roles en mensajes

- **system**: Instrucciones de comportamiento general del asistente
- **user**: Mensajes del usuario
- **assistant**: Respuestas previas del modelo (para contexto)

### Parámetros importantes

| Parámetro | Descripción | Rango | Uso típico |
|-----------|-------------|-------|------------|
| **temperature** | Controla aleatoriedad | 0.0 - 2.0 | 0.7 para general, 0.2 para técnico |
| **max_tokens** | Máximo de tokens en respuesta | 1 - límite modelo | 800-1000 típico |
| **top_p** | Nucleus sampling | 0.0 - 1.0 | 0.95 típico |
| **frequency_penalty** | Penaliza repetición | -2.0 - 2.0 | 0.0 - 0.5 |
| **presence_penalty** | Penaliza temas repetidos | -2.0 - 2.0 | 0.0 - 0.5 |

---

## 6. Casos de Uso Empresariales

### 1. Servicio al Cliente Inteligente

**Escenario:** Chatbot que responde preguntas sobre productos/servicios

**Implementación:**
- Usar GPT-3.5-turbo para respuestas rápidas
- System message con información de la empresa
- Integrar con Azure Cognitive Search para buscar documentación
- Content filters para prevenir respuestas inapropiadas

### 2. Análisis de Documentos

**Escenario:** Extraer insights de contratos, reportes financieros

**Implementación:**
- GPT-4 para análisis complejo
- Embeddings para encontrar secciones relevantes
- Resumen automático de puntos clave
- Extracción de entidades (fechas, montos, nombres)

### 3. Generación de Código

**Escenario:** Asistente de programación para desarrolladores

**Implementación:**
- GPT-4 para generación de código
- Explicación de código existente
- Debugging y sugerencias de mejora
- Documentación automática

### 4. Content Marketing

**Escenario:** Crear contenido para blogs, redes sociales

**Implementación:**
- GPT-3.5/GPT-4 para generación de texto
- DALL-E para imágenes
- Adaptación de tono según audiencia
- SEO optimization

### 5. Análisis de Sentimiento y Feedback

**Escenario:** Analizar reviews de clientes a escala

**Implementación:**
- Clasificación de sentimiento
- Extracción de temas principales
- Resumen de feedback común
- Identificación de issues críticos

---

## 7. Seguridad y Best Practices

### Autenticación

**Opción 1: API Keys**
- Fácil de implementar
- Regenerar keys periódicamente
- No incluir en código fuente
- Usar Azure Key Vault

**Opción 2: Azure AD (Recomendado)**
- Autenticación basada en tokens
- Integración con identidades corporativas
- Mejor auditoría y control
- Revocación granular

**Opción 3: Managed Identity**
- Para servicios Azure-to-Azure
- Sin gestión de credenciales
- Más seguro

### Protección de Datos

✅ **Residencia de datos**: Los datos permanecen en la región Azure seleccionada  
✅ **No se usa para entrenamiento**: Tus datos NO se usan para reentrenar modelos  
✅ **Encriptación**: En tránsito (TLS) y en reposo  
✅ **Private endpoints**: Tráfico no sale de la red Azure  

### Límites y Cuotas

**TPM (Tokens Per Minute):**
- Define cuántos tokens puedes procesar por minuto
- Se configura por deployment
- Ejemplo: 10K TPM = 10,000 tokens/minuto

**Rate Limiting:**
- Si excedes TPM, recibes error 429
- Implementar retry con backoff exponencial
- Distribuir carga entre múltiples deployments si es necesario

### Content Filtering

**Niveles de filtrado:**
- **Low**: Bloquea solo contenido muy explícito
- **Medium**: Balance entre seguridad y usabilidad
- **High**: Filtrado estricto

**Categorías detectadas:**
- Violence (Violencia)
- Hate (Odio)
- Sexual (Contenido sexual)
- Self-harm (Auto-daño)

---

## 8. Costos y Facturación

### Modelo de Precios

**Pay-per-use (Pago por uso):**
- Se cobra por tokens procesados
- Separado: prompt tokens + completion tokens
- Varía según modelo

**Ejemplos aproximados (precios referenciales):**
- GPT-4: ~$0.03/1K prompt tokens, ~$0.06/1K completion tokens
- GPT-3.5-turbo: ~$0.0015/1K prompt tokens, ~$0.002/1K completion tokens
- Embeddings: ~$0.0001/1K tokens

### Optimización de Costos

1. **Usar el modelo apropiado**: GPT-3.5 cuando GPT-4 no sea necesario
2. **Limitar max_tokens**: No generar más de lo necesario
3. **Cachear respuestas**: Para preguntas frecuentes
4. **Resumir contexto**: Mantener conversaciones más cortas
5. **Batch processing**: Agrupar solicitudes cuando sea posible

---

## ✅ Puntos Clave para el Examen

- Azure OpenAI Service proporciona acceso a modelos OpenAI con seguridad empresarial de Azure
- Modelos principales: GPT-4, GPT-3.5-turbo, Embeddings, DALL-E, Whisper
- **Deployment** = instancia específica de un modelo con nombre y capacidad
- Azure OpenAI Studio = interfaz web para gestionar y probar modelos
- **TPM (Tokens Per Minute)** define la capacidad del deployment
- Autenticación: API keys, Azure AD, o Managed Identity
- Content filters detectan y bloquean contenido dañino
- Los datos del cliente NO se usan para reentrenar modelos
- Facturación por tokens procesados (prompt + completion)
- System message define el comportamiento general del asistente

---

## 🎯 Preguntas Estilo Examen Microsoft AI-900

### Pregunta 1
Tu empresa quiere usar modelos GPT para un chatbot de servicio al cliente, pero requiere que los datos permanezcan en Europa por GDPR. ¿Qué servicio deberías usar?

A) OpenAI API directamente (openai.com)  
B) Azure OpenAI Service desplegado en región de Europa  
C) Azure AI Language Service  
D) Azure Bot Service sin modelos de lenguaje

**Respuesta correcta: B) Azure OpenAI Service desplegado en región de Europa**

**Explicación**: Azure OpenAI Service permite seleccionar la región de Azure donde se despliega el recurso, asegurando que los datos permanezcan en esa geografía (ej: West Europe, North Europe). Esto cumple con GDPR. OpenAI API directa (A) no ofrece este control de región. Azure AI Language (C) no proporciona acceso a modelos GPT. Azure Bot Service (D) necesita un backend de lenguaje.

---

### Pregunta 2
En Azure OpenAI Studio, estás configurando un chatbot. Quieres que el asistente siempre responda como un experto en finanzas. ¿Qué rol de mensaje deberías usar para esto?

A) user  
B) assistant  
C) system  
D) function

**Respuesta correcta: C) system**

**Explicación**: El mensaje de rol **system** define el comportamiento general y la personalidad del asistente. Es perfecto para instrucciones como "Eres un experto en finanzas". El rol **user** es para mensajes del usuario, **assistant** para respuestas previas del modelo (contexto), y **function** es para llamadas a funciones externas.

---

### Pregunta 3
Estás desplegando GPT-4 en Azure OpenAI. Configuras el deployment con 10K TPM. ¿Qué significa TPM?

A) Transactions Per Month (Transacciones por Mes)  
B) Tokens Per Minute (Tokens Por Minuto)  
C) Total Processing Memory (Memoria Total de Procesamiento)  
D) Time Per Message (Tiempo Por Mensaje)

**Respuesta correcta: B) Tokens Per Minute (Tokens Por Minuto)**

**Explicación**: **TPM (Tokens Per Minute)** es la capacidad asignada a un deployment que define cuántos tokens puede procesar por minuto. 10K TPM significa que puede procesar 10,000 tokens cada minuto. Si excedes este límite, recibirás un error 429 (rate limit). Esta métrica es fundamental para planificar capacidad y costos.

---

### Pregunta 4
¿Cuál de las siguientes es una ventaja de Azure OpenAI Service sobre usar OpenAI API directamente?

A) Modelos más avanzados no disponibles en OpenAI  
B) Acceso gratuito ilimitado  
C) Integración nativa con Azure AD y Managed Identity  
D) No requiere ningún tipo de autenticación

**Respuesta correcta: C) Integración nativa con Azure AD y Managed Identity**

**Explicación**: Azure OpenAI Service se integra con la infraestructura de seguridad de Azure, incluyendo Azure AD y Managed Identity, proporcionando mejor seguridad y control que solo API keys. Los modelos son los mismos que OpenAI (A es falso), no es gratis (B es falso), y SÍ requiere autenticación (D es falso). Otras ventajas incluyen SLA empresarial, cumplimiento regulatorio, y private endpoints.

---

### Pregunta 5
Estás usando Azure OpenAI para generar respuestas de un chatbot médico. Necesitas que las respuestas sean muy consistentes y predecibles, evitando variaciones creativas. ¿Qué configuración deberías usar?

A) Temperature = 0.0, Top_p = 0.1  
B) Temperature = 1.5, Top_p = 1.0  
C) Temperature = 2.0, Top_p = 0.5  
D) Frequency_penalty = 2.0, Presence_penalty = 2.0

**Respuesta correcta: A) Temperature = 0.0, Top_p = 0.1**

**Explicación**: Para respuestas **consistentes y predecibles**, necesitas valores **bajos** de temperature y top_p. Temperature = 0.0 hace que el modelo siempre seleccione la opción más probable (determinista). Top_p = 0.1 limita las opciones consideradas. Las opciones B y C tienen valores altos que generan respuestas creativas y variadas (inadecuado para información médica). La opción D penaliza repetición pero no controla consistencia.

---

## 📖 Recursos Adicionales

- [Azure OpenAI Service Documentation](https://learn.microsoft.com/azure/cognitive-services/openai/)
- [Azure OpenAI Studio](https://oai.azure.com/)
- [OpenAI Models Documentation](https://platform.openai.com/docs/models)
- [Best Practices for Azure OpenAI](https://learn.microsoft.com/azure/cognitive-services/openai/how-to/best-practices)
