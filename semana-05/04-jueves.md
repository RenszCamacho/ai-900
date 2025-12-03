# AI-900 Certification - Semana 5, Día 4

## Responsible AI (IA Responsable) ⭐

**Fecha:** Jueves, Semana 5  
**Duración estimada:** 60-75 minutos  
**Nivel:** Fundamental

---

## 📋 Objetivos del día

- Dominar los 6 principios de IA Responsable de Microsoft
- Comprender cómo aplicar cada principio en escenarios reales
- Conocer herramientas y prácticas para implementar IA Responsable
- Entender consideraciones éticas en el desarrollo de IA
- Identificar y mitigar sesgos en sistemas de IA

---

## 1. Los 6 Principios de IA Responsable de Microsoft

Microsoft ha establecido **6 principios fundamentales** que guían el desarrollo y despliegue de sistemas de IA. Estos principios son críticos para el examen AI-900.

---

### 1️⃣ Fairness (Equidad)

#### Definición
Los sistemas de IA deben tratar a todas las personas de manera justa, sin discriminar basándose en características como género, etnia, edad, discapacidad, orientación sexual u otras.

#### Objetivo
Evitar sesgos que puedan resultar en tratamiento injusto o discriminatorio.

#### Ejemplos de violaciones de Fairness

**❌ Problema:**
- Sistema de contratación que favorece candidatos masculinos
- Modelo de aprobación de crédito con tasas más altas para ciertos grupos étnicos
- Reconocimiento facial con menor precisión en personas de piel oscura
- Software de traducción que asume género masculino por defecto en profesiones

**✅ Aplicación correcta:**
- Entrenar con datasets balanceados y diversos
- Evaluar rendimiento del modelo por grupos demográficos
- Implementar métricas de fairness
- Auditar regularmente para detectar sesgos emergentes

#### Herramientas de Microsoft

**Fairlearn:**
- Biblioteca Python para evaluar y mitigar sesgos
- Permite comparar rendimiento entre grupos
- Ofrece algoritmos de mitigación

**Ejemplo de uso:**
```python
# Evaluar disparidad en predicciones
from fairlearn.metrics import MetricFrame
from sklearn.metrics import accuracy_score

# Analizar precisión por grupo sensible
mf = MetricFrame(
    metrics=accuracy_score,
    y_true=y_test,
    y_pred=predictions,
    sensitive_features=gender
)

print(mf.by_group)  # Muestra accuracy por género
```

#### Casos de estudio

**Caso 1: Sistema de Reclutamiento**
- **Escenario:** Empresa usa IA para filtrar CVs
- **Problema detectado:** Modelo rechaza 70% de candidatas mujeres vs 30% hombres
- **Causa:** Entrenado con CVs históricos cuando había menos mujeres en tech
- **Solución:** Reentrenar con dataset balanceado, remover características sesgadas, validar con métricas de fairness

**Caso 2: Reconocimiento Facial**
- **Escenario:** Sistema de asistencia laboral con face recognition
- **Problema detectado:** 15% error en personas asiáticas vs 3% en personas blancas
- **Causa:** Dataset de entrenamiento principalmente con rostros caucásicos
- **Solución:** Ampliar dataset con diversidad étnica, reentrenar, establecer umbrales de precisión mínima

---

### 2️⃣ Reliability & Safety (Confiabilidad y Seguridad)

#### Definición
Los sistemas de IA deben funcionar de manera confiable y segura bajo todas las condiciones esperadas, manejando errores apropiadamente.

#### Objetivo
Garantizar que los sistemas de IA operen consistentemente y no causen daño.

#### Ejemplos de aplicación

**✅ Buenas prácticas:**

**1. Manejo robusto de errores:**
```python
try:
    result = ai_model.predict(user_input)
    if confidence_score < 0.7:
        return "No estoy seguro, consulta con un humano"
except Exception as e:
    log_error(e)
    return fallback_response()
```

**2. Validación de entrada:**
- Verificar que los datos de entrada sean válidos
- Rechazar inputs fuera de distribución
- Implementar rate limiting

**3. Monitoreo continuo:**
- Tracking de precisión en producción
- Alertas cuando el rendimiento cae
- A/B testing de nuevas versiones

**4. Fallbacks y redundancia:**
- Sistema de respaldo si la IA falla
- Intervención humana para casos críticos
- Graceful degradation

#### Casos críticos donde la reliability es vital

**Vehículos autónomos:**
- Debe detectar obstáculos en todas las condiciones (lluvia, nieve, noche)
- Respuesta apropiada ante situaciones inesperadas
- Modo seguro de fallo (safe mode)

**Diagnóstico médico:**
- Alta precisión requerida (vidas en juego)
- Explicación clara de incertidumbre
- Revisión médica obligatoria

**Sistemas financieros:**
- Detección de fraude confiable
- Sin falsos positivos excesivos
- Auditoría completa de decisiones

#### Testing para Reliability

**Tipos de testing:**
1. **Unit tests**: Funciones individuales
2. **Integration tests**: Componentes integrados
3. **Stress tests**: Carga extrema
4. **Adversarial tests**: Inputs maliciosos
5. **Edge case tests**: Casos límite

---

### 3️⃣ Privacy & Security (Privacidad y Seguridad)

#### Definición
Los sistemas de IA deben proteger datos personales y mantener la confidencialidad, cumpliendo con regulaciones de privacidad.

#### Objetivo
Salvaguardar información sensible y prevenir acceso no autorizado.

#### Principios clave

**1. Minimización de datos:**
- Recolectar solo lo necesario
- No almacenar más de lo requerido
- Eliminar datos cuando ya no se necesiten

**2. Encriptación:**
- Datos en tránsito (TLS/SSL)
- Datos en reposo (AES-256)
- Claves gestionadas adecuadamente

**3. Control de acceso:**
- Autenticación robusta (MFA)
- Autorización basada en roles (RBAC)
- Principio de mínimo privilegio

**4. Anonimización:**
- Remover identificadores personales
- Agregación de datos
- Técnicas de differential privacy

#### Cumplimiento regulatorio

**GDPR (Europa):**
- Derecho a ser olvidado
- Consentimiento explícito
- Portabilidad de datos
- Notificación de brechas (72 horas)

**HIPAA (EE.UU. - Salud):**
- Protección de información médica
- Controles de acceso estrictos
- Auditoría completa

**CCPA (California):**
- Derecho a saber qué datos se recolectan
- Derecho a eliminación
- Opt-out de venta de datos

#### Implementación en Azure OpenAI

**✅ Prácticas en Azure:**
- Datos NO se usan para reentrenar modelos
- Residencia de datos por región
- Private endpoints (tráfico no sale de Azure)
- Managed Identity (sin credenciales expuestas)
- Logging y auditoría completa

**Ejemplo de configuración segura:**
```python
# Usar Managed Identity en lugar de API keys
from azure.identity import DefaultAzureCredential

credential = DefaultAzureCredential()
client = OpenAIClient(
    endpoint="https://myresource.openai.azure.com",
    credential=credential
)
```

#### Escenario de examen típico

**Pregunta:** Una empresa de salud desarrolla un chatbot para consultas médicas. ¿Qué principio de IA Responsable requiere que encripten los datos de los pacientes?

**Respuesta:** Privacy & Security

---

### 4️⃣ Inclusiveness (Inclusividad)

#### Definición
Los sistemas de IA deben ser diseñados para beneficiar a todos, incluyendo personas con discapacidades y grupos tradicionalmente marginados.

#### Objetivo
Garantizar que la IA sea accesible y útil para todas las personas, sin importar sus capacidades o circunstancias.

#### Dimensiones de Inclusiveness

**1. Accesibilidad física:**
- Interfaz compatible con lectores de pantalla
- Tamaño de texto ajustable
- Alto contraste para visión reducida
- Entrada por voz para movilidad limitada

**2. Accesibilidad lingüística:**
- Soporte multi-idioma
- Dialectos y variaciones regionales
- Lenguaje simple y claro
- Evitar jerga innecesaria

**3. Accesibilidad cognitiva:**
- Instrucciones claras
- Navegación simple
- Opciones de ayuda
- Feedback comprensible

**4. Inclusión socioeconómica:**
- Funciona con conexiones lentas
- No requiere hardware costoso
- Versión gratuita o de bajo costo
- Diseño para baja alfabetización digital

#### Ejemplos prácticos

**✅ Chatbot inclusivo:**
- Soporta entrada de texto Y voz
- Respuestas en múltiples idiomas
- Compatible con lectores de pantalla
- Funciona en dispositivos antiguos
- Modo de texto simplificado

**✅ Sistema de reconocimiento de voz:**
- Funciona con diferentes acentos
- Adapta a velocidad de habla
- Tolera pausas y repeticiones
- Alternativa de entrada por texto

**❌ Problemas de inclusividad:**
- App solo en inglés (excluye no angloparlantes)
- Solo funciona con cámara de alta resolución (excluye dispositivos económicos)
- Interfaz compleja (excluye adultos mayores o personas con discapacidad cognitiva)
- Requiere interacción táctil precisa (excluye personas con temblores)

#### Herramientas de Microsoft

**Inclusive Design Toolkit:**
- Guías para diseño accesible
- Checklists de inclusividad
- Plantillas y recursos

**Accessibility Insights:**
- Testing automatizado de accesibilidad
- Identifica barreras
- Sugerencias de mejora

#### Caso de estudio

**Caso: Sistema educativo con IA**
- **Objetivo:** Tutor virtual para estudiantes
- **Consideraciones de inclusividad:**
  - Soporte para estudiantes con dislexia (fuentes especiales, síntesis de voz)
  - Estudiantes con déficit auditivo (transcripciones, subtítulos)
  - Estudiantes de bajos recursos (funciona offline, baja conectividad)
  - Múltiples idiomas (comunidades inmigrantes)
  - Adaptación al ritmo de aprendizaje individual

---

### 5️⃣ Transparency (Transparencia)

#### Definición
Los usuarios deben entender cómo funciona el sistema de IA, sus limitaciones, y cuándo están interactuando con IA en lugar de humanos.

#### Objetivo
Construir confianza mediante claridad sobre capacidades, limitaciones y funcionamiento.

#### Elementos de Transparency

**1. Disclosure (Divulgación):**
- Informar que están interactuando con IA
- Explicar qué puede y no puede hacer el sistema
- Ser honesto sobre limitaciones

**Ejemplo:**
```
"Soy un asistente virtual impulsado por IA. 
Puedo ayudarte con: [lista de capacidades]
No puedo: [lista de limitaciones]
Si necesitas ayuda humana, di 'agente humano'"
```

**2. Explainability (Explicabilidad):**
- Por qué el modelo tomó cierta decisión
- Qué factores fueron más importantes
- Nivel de confianza en la predicción

**Ejemplo de sistema de crédito:**
```
Decisión: Préstamo rechazado

Factores principales:
- Ratio deuda/ingresos: 65% (límite: 50%)
- Historial crediticio: 2 pagos tardíos en últimos 6 meses
- Antigüedad laboral: 3 meses (mínimo: 6 meses)

Confianza en decisión: 92%
```

**3. Documentación:**
- Transparency Notes de Microsoft
- Casos de uso apropiados
- Casos de uso NO apropiados
- Precisión esperada
- Datos de entrenamiento

#### Transparency Notes de Microsoft

Para cada servicio de Azure AI, Microsoft publica Transparency Notes que incluyen:

**Estructura típica:**
1. **What is it?** - Qué hace el sistema
2. **What can it do?** - Capacidades
3. **What are its intended uses?** - Usos apropiados
4. **How was it evaluated?** - Testing y validación
5. **What are the limitations?** - Limitaciones conocidas
6. **What operational factors affect quality?** - Factores de rendimiento
7. **How can it be improved?** - Recomendaciones

**Ejemplo - Azure AI Vision Transparency Notes:**
- Precisión varía según calidad de imagen
- Mejor rendimiento en fotos bien iluminadas
- Puede fallar con objetos parcialmente ocultos
- No recomendado para decisiones críticas sin revisión humana

#### Niveles de explicabilidad

**Nivel 1 - Black box:** 
- Input → Output
- Sin explicación

**Nivel 2 - Feature importance:**
- "Edad fue el factor más importante (45%)"
- "Ingresos contribuyó 30%"

**Nivel 3 - Local explanation:**
- "Para ESTE cliente específico, rechazamos porque..."

**Nivel 4 - Counterfactual:**
- "Si sus ingresos fueran $5,000 más altos, habría sido aprobado"

#### Herramientas

**InterpretML:**
- Explica predicciones de modelos
- Visualizaciones de importancia de features
- Compatible con varios tipos de modelos

**SHAP (SHapley Additive exPlanations):**
- Valores de contribución por feature
- Gráficos de dependencia
- Explicaciones globales y locales

#### Escenarios de examen

**Pregunta típica:** "Una empresa usa IA para filtrar candidatos. ¿Qué principio requiere que informen a los candidatos que su CV será revisado por IA?"

**Respuesta:** Transparency

---

### 6️⃣ Accountability (Responsabilidad)

#### Definición
Las personas deben ser responsables de los sistemas de IA. Debe haber supervisión humana y gobiernanza adecuada.

#### Objetivo
Asegurar que siempre haya humanos responsables de las decisiones de IA y sus consecuencias.

#### Elementos de Accountability

**1. Supervisión humana:**
- Human-in-the-loop para decisiones críticas
- Revisión periódica de outputs
- Capacidad de override (anular decisión de IA)

**Ejemplos por nivel de criticidad:**

| Criticidad | Supervisión | Ejemplo |
|------------|-------------|---------|
| Baja | Automática | Sugerencias de productos |
| Media | Muestreo | Moderación de contenido (revisar 10%) |
| Alta | Revisión total | Diagnósticos médicos |
| Crítica | Decisión final humana | Aprobación de cirugías |

**2. Gobernanza:**
- Comité de ética de IA
- Políticas y procedimientos claros
- Revisiones regulares
- Proceso de escalamiento

**Estructura de gobernanza típica:**
```
Board / Directorio
    ↓
Comité de Ética de IA
    ↓
├─ Data Science Team
├─ Legal & Compliance
├─ Security Team
└─ Product Management
```

**3. Auditoría:**
- Logging completo de decisiones
- Trazabilidad (quién, qué, cuándo)
- Auditorías internas y externas
- Reportes de incidentes

**4. Remediación:**
- Proceso para reportar problemas
- Investigación de quejas
- Corrección de errores
- Compensación cuando sea apropiado

#### Implementación práctica

**Ejemplo: Sistema de aprobación de préstamos**

```python
def loan_decision(applicant_data):
    # IA hace recomendación
    ai_recommendation = model.predict(applicant_data)
    confidence = model.predict_proba(applicant_data)
    
    # Log completo
    log_decision(
        applicant_id=applicant_data['id'],
        recommendation=ai_recommendation,
        confidence=confidence,
        timestamp=now(),
        model_version="v2.3"
    )
    
    # Si baja confianza o monto alto → Revisión humana obligatoria
    if confidence < 0.85 or applicant_data['amount'] > 50000:
        return {
            'status': 'PENDING_HUMAN_REVIEW',
            'ai_recommendation': ai_recommendation,
            'reason': 'High risk or low confidence'
        }
    
    # Decisión final con accountability
    return {
        'status': 'APPROVED' if ai_recommendation else 'REJECTED',
        'reviewed_by': 'AI_SYSTEM',
        'reviewable': True,
        'appeal_process': 'contact support'
    }
```

#### Responsabilidades definidas

**Data Scientists:**
- Entrenar modelos sin sesgos
- Documentar limitaciones
- Validar rendimiento

**Product Managers:**
- Definir casos de uso apropiados
- Establecer umbrales de confianza
- Decidir nivel de supervisión humana

**Legal/Compliance:**
- Asegurar cumplimiento regulatorio
- Revisar implicaciones legales
- Gestionar riesgos

**Ejecutivos:**
- Aprobar despliegue de IA
- Asumir responsabilidad final
- Establecer cultura de IA Responsable

#### Escenarios de accountability

**Caso 1: Sistema de moderación de contenido**
- IA detecta contenido potencialmente ofensivo (80% confianza)
- Moderador humano revisa casos de 75-90% confianza
- Decisión final: Moderador
- Responsable: Moderador humano + supervisión del líder del equipo

**Caso 2: Diagnóstico médico asistido por IA**
- IA sugiere posible cáncer (92% confianza)
- Radiólogo revisa imagen y análisis de IA
- Decisión final: Médico
- Responsable: Médico (licencia profesional), hospital (institución)

---

## 2. Aplicación Integrada de los 6 Principios

### Caso Completo: Sistema de Contratación con IA

**Escenario:** Empresa multinacional implementa IA para filtrar 10,000 CVs mensuales.

#### Aplicación de cada principio:

**1. Fairness (Equidad)**
- ✅ Entrenar con CVs diversos (género, etnia, edad)
- ✅ Remover campos sesgados (nombre, foto, dirección)
- ✅ Evaluar precisión por grupos demográficos
- ✅ Auditar trimestralmente para sesgos emergentes

**2. Reliability & Safety (Confiabilidad)**
- ✅ Testing exhaustivo con diferentes formatos de CV
- ✅ Manejo de errores (formato no reconocido → revisión humana)
- ✅ Monitoreo: alertas si tasa de rechazo cambia >10%
- ✅ Fallback: Si IA falla, todo va a revisión humana

**3. Privacy & Security (Privacidad)**
- ✅ Encriptar todos los CVs (datos personales sensibles)
- ✅ Acceso solo a RRHH autorizado (RBAC)
- ✅ Retención limitada: eliminar CVs rechazados después de 6 meses
- ✅ Cumplir GDPR: derecho a eliminación

**4. Inclusiveness (Inclusividad)**
- ✅ Aceptar CVs en múltiples formatos (PDF, DOCX, texto)
- ✅ Procesamiento de CVs con formatos no tradicionales
- ✅ No penalizar gaps laborales (pueden ser por maternidad, enfermedad)
- ✅ Considerar educación no tradicional (bootcamps, autodidactas)

**5. Transparency (Transparencia)**
- ✅ Informar a candidatos que IA revisa CVs inicialmente
- ✅ Explicar criterios de evaluación en job posting
- ✅ Si rechazado, proporcionar razones generales
- ✅ Proceso de apelación disponible

**6. Accountability (Responsabilidad)**
- ✅ Reclutador humano revisa todos los CVs aprobados por IA
- ✅ Decisión final SIEMPRE humana
- ✅ Comité de ética supervisa el sistema trimestralmente
- ✅ Métricas reportadas a directorio mensualmente

---

## 3. Identificación y Mitigación de Sesgos

### Tipos comunes de sesgos

#### 1. Sesgo en datos de entrenamiento

**Problema:** Los datos históricos reflejan discriminación pasada.

**Ejemplo:**
- Dataset de contratación de 1990-2010
- 90% de ingenieros eran hombres
- Modelo aprende: ingeniero = probable hombre
- Resultado: discrimina contra mujeres

**Mitigación:**
- Balancear dataset
- Sobremuestrear grupos subrepresentados
- Re-etiquetar datos problemáticos
- Entrenar con datos más recientes

#### 2. Sesgo de etiquetado

**Problema:** Los humanos que etiquetan datos tienen sesgos.

**Ejemplo:**
- Etiquetar fotos de "profesional de negocios"
- Etiquetadores inconscientemente etiquetan más hombres en traje
- Modelo aprende sesgo

**Mitigación:**
- Múltiples etiquetadores por item
- Guidelines claros y objetivos
- Revisar acuerdo inter-etiquetador
- Auditar patrones de etiquetado

#### 3. Sesgo de medición

**Problema:** Las métricas mismas pueden ser sesgadas.

**Ejemplo:**
- Medir "buen empleado" solo por horas trabajadas
- Discrimina contra padres/madres con responsabilidades familiares

**Mitigación:**
- Usar múltiples métricas
- Considerar contexto
- Validar que métricas correlacionen con outcome real

#### 4. Sesgo de agregación

**Problema:** Un modelo para todos no funciona igual para todos.

**Ejemplo:**
- Modelo de diagnóstico médico entrenado principalmente con datos de hombres
- Menor precisión en mujeres (síntomas diferentes)

**Mitigación:**
- Modelos especializados por grupo cuando sea apropiado
- O modelo con features que capturen diferencias

### Proceso de detección de sesgos

**Paso 1: Identificar grupos sensibles**
- Género, edad, etnia, discapacidad, etc.

**Paso 2: Evaluar métricas por grupo**
```python
# Ejemplo: Evaluar precisión de modelo por género
for gender in ['Male', 'Female', 'Non-binary']:
    subset = test_data[test_data['gender'] == gender]
    accuracy = evaluate(model, subset)
    print(f"{gender}: {accuracy:.2%}")

# Output esperado similar:
# Male: 87%
# Female: 85%
# Non-binary: 83%
```

**Paso 3: Definir umbrales aceptables**
- Diferencia máxima entre grupos: ej. 5%
- Si se excede → investigar y mitigar

**Paso 4: Implementar técnicas de mitigación**

**Técnicas principales:**

**Pre-processing (antes de entrenar):**
- Reweighting: dar más peso a grupos subrepresentados
- Sampling: balancear dataset

**In-processing (durante entrenamiento):**
- Fairness constraints: penalizar modelo por disparidad
- Adversarial debiasing: usar red adversaria

**Post-processing (después de entrenar):**
- Threshold optimization: diferentes umbrales por grupo
- Calibration: ajustar probabilidades

---

## 4. Gobernanza y Políticas de IA

### Componentes de un programa de IA Responsable

#### 1. Políticas y estándares

**Documentos clave:**
- **AI Principles Document**: Valores de la organización
- **AI Usage Policy**: Qué se puede/no puede hacer
- **Model Development Standards**: Cómo desarrollar modelos
- **Deployment Checklist**: Qué validar antes de producción

**Ejemplo de sección de política:**
```
3.2 Prohibiciones en uso de IA

Está estrictamente prohibido usar IA para:
a) Decisiones automatizadas sobre empleo sin revisión humana
b) Reconocimiento facial para vigilancia masiva
c) Scoring social de empleados
d) Cualquier uso que viole derechos humanos fundamentales

Violaciones serán investigadas por el Comité de Ética.
```

#### 2. Comité de Ética de IA

**Composición típica:**
- CTO o líder técnico
- Chief Legal Officer
- Representante de Diversidad e Inclusión
- Data Scientists senior
- Representante de usuarios/clientes
- Experto en ética externo (opcional)

**Responsabilidades:**
- Revisar nuevos proyectos de IA
- Aprobar/rechazar despliegues
- Investigar incidentes
- Actualizar políticas
- Capacitación en IA Responsable

#### 3. Proceso de revisión

**Impact Assessment (Evaluación de Impacto):**

```
Proyecto: [Nombre del sistema de IA]

1. Propósito y beneficios esperados
2. Datos utilizados (fuente, características sensibles)
3. Potenciales riesgos por principio:
   - Fairness: [riesgos identificados]
   - Reliability: [riesgos identificados]
   - Privacy: [riesgos identificados]
   - Inclusiveness: [riesgos identificados]
   - Transparency: [riesgos identificados]
   - Accountability: [riesgos identificados]
4. Mitigaciones implementadas
5. Métricas de monitoreo
6. Plan de respuesta a incidentes
7. Revisión y aprobación: [Firma del comité]
```

#### 4. Capacitación continua

**Programas de training:**
- Todos los empleados: Awareness de IA Responsable (1 hora/año)
- Desarrolladores de IA: Training profundo (1 día/año)
- Líderes: Gobernanza y accountability (medio día/año)

---

## 5. Herramientas de Microsoft para IA Responsable

### Fairlearn
- **Propósito:** Evaluar y mitigar sesgos
- **Capacidades:** Métricas de fairness, algoritmos de mitigación
- **Uso:** Python library

### InterpretML
- **Propósito:** Explicabilidad de modelos
- **Capacidades:** Feature importance, explanations
- **Uso:** Python library

### Error Analysis
- **Propósito:** Identificar dónde falla el modelo
- **Capacidades:** Análisis de cohorts, árbol de errores
- **Uso:** Parte de Responsible AI Toolbox

### Responsible AI Dashboard
- **Propósito:** Vista unificada de IA Responsable
- **Capacidades:** Fairness, explicabilidad, error analysis en un solo lugar
- **Uso:** Azure Machine Learning Studio

### Azure AI Content Safety
- **Propósito:** Detectar contenido dañino
- **Capacidades:** Detectar violencia, odio, sexual, auto-daño
- **Uso:** API REST

---

## ✅ Puntos Clave para el Examen

- **6 Principios de IA Responsable:** Fairness, Reliability & Safety, Privacy & Security, Inclusiveness, Transparency, Accountability
- **Fairness** = tratar a todos de manera justa, sin discriminación basada en características protegidas
- **Reliability** = funcionar consistentemente y manejar errores apropiadamente
- **Privacy** = proteger datos personales, cumplir regulaciones (GDPR, HIPAA)
- **Inclusiveness** = accesible para todos, incluyendo personas con discapacidades
- **Transparency** = usuarios entienden cómo funciona el sistema y sus limitaciones
- **Accountability** = supervisión humana, responsabilidad clara de decisiones
- **Transparency Notes** de Microsoft explican capacidades y limitaciones de cada servicio
- **Fairlearn** es la herramienta para evaluar y mitigar sesgos
- **InterpretML** proporciona explicabilidad de modelos
- **Sesgos** pueden venir de: datos de entrenamiento, etiquetado, medición, agregación
- Human-in-the-loop es esencial para decisiones críticas
- Azure AI Content Safety detecta contenido dañino (violencia, odio, sexual, auto-daño)
- GDPR requiere: consentimiento explícito, derecho a ser olvidado, notificación de brechas
- Modelos deben ser auditados regularmente para detectar sesgos emergentes

---

## 🎯 Preguntas Estilo Examen Microsoft AI-900

### Pregunta 1
Un sistema de reconocimiento facial tiene 95% de precisión para personas de piel clara pero solo 75% para personas de piel oscura. ¿Qué principio de IA Responsable se está violando?

A) Transparency  
B) Accountability  
C) Fairness  
D) Privacy & Security

**Respuesta correcta: C) Fairness**

**Explicación**: **Fairness (Equidad)** requiere que los sistemas de IA traten a todas las personas de manera justa sin discriminación. Una diferencia de 20% en precisión entre grupos étnicos constituye sesgo y discriminación. Para corregirlo, se debe entrenar con un dataset más diverso y balanceado. Transparency (A) es sobre explicar funcionamiento, Accountability (B) sobre responsabilidad humana, y Privacy (D) sobre protección de datos.

---

### Pregunta 2
Una empresa desarrolla un chatbot para servicio al cliente. ¿Qué principio de IA Responsable requiere que el chatbot informe a los usuarios que están hablando con IA y no con un humano?

A) Fairness  
B) Transparency  
C) Inclusiveness  
D) Reliability

**Respuesta correcta: B) Transparency**

**Explicación**: **Transparency (Transparencia)** requiere divulgación clara cuando los usuarios interactúan con IA en lugar de humanos. Esto construye confianza y permite a los usuarios tomar decisiones informadas sobre cómo compartir información. Fairness (A) es sobre trato equitativo, Inclusiveness (C) sobre accesibilidad, y Reliability (D) sobre funcionamiento consistente.

---

### Pregunta 3
Un hospital implementa IA para diagnóstico médico. El sistema proporciona recomendaciones, pero un médico siempre revisa y toma la decisión final. ¿Qué principio se está aplicando?

A) Fairness  
B) Privacy & Security  
C) Transparency  
D) Accountability

**Respuesta correcta: D) Accountability**

**Explicación**: **Accountability (Responsabilidad)** requiere supervisión humana para decisiones críticas. En este caso, el médico es responsable de la decisión final y puede anular la recomendación de la IA. Esto es especialmente importante en aplicaciones de alto riesgo como medicina. Fairness (A) sería sobre trato equitativo de pacientes, Privacy (B) sobre protección de datos médicos, y Transparency (C) sobre explicar cómo funciona el sistema.

---

### Pregunta 4
¿Cuál de las siguientes herramientas de Microsoft se usa específicamente para evaluar y mitigar sesgos en modelos de machine learning?

A) InterpretML  
B) Fairlearn  
C) Azure Monitor  
D) Error Analysis

**Respuesta correcta: B) Fairlearn**

**Explicación**: **Fairlearn** es la biblioteca de Python diseñada específicamente para evaluar fairness (equidad) y mitigar sesgos en modelos ML. Permite comparar rendimiento entre grupos demográficos y aplicar algoritmos de mitigación. InterpretML (A) es para explicabilidad, Azure Monitor (C) para observabilidad general, y Error Analysis (D) para identificar dónde falla el modelo (pero no específicamente para sesgos).

---

### Pregunta 5
Una empresa debe cumplir con GDPR al desarrollar un sistema de IA que procesa datos de ciudadanos europeos. ¿Qué principio de IA Responsable es más relevante?

A) Fairness  
B) Inclusiveness  
C) Privacy & Security  
D) Transparency

**Respuesta correcta: C) Privacy & Security**

**Explicación**: **Privacy & Security (Privacidad y Seguridad)** es el principio directamente relacionado con cumplimiento regulatorio como GDPR. GDPR requiere protección de datos personales, consentimiento explícito, derecho a ser olvidado, y notificación de brechas. Mientras que Transparency (D) también es parte de GDPR (explicar uso de datos), Privacy & Security es el principio fundamental. Fairness (A) e Inclusiveness (B) no están directamente relacionados con cumplimiento de privacidad.

---

### Pregunta 6
Un sistema de aprobación de crédito debe explicar por qué un préstamo fue rechazado, indicando los factores principales que influyeron en la decisión. ¿Qué principio de IA Responsable requiere esta explicación?

A) Accountability  
B) Transparency  
C) Fairness  
D) Reliability

**Respuesta correcta: B) Transparency**

**Explicación**: **Transparency (Transparencia)** incluye explicabilidad - los usuarios deben entender por qué el sistema tomó cierta decisión. En sistemas financieros, esto es además un requisito regulatorio en muchos países. Proporcionar los factores que llevaron al rechazo permite al solicitante entender y potencialmente mejorar su situación. Accountability (A) sería sobre quién es responsable de la decisión, Fairness (C) sobre trato equitativo, y Reliability (D) sobre consistencia.

---

### Pregunta 7
Un sistema de IA para contratación es entrenado con CVs históricos de los últimos 20 años. Durante testing, se descubre que favorece candidatos masculinos. ¿Cuál es la causa MÁS probable?

A) Error en el código del modelo  
B) Sesgo en los datos de entrenamiento  
C) Falta de transparencia  
D) Problema de privacidad

**Respuesta correcta: B) Sesgo en los datos de entrenamiento**

**Explicación**: Los datos históricos frecuentemente reflejan discriminación o desigualdades del pasado. Si hace 20 años había mayoría de hombres contratados, el modelo aprende ese patrón y lo replica. Este es el tipo de **sesgo más común en IA**. La solución incluye: balancear el dataset, remover features sesgadas, y auditar el modelo regularmente. Un error de código (A) causaría otros problemas, falta de transparencia (C) no causa el sesgo sino dificulta detectarlo, y privacidad (D) no está relacionada.

---

### Pregunta 8
¿Qué documento de Microsoft proporciona información sobre casos de uso apropiados, limitaciones y factores que afectan la calidad de un servicio de Azure AI?

A) API Documentation  
B) Pricing Calculator  
C) Transparency Notes  
D) Service Level Agreement (SLA)

**Respuesta correcta: C) Transparency Notes**

**Explicación**: **Transparency Notes** son documentos publicados por Microsoft para cada servicio de Azure AI que explican: qué hace el sistema, casos de uso apropiados e inapropiados, limitaciones conocidas, cómo fue evaluado, y factores que afectan calidad. Son parte del compromiso de Transparency. API Documentation (A) es técnica, Pricing Calculator (B) es para costos, y SLA (D) es sobre disponibilidad del servicio.

---

### Pregunta 9
Una aplicación móvil con IA debe ser utilizable por personas con discapacidad visual. ¿Qué principio de IA Responsable es prioritario?

A) Privacy & Security  
B) Fairness  
C) Inclusiveness  
D) Accountability

**Respuesta correcta: C) Inclusiveness**

**Explicación**: **Inclusiveness (Inclusividad)** requiere que los sistemas de IA sean accesibles para todos, incluyendo personas con discapacidades. En este caso, la app debe ser compatible con lectores de pantalla, tener navegación por voz, alto contraste, etc. Fairness (B) es sobre trato equitativo pero no específicamente sobre accesibilidad, Privacy (A) es sobre datos, y Accountability (D) es sobre responsabilidad humana.

---

### Pregunta 10
En un sistema de IA para recursos humanos, ¿qué práctica MEJOR ejemplifica el principio de Accountability?

A) Encriptar todos los datos de empleados  
B) Usar un dataset balanceado para entrenamiento  
C) Requerir que un gerente de RRHH revise y apruebe todas las decisiones finales  
D) Proporcionar explicaciones de las decisiones a los candidatos

**Respuesta correcta: C) Requerir que un gerente de RRHH revise y apruebe todas las decisiones finales**

**Explicación**: **Accountability (Responsabilidad)** se centra en supervisión humana y responsabilidad clara. Un humano (gerente de RRHH) debe ser responsable de las decisiones finales, especialmente en contextos críticos como empleo. Encriptar datos (A) es Privacy & Security, dataset balanceado (B) es Fairness, y proporcionar explicaciones (D) es Transparency. Aunque todas son importantes, (C) es la aplicación más directa de Accountability.

---

## 📖 Recursos Adicionales

- [Microsoft Responsible AI Principles](https://www.microsoft.com/ai/responsible-ai)
- [Fairlearn Documentation](https://fairlearn.org/)
- [Azure AI Transparency Notes](https://learn.microsoft.com/azure/cognitive-services/transparency-note)
- [Responsible AI Toolbox](https://responsibleaitoolbox.ai/)
- [GDPR Compliance Guide](https://gdpr.eu/)
