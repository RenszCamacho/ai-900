# AI-900 Certification - Semana 5, Día 1

## Azure AI Services Overview & Responsible AI Principles

**Fecha:** Lunes, Semana 5  
**Duración estimada:** 45-60 minutos  
**Nivel:** Fundamental

---

## 📋 Objetivos del día

- Comprender la arquitectura general de Azure AI Services
- Conocer los principios de IA Responsable de Microsoft
- Entender consideraciones de seguridad y gobernanza en AI

---

## 1. Azure AI Services: Visión General

### ¿Qué son Azure AI Services?

Azure AI Services es una colección de servicios de IA preentrenados que puedes usar mediante APIs REST. Anteriormente conocidos como "Cognitive Services", ahora incluyen:

- **Azure OpenAI Service** - Acceso a modelos GPT, Codex, DALL-E
- **Azure AI Vision** - Computer Vision, Custom Vision, Face API
- **Azure AI Language** - Text Analytics, QnA Maker, LUIS, Translator
- **Azure AI Speech** - Speech-to-Text, Text-to-Speech, Translation
- **Azure AI Decision** - Anomaly Detector, Personalizer, Content Moderator

### Características clave

- **Pre-entrenados**: No necesitas entrenar modelos desde cero
- **API-first**: Integración simple mediante REST APIs
- **Multi-región**: Disponibilidad global
- **Escalable**: Ajusta recursos según demanda
- **Seguro**: Autenticación con claves o Azure AD

---

## 2. Creación y Gestión de Recursos

### Dos tipos de recursos

#### a) Multi-service resource (Recomendado para desarrollo)
- Un solo endpoint para múltiples servicios
- Una sola clave de acceso
- Facturación consolidada
- Nombre: "Azure AI services" en el portal

#### b) Single-service resource
- Recurso dedicado para un servicio específico
- Útil para producción con necesidades específicas
- Ejemplo: Solo "Computer Vision" o solo "Text Analytics"

### Información importante para el recurso

- **Endpoint**: URL base para llamadas API  
  Ejemplo: `https://myresource.cognitiveservices.azure.com/`
- **Keys**: Clave primaria y secundaria para autenticación
- **Location/Region**: Región de Azure donde se despliega
- **Pricing tier**: Free (F0) o Standard (S0, S1, etc.)

---

## 3. Principios de IA Responsable de Microsoft

Microsoft define **6 principios fundamentales** para el desarrollo de IA:

### 1. Fairness (Equidad)
- Los sistemas de IA deben tratar a todas las personas de manera justa
- Evitar sesgos basados en género, etnia, edad, etc.
- **Ejemplo**: Un modelo de contratación no debe favorecer un género sobre otro

### 2. Reliability & Safety (Confiabilidad y Seguridad)
- Los sistemas deben funcionar de manera confiable y segura
- Manejar errores apropiadamente
- **Ejemplo**: Un vehículo autónomo debe detectar y responder a situaciones inesperadas

### 3. Privacy & Security (Privacidad y Seguridad)
- Proteger datos personales y mantener confidencialidad
- Cumplir con regulaciones (GDPR, etc.)
- **Ejemplo**: Un chatbot médico debe encriptar información de salud

### 4. Inclusiveness (Inclusividad)
- Los sistemas deben beneficiar a todos, incluyendo personas con discapacidades
- Diseño accesible
- **Ejemplo**: Reconocimiento de voz que funcione con diferentes acentos

### 5. Transparency (Transparencia)
- Los usuarios deben entender cómo funciona el sistema de IA
- Explicar limitaciones y propósito
- **Ejemplo**: Divulgar cuando interactúan con un bot vs. una persona

### 6. Accountability (Responsabilidad)
- Las personas deben ser responsables de los sistemas de IA
- Gobernanza y supervisión humana
- **Ejemplo**: Revisión humana en decisiones críticas (préstamos, diagnósticos)

---

## 4. Consideraciones Prácticas de IA Responsable

### Identificación de Sesgos

- **Datos de entrenamiento**: ¿Son representativos?
- **Etiquetado**: ¿Hay prejuicios en las etiquetas?
- **Métricas**: Evaluar rendimiento por grupos demográficos

### Transparencia en Azure AI

- **Transparency Notes**: Documentación de cada servicio explicando casos de uso, limitaciones
- **Disclosure**: Indicar a usuarios cuando interactúan con IA
- **Explainability**: Entender por qué un modelo toma ciertas decisiones

### Herramientas de Microsoft

- **Fairlearn**: Evaluar y mitigar sesgos en modelos ML
- **InterpretML**: Explicar predicciones de modelos
- **Error Analysis**: Identificar dónde fallan los modelos

---

## 5. Seguridad y Gobernanza

### Autenticación y Autorización

- **Subscription keys**: Claves de suscripción (primaria/secundaria)
- **Azure Active Directory**: Autenticación más segura con tokens
- **Managed Identity**: Permite que servicios de Azure accedan sin credenciales explícitas

### Content Safety

**Azure AI Content Safety**: Detecta contenido inapropiado
- Violencia
- Odio
- Contenido sexual
- Auto-daño

### Cumplimiento

- **GDPR**: Protección de datos en Europa
- **HIPAA**: Estándares de salud en US
- **ISO 27001**: Estándares de seguridad de información

### Monitoreo

- **Azure Monitor**: Rastrear uso, rendimiento, errores
- **Application Insights**: Telemetría detallada
- **Logs**: Auditoría de accesos y operaciones

---

## 6. Escenario Práctico

### Caso: Sistema de Contratación con IA

Una empresa quiere usar IA para filtrar CVs y recomendar candidatos.

**Aplicación de Principios:**

1. **Fairness**: Entrenar con CVs diversos, probar para sesgos de género/edad
2. **Reliability**: Sistema de respaldo si la IA falla, no rechazar automáticamente
3. **Privacy**: Encriptar datos personales, cumplir GDPR
4. **Inclusiveness**: Considerar formatos alternativos de CV (accesibilidad)
5. **Transparency**: Informar a candidatos que hay IA en el proceso, explicar criterios
6. **Accountability**: Revisión humana final, RRHH responsable de decisiones

---

## ✅ Puntos Clave para el Examen

- Azure AI Services son servicios pre-entrenados accesibles vía API
- Multi-service resource = un recurso para múltiples servicios
- Los 6 principios de IA Responsable: Fairness, Reliability, Privacy, Inclusiveness, Transparency, Accountability
- Transparency Notes explican limitaciones y casos de uso
- Content Safety detecta contenido inapropiado
- Autenticación con subscription keys o Azure AD
- Managed Identity permite acceso seguro sin credenciales explícitas

---

## 🎯 Preguntas Estilo Examen Microsoft AI-900

### Pregunta 1
Estás desarrollando una aplicación que usa Azure AI Services. Quieres usar un solo recurso para acceder tanto a Computer Vision como a Text Analytics. ¿Qué tipo de recurso debes crear?

A) Computer Vision resource  
B) Text Analytics resource  
C) Azure AI services resource  
D) Custom Vision resource

**Respuesta correcta: C) Azure AI services resource**

**Explicación**: El recurso "Azure AI services" (multi-service) te permite acceder a múltiples servicios con un solo endpoint y una sola clave, perfecto cuando necesitas Computer Vision y Text Analytics juntos. Las opciones A y B son recursos single-service.

---

### Pregunta 2
Tu organización está implementando un sistema de IA para aprobación de préstamos. ¿Cuál de los siguientes principios de IA Responsable requiere que los solicitantes puedan entender por qué se aprobó o rechazó su préstamo?

A) Fairness  
B) Transparency  
C) Privacy & Security  
D) Inclusiveness

**Respuesta correcta: B) Transparency**

**Explicación**: Transparency (Transparencia) implica que los usuarios deben entender cómo funciona el sistema de IA y por qué toma ciertas decisiones. En este caso, explicar el motivo de aprobación/rechazo es transparencia. Fairness se enfoca en trato equitativo, Privacy en protección de datos, e Inclusiveness en accesibilidad para todos.

---

### Pregunta 3
Estás usando Azure AI services en tu aplicación. ¿Cuál de las siguientes es la forma MÁS segura de autenticación?

A) Incluir la subscription key directamente en el código  
B) Usar Azure Active Directory (Azure AD)  
C) Compartir la subscription key entre múltiples aplicaciones  
D) Guardar la subscription key en un archivo de texto

**Respuesta correcta: B) Usar Azure Active Directory (Azure AD)**

**Explicación**: Azure AD proporciona autenticación basada en tokens con capacidades de revocación, auditoría y control de acceso granular. Las subscription keys son menos seguras porque si se comprometen, tienes que regenerarlas. Nunca debes incluir keys en código o compartirlas indiscriminadamente (opciones A, C, D son malas prácticas).

---

### Pregunta 4
Una empresa de salud está desarrollando un chatbot para pacientes. El chatbot debe detectar si los usuarios comparten contenido relacionado con auto-daño para escalar a un profesional humano. ¿Qué servicio de Azure AI deberían usar?

A) Azure AI Language - Sentiment Analysis  
B) Azure AI Content Safety  
C) Azure AI Speech  
D) Azure OpenAI Service

**Respuesta correcta: B) Azure AI Content Safety**

**Explicación**: Azure AI Content Safety está específicamente diseñado para detectar contenido dañino, incluyendo auto-daño, violencia, odio, etc. Aunque Sentiment Analysis (A) puede detectar emociones negativas, no está diseñado específicamente para identificar contenido peligroso que requiere moderación.

---

### Pregunta 5
Tu equipo está entrenando un modelo de reconocimiento facial para un sistema de asistencia. Durante las pruebas, descubren que el modelo tiene menor precisión al identificar personas de ciertos grupos étnicos. ¿Qué principio de IA Responsable se está violando?

A) Accountability  
B) Reliability & Safety  
C) Fairness  
D) Transparency

**Respuesta correcta: C) Fairness**

**Explicación**: Fairness (Equidad) requiere que los sistemas de IA traten a todas las personas de manera justa, sin sesgos basados en características como etnia, género, edad, etc. Un modelo con menor precisión para ciertos grupos étnicos muestra sesgo y viola el principio de fairness. La solución sería entrenar con datos más diversos y equilibrados.

---

## 📚 Tarea para mañana

Mañana continuaremos con **Azure Machine Learning fundamentals** - workspace, compute, datasets y automated ML.

---

## 📖 Recursos Adicionales

- [Microsoft Learn - AI-900 Learning Path](https://docs.microsoft.com/learn/certifications/exams/ai-900)
- [Azure AI Services Documentation](https://docs.microsoft.com/azure/cognitive-services/)
- [Responsible AI Resources](https://www.microsoft.com/ai/responsible-ai)
- [Transparency Notes](https://docs.microsoft.com/azure/cognitive-services/transparency-note)

---

**Preparado por:** Claude AI  
**Para:** Renszo - Preparación AI-900  
**Semana:** 5 de 6  
**Próximo tema:** Azure Machine Learning Fundamentals
