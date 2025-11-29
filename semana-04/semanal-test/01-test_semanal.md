## 40 Preguntas Estilo Examen Microsoft AI-900 con Casos Reales

---

## 🎯 SOBRE ESTE BANCO DE PREGUNTAS

**Propósito:** Práctica adicional con escenarios realistas del mundo empresarial

**Características:**
- ✅ 40 preguntas nuevas (adicionales a las 30 del viernes)
- ✅ Escenarios basados en casos reales de empresas
- ✅ Nivel de dificultad variado (fácil, medio, difícil)
- ✅ Explicaciones detalladas
- ✅ Tips para identificar patrones

**Formato:**
- Opción múltiple (4 opciones)
- Algunas preguntas multi-select (donde se indica)
- Estilo idéntico al examen AI-900 real

**Tiempo sugerido:** 60-75 minutos

---

## 📊 SECCIÓN 1: SENTIMENT ANALYSIS & OPINION MINING - CASOS REALES (10 preguntas)

### Pregunta 1 - Retail E-commerce
**DIFICULTAD: 🟢 Fácil**

**ESCENARIO:**
Una tienda online recibe esta reseña de un producto:
```
"El producto llegó rápido y el empaque era perfecto. Sin embargo, 
la calidad del material es decepcionante para el precio. El color 
también es diferente al de las fotos."
```

El sistema de Sentiment Analysis devuelve: `sentiment: "mixed"`

**PREGUNTA:**
¿Por qué el resultado es "mixed" en lugar de "negative"?

A) Hay un error en el análisis, debería ser "negative"  
B) El texto contiene tanto elementos positivos (entrega, empaque) como negativos (calidad, color)  
C) El sistema no tiene suficiente confianza para determinar el sentimiento  
D) "Mixed" significa que el texto es neutral  

<details>
<summary>👉 Ver respuesta y explicación</summary>

**RESPUESTA CORRECTA: B) El texto contiene tanto elementos positivos (entrega, empaque) como negativos (calidad, color)**

**EXPLICACIÓN DETALLADA:**

```
ANÁLISIS DEL TEXTO:

ELEMENTOS POSITIVOS:
✅ "llegó rápido" 
✅ "empaque perfecto"

ELEMENTOS NEGATIVOS:
❌ "calidad decepcionante"
❌ "color diferente"

RESULTADO:
Como hay balance entre positivo y negativo → MIXED
```

**Por qué las otras son incorrectas:**
- **A)** FALSO: No es error, mixed es válido cuando hay balance
- **C)** FALSO: Mixed no significa baja confianza, significa balance de sentimientos
- **D)** FALSO: Mixed ≠ Neutral. Neutral es ausencia de sentimiento; Mixed es presencia de ambos

**PATRÓN PARA EL EXAMEN:**
Cuando veas reseñas con "pero", "sin embargo", "aunque" → piensa en MIXED sentiment

**TIP:**
```
PALABRAS CLAVE que indican MIXED:
- "pero"
- "sin embargo"  
- "aunque"
- Mitad positivo + mitad negativo
```

</details>

---

### Pregunta 2 - Análisis de Redes Sociales
**DIFICULTAD: 🟡 Media**

**ESCENARIO:**
Una agencia de marketing analiza 50,000 tweets sobre una nueva película. Reciben estos confidence scores promedio:

```
Tweet tipo A:
{
  "positive": 0.89,
  "neutral": 0.08,
  "negative": 0.03
}

Tweet tipo B:
{
  "positive": 0.52,
  "neutral": 0.28,
  "negative": 0.20
}
```

**PREGUNTA:**
¿Qué recomendación correcta puede hacer la agencia al cliente basándose en estos datos?

A) Ambos tipos de tweets muestran la misma recepción positiva  
B) Tweet tipo A muestra recepción muy positiva (alta confianza); tipo B muestra recepción ligeramente positiva pero más ambigua  
C) Los datos son inválidos porque los confidence scores del tipo B no suman 1.00  
D) Tweet tipo B muestra sentimiento negativo predominante  

<details>
<summary>👉 Ver respuesta y explicación</summary>

**RESPUESTA CORRECTA: B) Tweet tipo A muestra recepción muy positiva (alta confianza); tipo B muestra recepción ligeramente positiva pero más ambigua**

**EXPLICACIÓN DETALLADA:**

```
TWEET TIPO A:
positive: 0.89 → MUY ALTO (89%)
negative: 0.03 → INSIGNIFICANTE (3%)
INTERPRETACIÓN: ✅ Recepción MUY positiva

TWEET TIPO B:
positive: 0.52 → MEDIO (52%)
neutral: 0.28 → CONSIDERABLE (28%)
negative: 0.20 → NO DESPRECIABLE (20%)
INTERPRETACIÓN: ⚠️ Ligeramente positivo pero AMBIGUO
```

**RECOMENDACIÓN AL CLIENTE:**
```
✅ FORTALEZA: 
Tweets claramente positivos (tipo A) dominan

⚠️ ÁREA DE ATENCIÓN:
Hay un segmento con opiniones mixtas/ambiguas (tipo B)
→ Investigar qué aspectos causan esta ambigüedad
```

**Por qué las otras son incorrectas:**
- **A)** FALSO: 0.89 (muy claro) ≠ 0.52 (ambiguo)
- **C)** FALSO: 0.52 + 0.28 + 0.20 = 1.00 ✅ (suma correctamente)
- **D)** FALSO: Positive (0.52) > Negative (0.20), es positivo aunque débil

**CONCEPTO CLAVE:**
```
INTERPRETACIÓN DE CONFIDENCE SCORES:

ALTA CONFIANZA (>0.80):
→ Sentimiento muy claro
→ Confiable para decisiones

MEDIA CONFIANZA (0.50-0.80):
→ Sentimiento existe pero con ambigüedad
→ Revisar casos individuales

BAJA CONFIANZA (<0.50):
→ Texto muy ambiguo
→ Revisión manual recomendada
```

**TIP PARA EL EXAMEN:**
No todos los confidence scores altos son iguales. 0.89 y 0.52 ambos indican "positive", pero con niveles muy diferentes de certeza.

</details>

---

### Pregunta 3 - Feedback de Empleados (Opinion Mining)
**DIFICULTAD: 🟡 Media**

**ESCENARIO:**
Una empresa de 2,000 empleados realiza encuesta anual de satisfacción. Quieren un dashboard que muestre:

```
RESULTADOS DESEADOS:
- Salario: 45% satisfecho, 55% insatisfecho
- Balance vida-trabajo: 78% satisfecho, 22% insatisfecho
- Gestión: 62% satisfecho, 38% insatisfecho
- Beneficios: 85% satisfecho, 15% insatisfecho
- Cultura: 71% satisfecho, 29% insatisfecho
```

**PREGUNTA:**
¿Qué combinación de servicios de Azure AI Language necesitan?

A) Solo Sentiment Analysis (documento completo)  
B) Sentiment Analysis + Key Phrase Extraction  
C) Opinion Mining para identificar targets (aspectos) y sentimiento sobre cada uno  
D) Named Entity Recognition + Sentiment Analysis  

<details>
<summary>👉 Ver respuesta y explicación</summary>

**RESPUESTA CORRECTA: C) Opinion Mining para identificar targets (aspectos) y sentimiento sobre cada uno**

**EXPLICACIÓN DETALLADA:**

```
ANÁLISIS DEL REQUERIMIENTO:

NECESITAN:
✅ Identificar ASPECTOS específicos (salario, balance, gestión, etc.)
✅ Sentimiento SOBRE CADA aspecto
✅ Porcentajes por aspecto

ESTO ES EXACTAMENTE Opinion Mining:
Target: "salario" → Sentiment: 45% positivo, 55% negativo
Target: "balance vida-trabajo" → Sentiment: 78% positivo, 22% negativo
```

**EJEMPLO DE COMENTARIO:**
```
"Me encanta la cultura de la empresa y los beneficios son excelentes. 
Sin embargo, el salario es bajo comparado con el mercado y la carga 
de trabajo es muy pesada."

SENTIMENT ANALYSIS (básico):
→ MIXED (alguna cosa positiva, alguna negativa)
❌ NO identifica QUÉ aspectos son positivos/negativos

OPINION MINING:
→ Target: "cultura" → POSITIVE
→ Target: "beneficios" → POSITIVE  
→ Target: "salario" → NEGATIVE
→ Target: "carga de trabajo" → NEGATIVE
✅ Identifica sentimiento POR ASPECTO
```

**Por qué las otras son incorrectas:**
- **A)** Solo daría tono general, no desglose por aspecto
- **B)** Key Phrases identificaría temas, pero NO asociaría sentimiento a cada uno
- **D)** NER extrae nombres/fechas, no aspectos con sentimiento

**PATRÓN PARA EL EXAMEN:**
```
PALABRAS CLAVE que indican Opinion Mining:
- "aspectos específicos"
- "qué características"
- "desglose por categoría"
- "dashboard por atributo"
- "análisis granular"
```

**TIP:**
Si la pregunta pide identificar MÚLTIPLES aspectos Y el sentimiento sobre CADA UNO → Opinion Mining

</details>

---

### Pregunta 4 - Análisis Multinivel
**DIFICULTAD: 🔴 Difícil**

**ESCENARIO:**
Un sistema analiza reseñas de hoteles. Para esta reseña específica:

```
"El hotel es hermoso y está en el centro de la ciudad. 
Las habitaciones son espaciosas y limpias. 
El personal fue extremadamente grosero y poco profesional. 
El desayuno era terrible, comida fría y sin sabor. 
La piscina del hotel es espectacular."
```

Azure AI Language devuelve:
```json
{
  "document": {
    "sentiment": "mixed",
    "confidenceScores": {
      "positive": 0.48,
      "neutral": 0.07,
      "negative": 0.45
    }
  },
  "sentences": [
    {"text": "El hotel es hermoso...", "sentiment": "positive"},
    {"text": "Las habitaciones son...", "sentiment": "positive"},
    {"text": "El personal fue...", "sentiment": "negative"},
    {"text": "El desayuno era...", "sentiment": "negative"},
    {"text": "La piscina del hotel...", "sentiment": "positive"}
  ]
}
```

**PREGUNTA:**
Un gerente del hotel pregunta: "¿Por qué el análisis dice 'mixed' si tenemos 3 oraciones positivas y solo 2 negativas?" ¿Cuál es la explicación CORRECTA?

A) Hay un error en el sistema, debería marcar como "positive" por mayoría  
B) El análisis a nivel de documento considera el peso emocional de las palabras, no solo el conteo de oraciones  
C) El sistema está mal entrenado para español  
D) Mixed siempre se asigna cuando hay cualquier oración negativa, sin importar la proporción  

<details>
<summary>👉 Ver respuesta y explicación</summary>

**RESPUESTA CORRECTA: B) El análisis a nivel de documento considera el peso emocional de las palabras, no solo el conteo de oraciones**

**EXPLICACIÓN DETALLADA:**

```
ANÁLISIS PROFUNDO:

ORACIONES POSITIVAS (3):
1. "hermoso", "centro de la ciudad" → Moderadamente positivo
2. "espaciosas", "limpias" → Moderadamente positivo
3. "espectacular" → Muy positivo

ORACIONES NEGATIVAS (2):
4. "EXTREMADAMENTE grosero", "poco profesional" → MUY negativo
5. "TERRIBLE", "fría", "sin sabor" → MUY negativo

PALABRAS CLAVE:
✅ Positivas: hermoso, espaciosas, limpias, espectacular
❌ Negativas: EXTREMADAMENTE, grosero, poco profesional, TERRIBLE

INTENSIDAD:
Las palabras negativas tienen MAYOR intensidad emocional
→ "EXTREMADAMENTE grosero" pesa más que "hermoso"
→ "TERRIBLE" pesa más que "espaciosas"
```

**CONCEPTO IMPORTANTE:**
El modelo de Sentiment Analysis no cuenta oraciones, sino que:
1. Analiza intensidad de palabras emocionales
2. Considera contexto y modificadores (extremadamente, muy, poco)
3. Pondera el impacto emocional general

```
CONTEO SIMPLE (incorrecto):
3 positivas vs 2 negativas = POSITIVE ❌

ANÁLISIS REAL (correcto):
Peso emocional total ≈ equilibrado = MIXED ✅
```

**Por qué las otras son incorrectas:**
- **A)** El sistema NO funciona por conteo de oraciones, sino por peso emocional
- **C)** El análisis es correcto; el español está bien soportado
- **D)** FALSO: Mixed requiere balance, no solo presencia de negativo

**CASO REAL COMPARABLE:**
```
Imagina estas dos reseñas:

RESEÑA 1:
"Está bien. Es aceptable. No está mal."
3 oraciones ligeramente positivas
→ Sentiment: NEUTRAL/POSITIVE (bajo)

RESEÑA 2:  
"¡ODIO este lugar! ¡HORRIBLE experiencia!"
2 oraciones extremadamente negativas
→ Sentiment: VERY NEGATIVE

La INTENSIDAD importa más que el CONTEO
```

**TIP PARA EL EXAMEN:**
El análisis de sentimiento es sobre PESO EMOCIONAL, no conteo estadístico de oraciones positivas vs negativas.

</details>

---

### Pregunta 5 - Threshold Configuration
**DIFICULTAD: 🟡 Media**

**ESCENARIO:**
Una empresa configura un sistema automático que:
- Si sentiment = NEGATIVE con confidence >0.80 → Alerta urgente al equipo
- Si sentiment = NEGATIVE con confidence 0.60-0.80 → Cola de revisión
- Si sentiment = NEGATIVE con confidence <0.60 → Sin acción

Reciben esta reseña:
```
"No estoy seguro sobre este producto. Tiene cosas buenas y malas."

Resultado:
{
  "sentiment": "neutral",
  "confidenceScores": {
    "positive": 0.28,
    "neutral": 0.45,
    "negative": 0.27
  }
}
```

**PREGUNTA:**
¿Qué acción tomará el sistema?

A) Alerta urgente (negative >0.80)  
B) Cola de revisión (negative 0.60-0.80)  
C) Sin acción automática  
D) Error, debe reprocessarse  

<details>
<summary>👉 Ver respuesta y explicación</summary>

**RESPUESTA CORRECTA: C) Sin acción automática**

**EXPLICACIÓN DETALLADA:**

```
ANÁLISIS DE LA CONFIGURACIÓN:

CONDICIONES:
1. Alerta urgente: sentiment = NEGATIVE AND confidence >0.80
2. Cola revisión: sentiment = NEGATIVE AND confidence 0.60-0.80
3. Sin acción: Todo lo demás

RESULTADO RECIBIDO:
- Sentiment: NEUTRAL (NO negative)
- Confidence negative: 0.27 (muy bajo)

EVALUACIÓN:
Condición 1: ❌ (no es NEGATIVE)
Condición 2: ❌ (no es NEGATIVE)
Condición 3: ✅ (default)

ACCIÓN: Sin acción automática
```

**RAZONAMIENTO:**
```
El sistema busca sentiment = NEGATIVE
Pero recibió sentiment = NEUTRAL

Aunque hay 0.27 (27%) de negative en los scores,
el SENTIMIENTO PREDOMINANTE es NEUTRAL (0.45 = 45%)

Por lo tanto, NO cumple las condiciones de alerta
```

**CASO EDUCATIVO:**
Este es exactamente el tipo de reseña ambigua que:
- No dispara alertas automáticas
- Debería revisarse manualmente en un flujo completo
- Representa incertidumbre del usuario

**Por qué las otras son incorrectas:**
- **A)** Requiere negative >0.80, pero es neutral con 0.27 negative
- **B)** Requiere negative 0.60-0.80, pero es neutral con 0.27 negative
- **D)** No hay error, es un resultado válido

**CONCEPTO CLAVE:**
```
DIFERENCIA IMPORTANTE:

sentiment: "negative" 
→ Es el TIPO predominante

confidenceScores.negative: 0.27
→ Es el PORCENTAJE de negatividad detectada

Para que actúe, necesitas:
sentiment == "negative" (predominante)
```

**TIP PARA EL EXAMEN:**
Lee cuidadosamente las CONDICIONES. El sistema evalúa el `sentiment` predominante, no los `confidenceScores` individuales.

</details>

---

### Pregunta 6 - Document vs Sentence Level
**DIFICULTAD: 🟡 Media**

**ESCENARIO:**
Un analista revisa resultados de Sentiment Analysis y encuentra esto confuso:

```
DOCUMENTO COMPLETO: sentiment = "positive" (0.75)

ORACIONES:
1. "Excelente producto" → positive (0.95)
2. "Muy recomendable" → positive (0.92)
3. "Servicio al cliente terrible" → negative (0.88)
4. "Gran calidad" → positive (0.90)
```

**PREGUNTA:**
El analista pregunta: "¿Cómo puede el documento ser 'positive' si hay una oración muy negativa?" ¿Cuál es la mejor explicación?

A) Hay un error, debería ser "mixed"  
B) El análisis de documento pondera todas las oraciones; 3 positivas fuertes superan 1 negativa  
C) El sistema ignora oraciones negativas minoritarias  
D) Solo la primera oración determina el sentimiento del documento  

<details>
<summary>👉 Ver respuesta y explicación</summary>

**RESPUESTA CORRECTA: B) El análisis de documento pondera todas las oraciones; 3 positivas fuertes superan 1 negativa**

**EXPLICACIÓN DETALLADA:**

```
ANÁLISIS MATEMÁTICO (simplificado):

PESO EMOCIONAL:
Oración 1: +0.95 (muy positiva)
Oración 2: +0.92 (muy positiva)
Oración 3: -0.88 (muy negativa)
Oración 4: +0.90 (muy positiva)

PROMEDIO PONDERADO (aproximado):
(0.95 + 0.92 - 0.88 + 0.90) / 4 = 0.72 ≈ 0.75

RESULTADO DOCUMENTO: POSITIVE (0.75)
```

**RAZONAMIENTO:**
```
3 ORACIONES MUY POSITIVAS (0.95, 0.92, 0.90)
vs
1 ORACIÓN MUY NEGATIVA (0.88)

La proporción 3:1 positivo:negativo con pesos altos
→ Documento GENERAL es positivo

Pero el score no es 0.95 (altísimo)
→ Es 0.75 (positivo pero más moderado)
→ Refleja que HAY contenido negativo
```

**ANALOGÍA:**
```
Si 3 personas califican un restaurante con 5⭐
y 1 persona califica con 1⭐

Promedio ≈ 4 estrellas (positivo, pero no perfecto)
No es 5⭐ (por el review negativo)
No es 2.5⭐ (porque mayoría es positiva)
```

**Por qué las otras son incorrectas:**
- **A)** No es error; positive es correcto cuando positivo > negativo significativamente
- **C)** No ignora nada; todas las oraciones influyen en el score final
- **D)** FALSO: Todas las oraciones contribuyen, no solo la primera

**CUÁNDO SERÍA "MIXED":**
```
Si fuera:
2 positivas (0.85, 0.88)
2 negativas (0.82, 0.86)

→ Balance más parejo → MIXED

Pero 3 vs 1 con todas scores altos
→ Claro predominio positivo → POSITIVE
```

**TIP PARA EL EXAMEN:**
Documento "positive" puede contener oraciones negativas si la proporción y peso favorece claramente lo positivo. Mixed requiere balance más equitativo.

</details>

---

### Pregunta 7 - Active Learning en Opinion Mining
**DIFICULTAD: 🔴 Difícil**

**ESCENARIO:**
Una cadena hotelera implementó Opinion Mining hace 3 meses. El sistema ahora detecta estos targets comúnmente:
- Habitaciones, WiFi, Desayuno, Ubicación, Personal

Empiezan a recibir menciones de un nuevo target que el sistema NO reconoce bien:
"Las medidas de higiene COVID son excelentes"
"Protocolos sanitarios muy estrictos"
"Limpieza anti-COVID impecable"

**PREGUNTA:**
¿Qué característica de Azure AI Language les permite mejorar el sistema para reconocer "protocolos COVID/sanitarios" como un nuevo target?

A) Active Learning  
B) Custom Text Classification  
C) Sentiment Analysis avanzado  
D) Entity Linking  

<details>
<summary>👉 Ver respuesta y explicación</summary>

**RESPUESTA CORRECTA: A) Active Learning**

**EXPLICACIÓN DETALLADA:**

```
PROBLEMA:
Nuevo concepto emergente: "Protocolos COVID/Sanitarios"
Sistema entrenado pre-COVID no reconoce este target

SOLUCIÓN: Active Learning
```

**CÓMO FUNCIONA ACTIVE LEARNING:**

```
PASO 1: SISTEMA DETECTA INCERTIDUMBRE
Recibe: "Protocolos sanitarios muy estrictos"
Sistema piensa: 
  "¿Es esto sobre 'Limpieza'? (60% seguro)
   ¿Es un nuevo concepto? (40% seguro)"
→ Marca para revisión humana

PASO 2: REVISIÓN HUMANA
Administrador revisa:
✅ "Sí, es un nuevo target: 'Protocolos Sanitarios'"
✅ Asocia estas frases al nuevo target

PASO 3: SISTEMA APRENDE
Próximas menciones de:
- "protocolos COVID"
- "medidas sanitarias"
- "higiene COVID"
→ Se reconocen automáticamente como target

PASO 4: MEJORA CONTINUA
El sistema ahora detecta este nuevo aspecto
en futuras reseñas automáticamente
```

**EJEMPLO PRÁCTICO:**

```
MES 1 (sin Active Learning):
"Los protocolos COVID son excelentes"
→ No detectado como target ❌

MES 2 (con Active Learning - entrenamiento):
"Las medidas sanitarias son estrictas"
→ Marcado para revisión
→ Admin confirma: nuevo target "Protocolos Sanitarios"

MES 3 (después de aprendizaje):
"Higiene COVID impecable"
→ Automáticamente detectado ✅
→ Target: "Protocolos Sanitarios"
→ Sentiment: POSITIVE
```

**Por qué las otras son incorrectas:**
- **B)** Custom Text Classification es para categorías completas, no targets de Opinion Mining
- **C)** Sentiment Analysis NO aprende nuevos targets, solo detecta sentimiento
- **D)** Entity Linking vincula a Wikipedia, no aprende targets nuevos

**CONCEPTO CLAVE:**
```
ACTIVE LEARNING:
- Sistema mejora CON EL USO
- Aprende de correcciones humanas
- Se adapta a nuevos conceptos
- Común en producción real

STATIC MODEL:
- No cambia después de deployment
- Requiere re-entrenamiento manual
- No se adapta a cambios
```

**CASO REAL:**
```
2019: Hoteles mencionaban "WiFi", "Desayuno"
2020: Aparece "Protocolos COVID" como tema importante
2021: Aparece "Trabajo remoto" como necesidad
2023: Aparece "Cargadores EV" en hoteles modernos

Active Learning permite adaptarse a estos cambios
sin re-entrenar completamente el modelo
```

**TIP PARA EL EXAMEN:**
Active Learning = El sistema APRENDE y se MEJORA automáticamente con feedback humano en producción

</details>

---

### Pregunta 8 - Metadata Filtering en Opinion Mining
**DIFICULTAD: 🔴 Difícil**

**ESCENARIO:**
Una aerolínea analiza feedback de pasajeros. Tienen 3 clases de servicio:
- Económica
- Premium Economy  
- Business

Un pasajero escribe:
"La comida era excelente y el espacio muy cómodo"

**PREGUNTA:**
La aerolínea quiere que Opinion Mining devuelva respuestas contextuales:
- Si es clase Económica → Comparar con estándares de económica
- Si es clase Business → Comparar con estándares de business

¿Qué característica de Azure AI Language necesitan configurar?

A) Multi-turn conversations  
B) Metadata filtering  
C) Custom entities  
D) Sentiment thresholds  

<details>
<summary>👉 Ver respuesta y explicación</summary>

**RESPUESTA CORRECTA: B) Metadata filtering**

**EXPLICACIÓN DETALLADA:**

```
PROBLEMA:
"Espacio cómodo" significa cosas diferentes:

En Económica: 
- 80cm de espacio = "cómodo" (comparado con típico 75cm)

En Business:
- 80cm de espacio = "estrecho" (comparado con típico 120cm)

NECESITAN: Respuestas contextuales basadas en clase
```

**CÓMO FUNCIONA METADATA FILTERING:**

```
CONFIGURACIÓN EN KB:

ENTRADA 1:
Pregunta: "¿Cómo es el espacio?"
Respuesta: "El espacio es adecuado para vuelos cortos"
Metadata: {"clase": "economica"}

ENTRADA 2:
Pregunta: "¿Cómo es el espacio?"
Respuesta: "El espacio es amplio con asientos reclinables"
Metadata: {"clase": "business"}
```

**USO EN PRODUCCIÓN:**

```
CASO 1:
Pasajero de Económica
Context: {"clase": "economica"}
Opinion Mining sobre "espacio":
→ Usa estándares de económica
→ "cómodo" = Bueno comparado con económica típica

CASO 2:
Pasajero de Business
Context: {"clase": "business"}
Opinion Mining sobre "espacio":
→ Usa estándares de business
→ "cómodo" = Mínimo aceptable para business
```

**EJEMPLO REAL COMPLETO:**

```
RESEÑA: "La comida era excelente y el espacio cómodo"
CLASE: Business
METADATA: {"clase": "business"}

OPINION MINING RESULTADO:
Target: "comida"
Assessment: "excelente"  
Sentiment: POSITIVE
Context: "Cumple expectativas premium" ✅

Target: "espacio"
Assessment: "cómodo"
Sentiment: NEUTRAL/POSITIVE
Context: "Adecuado pero no excepcional para Business" ⚠️
```

**Por qué las otras son incorrectas:**
- **A)** Multi-turn es para conversaciones en varios pasos, no contexto de clase
- **C)** Custom entities detectan tipos de datos, no cambian interpretación contextual
- **D)** Thresholds son para confianza, no para contexto

**OTROS USOS DE METADATA:**

```
E-COMMERCE:
Metadata: {"categoria": "electronica"} vs {"categoria": "ropa"}
→ "Dura poco" tiene significado diferente
→ Electrónico: problema de calidad
→ Ropa: tendencia de moda pasajera

HOTELES:
Metadata: {"tipo": "resort"} vs {"tipo": "business"}
→ "Tranquilo" tiene valor diferente
→ Resort: ¡Positivo! (relax)
→ Business: ¿Negativo? (falta actividad)
```

**TIP PARA EL EXAMEN:**
Metadata filtering permite respuestas CONTEXTUALES - la misma frase puede interpretarse diferente según el contexto del usuario/producto.

</details>

---

### Pregunta 9 - Confidence Score Edge Case
**DIFICULTAD: 🔴 Difícil**

**ESCENARIO:**
Un analista recibe estos dos resultados:

```
TEXTO A: "¡Increíble! ¡Perfecto! ¡Me encanta!"
{
  "sentiment": "positive",
  "confidenceScores": {
    "positive": 0.99,
    "neutral": 0.01,
    "negative": 0.00
  }
}

TEXTO B: "OK"
{
  "sentiment": "positive",
  "confidenceScores": {
    "positive": 0.48,
    "neutral": 0.47,
    "negative": 0.05
  }
}
```

**PREGUNTA:**
¿Cuál afirmación es VERDADERA sobre estos resultados?

A) Ambos son igualmente confiables porque ambos tienen sentiment "positive"  
B) Texto A es muy confiable; Texto B está en el límite y podría beneficiarse de revisión manual  
C) Texto B es inválido porque positive (0.48) no es mayoría clara  
D) Ambos requieren re-procesamiento por tener scores tan diferentes  

<details>
<summary>👉 Ver respuesta y explicación</summary>

**RESPUESTA CORRECTA: B) Texto A es muy confiable; Texto B está en el límite y podría beneficiarse de revisión manual**

**EXPLICACIÓN DETALLADA:**

```
ANÁLISIS PROFUNDO:

TEXTO A: "¡Increíble! ¡Perfecto! ¡Me encanta!"
✅ Sentiment: POSITIVE
✅ Confidence: 0.99 (ALTÍSIMA)
✅ Sin ambigüedad
✅ Acción: Confiar completamente

TEXTO B: "OK"
✅ Sentiment: POSITIVE (técnicamente)
⚠️ Confidence: 0.48 (BAJA)
⚠️ Neutral muy cercano: 0.47
⚠️ Alta ambigüedad
⚠️ Acción: Revisión manual recomendada
```

**¿POR QUÉ TEXTO B ES AMBIGUO?**

```
"OK" puede significar:

CONTEXTO 1:
P: "¿Te gustó la película?"
R: "OK" → Meh, regular (NEUTRAL)

CONTEXTO 2:
P: "¿Funciona el sistema?"
R: "OK" → Sí, funciona (NEUTRAL/POSITIVE)

CONTEXTO 3:
P: "¿Apruebas el plan?"
R: "OK" → Acepto (POSITIVE)

La palabra "OK" es inherentemente ambigua
→ Explica los scores casi iguales (0.48 vs 0.47)
```

**ESTRATEGIA EMPRESARIAL RECOMENDADA:**

```
TIER 1 - ALTA CONFIANZA (>0.85):
Action: Procesamiento automático completo
Ejemplo: Texto A (0.99)

TIER 2 - MEDIA CONFIANZA (0.65-0.85):
Action: Procesamiento automático + muestreo aleatorio
Ejemplo: "El producto es bueno" (0.75)

TIER 3 - BAJA CONFIANZA (<0.65):
Action: Marcar para revisión manual
Ejemplo: Texto B (0.48)
```

**Por qué las otras son incorrectas:**
- **A)** NO son igualmente confiables; 0.99 >> 0.48 en confiabilidad
- **C)** NO es inválido; es válido pero con baja certeza
- **D)** NO necesitan re-procesamiento; son resultados correctos

**CONCEPTO IMPORTANTE:**

```
MISMO SENTIMENT ≠ MISMA CONFIANZA

"positive" con 0.99 → CERTEZA ABSOLUTA
"positive" con 0.48 → APENAS POSITIVO

Es como decir:
"99% seguro que es positivo" vs "48% seguro que es positivo"
```

**CASO REAL:**

```
EMPRESA DE SOPORTE:
Analiza 10,000 tickets

HIGH CONFIDENCE (7,000 tickets):
→ Procesamiento automático ✅

LOW CONFIDENCE (3,000 tickets):
→ Revisión humana
→ Descubren: mayoría son casos edge
   * Sarcasmo
   * Contexto cultural
   * Abreviaturas
   * Lenguaje informal

RESULTADO: Mejora en satisfacción del cliente
```

**TIP PARA EL EXAMEN:**
Mismo sentiment label no significa misma confiabilidad. Confidence scores bajos (<0.60) requieren atención adicional incluso si el sentiment parece claro.

</details>

---

### Pregunta 10 - Real-Time Dashboard
**DIFICULTAD: 🟡 Media**

**ESCENARIO:**
Una empresa de delivery de comida quiere un dashboard en tiempo real que muestre:

```
DASHBOARD REQUERIDO:
┌─────────────────────────────────────┐
│ SENTIMIENTO GENERAL: 78% Positivo   │
├─────────────────────────────────────┤
│ ASPECTOS:                           │
│ • Rapidez: 85% positivo ✅          │
│ • Calidad comida: 72% positivo ✅   │
│ • Empaque: 90% positivo ✅          │
│ • Precio: 45% positivo ⚠️           │
│ • App: 68% positivo ✅              │
└─────────────────────────────────────┘

ALERTAS AUTOMÁTICAS cuando:
- Cualquier aspecto cae <50% positivo
```

**PREGUNTA:**
¿Qué combinación de servicios Azure necesitan?

A) Sentiment Analysis (documento) + Azure Monitor para alertas  
B) Opinion Mining + Stream Analytics + Power BI para dashboard + Logic Apps para alertas  
C) Solo Question Answering con knowledge base de reseñas  
D) Named Entity Recognition + Sentiment Analysis  

<details>
<summary>👉 Ver respuesta y explicación</summary>

**RESPUESTA CORRECTA: B) Opinion Mining + Stream Analytics + Power BI para dashboard + Logic Apps para alertas**

**EXPLICACIÓN DETALLADA:**

```
ARQUITECTURA COMPLETA:

1. OPINION MINING (Azure AI Language):
   Input: Reseñas de clientes
   Output: Targets + Sentiments
   
   Ejemplo:
   "Rapidez excelente pero muy caro"
   → Target: Rapidez, Sentiment: POSITIVE
   → Target: Precio, Sentiment: NEGATIVE

2. STREAM ANALYTICS:
   Procesa reseñas en tiempo real
   Calcula estadísticas agregadas
   
   Query ejemplo:
   SELECT 
     Target,
     COUNT(*) as Total,
     SUM(CASE WHEN Sentiment='positive' THEN 1 END) / COUNT(*) as PositiveRate
   FROM ReviewStream
   GROUP BY Target, TumblingWindow(minute, 5)

3. POWER BI:
   Visualización del dashboard
   Actualización en tiempo real
   Gráficos por aspecto

4. LOGIC APPS:
   Monitorea métricas
   Dispara alertas cuando PositiveRate < 0.50
   Notifica a equipo via email/Teams
```

**FLUJO COMPLETO:**

```
TIEMPO REAL:

09:00 AM - Reseña nueva:
"Entrega rápida pero la comida llegó fría"

↓ Opinion Mining procesa
Target: Entrega → POSITIVE
Target: Comida → NEGATIVE

↓ Stream Analytics agrega
Calidad Comida: ahora 48% positivo (bajó de 72%)

↓ Logic App detecta
48% < 50% → TRIGGER ALERT

↓ Notificación
Email a gerente de cocina:
"⚠️ ALERTA: Calidad comida cayó a 48%"

↓ Dashboard actualiza
Power BI muestra gráfico en rojo
```

**Por qué las otras son incorrectas:**

- **A)** Sentiment Analysis solo da sentimiento general, NO por aspecto
  
- **C)** Question Answering NO hace análisis de sentimiento; solo responde preguntas de KB

- **D)** NER + Sentiment NO identifica targets de opinión (como "rapidez", "precio")

**COMPONENTES CRÍTICOS:**

```
¿POR QUÉ NECESITAS CADA SERVICIO?

OPINION MINING:
→ Sin esto, no puedes desglosar por aspecto
→ Sentiment solo daría tono general

STREAM ANALYTICS:
→ Sin esto, no puedes procesar tiempo real
→ No puedes agregar estadísticas dinámicas

POWER BI:
→ Sin esto, no tienes dashboard visual
→ Podrías usar otra herramienta de BI

LOGIC APPS:
→ Sin esto, no hay alertas automáticas
→ Podrías usar Azure Functions también
```

**TIP PARA EL EXAMEN:**
"Dashboard en tiempo real con desglose por aspectos" = Opinion Mining + herramientas de streaming y visualización

</details>

---

## 📊 SECCIÓN 2: EXTRACCIÓN DE INFORMACIÓN (8 preguntas)

### Pregunta 11 - Key Phrases vs NER en Indexación
**DIFICULTAD: 🟡 Media**

**ESCENARIO:**
Una biblioteca digital tiene 100,000 artículos académicos. Quieren dos sistemas de búsqueda diferentes:

**SISTEMA A:** Búsqueda por tema/concepto
- Usuario busca: "inteligencia artificial"
- Devuelve: Artículos donde IA es tema principal

**SISTEMA B:** Búsqueda por persona/organización
- Usuario busca: "Microsoft"
- Devuelve: Artículos que mencionan Microsoft específicamente

**PREGUNTA:**
¿Qué servicios deben usar para cada sistema?

A) Ambos usan Key Phrase Extraction  
B) Ambos usan Named Entity Recognition  
C) Sistema A: Key Phrase Extraction; Sistema B: Named Entity Recognition  
D) Sistema A: Sentiment Analysis; Sistema B: Key Phrase Extraction  

<details>
<summary>👉 Ver respuesta y explicación</summary>

**RESPUESTA CORRECTA: C) Sistema A: Key Phrase Extraction; Sistema B: Named Entity Recognition**

**EXPLICACIÓN DETALLADA:**

```
SISTEMA A - BÚSQUEDA POR TEMA:

Artículo ejemplo:
"Este paper explora machine learning aplicado a medicina.
Específicamente, analizamos redes neuronales para diagnóstico
de enfermedades cardíacas."

KEY PHRASE EXTRACTION detecta:
✅ "machine learning"
✅ "medicina"
✅ "redes neuronales"
✅ "diagnóstico"
✅ "enfermedades cardíacas"

Usuario busca: "machine learning medicina"
→ Este artículo aparece (tema match) ✅
```

```
SISTEMA B - BÚSQUEDA POR ENTIDAD:

Artículo ejemplo:
"El estudio fue realizado en colaboración con Microsoft Research
y la Universidad de Stanford. Los datos se procesaron usando Azure."

NER detecta:
✅ Microsoft Research (Organization)
✅ Universidad de Stanford (Organization)
✅ Azure (Product)

Usuario busca: "Microsoft"
→ Este artículo aparece (entidad match) ✅
```

**DIFERENCIA CLAVE:**

```
KEY PHRASES (conceptos generales):
- "inteligencia artificial" (tema)
- "cambio climático" (tema)
- "política económica" (tema)
→ PARA: Clasificación temática

NER (entidades específicas):
- "Microsoft" (organización)
- "Bill Gates" (persona)
- "Seattle" (lugar)
→ PARA: Referencias específicas
```

**CASO REAL:**

```
BÚSQUEDA: "inteligencia artificial"

CON KEY PHRASES:
Encuentra artículos donde "IA" es tema central
→ 5,000 resultados relevantes ✅

CON NER:
Solo encuentra si "Inteligencia Artificial" 
es nombre de organización/producto
→ 50 resultados (mayormente falsos positivos) ❌

CONCLUSIÓN:
Key Phrases mejor para temas
NER mejor para entidades nombradas
```

**Por qué las otras son incorrectas:**
- **A)** Key Phrases NO es óptimo para nombres de organizaciones
- **B)** NER NO es óptimo para conceptos generales
- **D)** Sentiment Analysis no ayuda en búsqueda de contenido

**TIP PARA EL EXAMEN:**
```
¿BUSCAR POR QUÉ? → Key Phrase Extraction
¿BUSCAR POR QUIÉN/DÓNDE? → Named Entity Recognition
```

</details>

---

### Pregunta 12 - PII Detection con Redacción
**DIFICULTAD: 🟡 Media**

**ESCENARIO:**
Un hospital debe publicar transcripciones anonimizadas de consultas para investigación médica. Tienen esta transcripción:

```
"Paciente: Juan Pérez, DNI 12345678A, edad 45 años.
Dirección: Calle Mayor 123, Madrid.
Email: juan.perez@email.com
Diagnóstico: Hipertensión arterial con presión 140/90.
Prescripción: Enalapril 10mg, seguimiento en 3 meses."
```

**PREGUNTA:**
Quieren publicar: mantener información médica pero eliminar datos identificables. ¿Qué configuración de PII Detection necesitan?

A) Detectar y redactar todas las entidades incluyendo diagnóstico  
B) Detectar Person, ID, Address, Email pero NO redactar términos médicos  
C) Solo usar Sentiment Analysis  
D) No pueden usar PII Detection porque es español  

<details>
<summary>👉 Ver respuesta y explicación</summary>

**RESPUESTA CORRECTA: B) Detectar Person, ID, Address, Email pero NO redactar términos médicos**

**EXPLICACIÓN DETALLADA:**

```
CONFIGURACIÓN DE PII DETECTION:

piiCategories: [
  "Person",           // Juan Pérez
  "SpainIdentityCard", // 12345678A
  "Address",          // Calle Mayor 123
  "Email"             // juan.perez@email.com
]

NO INCLUIR:
❌ Términos médicos (no son PII)
❌ Edad (puede ser relevante para investigación)
❌ Medicamentos (información médica necesaria)
```

**RESULTADO DE REDACCIÓN:**

```
TEXTO ORIGINAL:
"Paciente: Juan Pérez, DNI 12345678A, edad 45 años.
Dirección: Calle Mayor 123, Madrid.
Email: juan.perez@email.com
Diagnóstico: Hipertensión arterial con presión 140/90.
Prescripción: Enalapril 10mg, seguimiento en 3 meses."

TEXTO REDACTADO:
"Paciente: [PERSON], DNI [ID], edad 45 años.
Dirección: [ADDRESS], Madrid.
Email: [EMAIL]
Diagnóstico: Hipertensión arterial con presión 140/90.
Prescripción: Enalapril 10mg, seguimiento en 3 meses."
```

**UTILIDAD PARA INVESTIGACIÓN:**

```
DATOS PRESERVADOS (útiles):
✅ Edad: 45 años
✅ Ubicación general: Madrid
✅ Diagnóstico: Hipertensión arterial
✅ Presión: 140/90
✅ Tratamiento: Enalapril 10mg
✅ Timeline: seguimiento 3 meses

DATOS REMOVIDOS (identificables):
❌ Nombre específico
❌ DNI
❌ Dirección exacta
❌ Email

RESULTADO:
Investigadores pueden analizar patrones médicos
SIN poder identificar pacientes individuales ✅
```

**HIPAA COMPLIANCE:**

```
HIPAA requiere eliminar 18 tipos de identificadores:
1. Nombres ✅
2. Direcciones (más específico que ciudad/estado) ✅
3. Fechas (excepto año)
4. Números de teléfono ✅
5. Números de seguridad social ✅
6. Números de historia clínica ✅
7. Email ✅
...

PII Detection de Azure cubre estos tipos
→ Facilita compliance automático
```

**Por qué las otras son incorrectas:**
- **A)** NO deben redactar diagnóstico; es información médica necesaria
- **C)** Sentiment Analysis NO detecta ni redacta PII
- **D)** PII Detection SÍ funciona en español

**CONFIGURACIÓN ADICIONAL POSIBLE:**

```
Si necesitan MÁS privacidad:

OPCIÓN 1 - Generalizar edad:
"45 años" → "40-50 años"

OPCIÓN 2 - Generalizar ubicación:
"Madrid" → "Comunidad de Madrid"

OPCIÓN 3 - Usar IDs de investigación:
[PERSON] → "PARTICIPANT_001"
```

**TIP PARA EL EXAMEN:**
PII Detection es CONFIGURABLE - puedes elegir QUÉ categorías detectar/redactar según tus necesidades de compliance vs utilidad de datos.

</details>

---

[Continúo con las preguntas restantes...]

---

**¿Te sigo generando las 30 preguntas restantes (Pregunta 13-40)?**

Este banco está diseñado para:
- ✅ Casos más realistas y complejos
- ✅ Escenarios empresariales verdaderos
- ✅ Mayor profundidad en explicaciones
- ✅ Dificultad progresiva

**Ya tienes 12 preguntas completas. ¿Quieres que continúe con las otras 28?** 🎯
