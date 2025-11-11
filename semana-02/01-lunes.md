# 📚 SEMANA 2 - MACHINE LEARNING EN PROFUNDIDAD

---

## 📖 LUNES 10 NOV (1.5 horas) - Tipos de ML en profundidad

### 🎯 Objetivo del día

Dominar completamente los tipos de Machine Learning y saber cuándo usar cada uno

---

## 🔄 REPASO RÁPIDO: ¿Qué es Machine Learning?

**Machine Learning es:**
Enseñar a las computadoras a aprender de datos sin programar explícitamente cada regla.

**En la Semana 1 viste:**

- ✅ Los 3 tipos básicos: Supervisado, No supervisado, Refuerzo
- ✅ Diferencia entre Regresión y Clasificación
- ✅ Qué es Clustering

**Esta semana profundizaremos en cada uno.**

---

## 🧠 LOS 3 TIPOS DE MACHINE LEARNING (PROFUNDO)

```
MACHINE LEARNING
│
├── 1. SUPERVISADO (Supervised Learning)
│   ├── Regresión (predecir números)
│   └── Clasificación (predecir categorías)
│
├── 2. NO SUPERVISADO (Unsupervised Learning)
│   ├── Clustering (agrupar similares)
│   └── Dimensionality Reduction (simplificar datos)
│
└── 3. REFUERZO (Reinforcement Learning)
    └── Aprender por prueba y error
```

---

## 📊 1. SUPERVISED LEARNING (Aprendizaje Supervisado)

### 🎯 Concepto clave:

**Aprende con un "profesor" que le da las respuestas correctas.**

**Analogía:**
Como estudiar con un libro que tiene las soluciones al final. Haces ejercicios, miras las respuestas, aprendes de tus errores.

---

### 📋 Características del Supervisado:

✅ **Tienes datos CON etiquetas (respuestas conocidas)**

- Ejemplo: 10,000 emails etiquetados "spam" o "no spam"

✅ **El algoritmo aprende la relación entre datos y respuestas**

- Ejemplo: Aprende qué características hacen que un email sea spam

✅ **Después puede predecir respuestas para datos nuevos**

- Ejemplo: Recibe email nuevo → predice "spam" o "no spam"

✅ **Es el tipo MÁS común en la industria**

- 80% de los proyectos de ML usan supervisado

---

### 🎯 Los 2 sub-tipos: REGRESIÓN vs CLASIFICACIÓN

#### 📈 REGRESIÓN (Regression)

**¿Qué predice?** NÚMEROS continuos

**Pregunta que responde:** "¿CUÁNTO?" o "¿QUÉ VALOR?"

**Ejemplos:**

1. Predecir el **precio** de una casa → $250,000
2. Predecir la **temperatura** de mañana → 25°C
3. Predecir las **ventas** del próximo mes → 15,340 unidades
4. Predecir cuánto **tiempo** tardará un envío → 3.5 días
5. Predecir la **edad** de una persona en una foto → 32 años

**Datos de entrada (features):**

- Para precio de casa: tamaño (m²), ubicación, habitaciones, año construcción
- Para temperatura: temperatura actual, humedad, presión, histórico
- Para ventas: ventas pasadas, promociones, temporada, competencia

**Salida:** Un número en un rango continuo

---

**Algoritmos comunes de Regresión:**

- Linear Regression (regresión lineal)
- Decision Tree Regression
- Random Forest Regression
- Neural Networks (para problemas complejos)

**Para el examen:** NO necesitas saber los algoritmos en detalle, solo QUÉ es regresión y CUÁNDO usarla.

---

#### 🏷️ CLASIFICACIÓN (Classification)

**¿Qué predice?** CATEGORÍAS o ETIQUETAS discretas

**Pregunta que responde:** "¿A QUÉ GRUPO pertenece?"

**Ejemplos:**

1. ¿Este email es **spam** o **no spam**? → 2 categorías (binaria)
2. ¿Este tumor es **benigno** o **maligno**? → 2 categorías (binaria)
3. ¿Esta flor es **setosa**, **versicolor** o **virginica**? → 3 categorías (multiclase)
4. ¿Este cliente va a **comprar** o **no comprar**? → 2 categorías (binaria)
5. ¿Esta imagen muestra un **gato**, **perro** o **pájaro**? → 3 categorías (multiclase)

**Datos de entrada (features):**

- Para spam: palabras del email, remitente, enlaces, mayúsculas
- Para tumor: tamaño, forma, textura, crecimiento
- Para flor: longitud pétalo, ancho pétalo, longitud sépalo, ancho sépalo

**Salida:** Una categoría/etiqueta

---

**Tipos de Clasificación:**

**1. Clasificación Binaria (2 categorías):**

- Spam / No spam
- Fraude / No fraude
- Enfermo / Sano
- Compra / No compra

**2. Clasificación Multiclase (3+ categorías):**

- Perro / Gato / Pájaro
- Alta / Media / Baja prioridad
- Norte / Sur / Este / Oeste

**3. Clasificación Multilabel (múltiples etiquetas simultáneas):**

- Una imagen puede ser: ["exterior", "naturaleza", "montaña", "nieve"]
- Para el examen: menos importante, solo mencionar que existe

---

**Algoritmos comunes de Clasificación:**

- Logistic Regression (sí, se llama "regression" pero es clasificación)
- Decision Trees
- Random Forest
- Support Vector Machines (SVM)
- Neural Networks

**Para el examen:** NO necesitas saber los algoritmos, solo QUÉ es clasificación y CUÁNDO usarla.

---

### 🎯 REGRESIÓN vs CLASIFICACIÓN: La diferencia clave

| Aspecto       | REGRESIÓN                   | CLASIFICACIÓN                         |
| ------------- | --------------------------- | ------------------------------------- |
| **Predice**   | Números continuos           | Categorías discretas                  |
| **Pregunta**  | "¿Cuánto?"                  | "¿Cuál?"                              |
| **Salida**    | $250,000                    | "Spam"                                |
| **Rango**     | Infinito (cualquier número) | Finito (categorías fijas)             |
| **Ejemplo 1** | Precio de casa              | Tipo de casa (apartamento/casa/villa) |
| **Ejemplo 2** | Temperatura en °C           | Clima (soleado/nublado/lluvioso)      |
| **Ejemplo 3** | Edad exacta (32 años)       | Grupo de edad (joven/adulto/senior)   |

---

### 💡 TRUCO para identificar:

**Pregúntate:** "¿La respuesta es un número en un rango continuo?"

✅ **SÍ** → Es REGRESIÓN

- Precio: $100, $150.50, $200.99... (infinitas posibilidades)
- Temperatura: 20°C, 20.5°C, 20.51°C... (infinitas posibilidades)

❌ **NO** → Es CLASIFICACIÓN

- Spam/No spam (solo 2 opciones)
- Gato/Perro/Pájaro (solo 3 opciones)

---

### 📝 EJERCICIO 1: Regresión o Clasificación (10 min)

**Para cada problema, identifica: ¿Regresión o Clasificación?**

1. Predecir cuántos días tardará en llegar un paquete
   - Tipo: **\*\***\_**\*\***
   - Por qué: **\*\***\_**\*\***

2. Determinar si una transacción es fraudulenta o legítima
   - Tipo: **\*\***\_**\*\***
   - Por qué: **\*\***\_**\*\***

3. Estimar el salario de una persona según su experiencia y educación
   - Tipo: **\*\***\_**\*\***
   - Por qué: **\*\***\_**\*\***

4. Clasificar películas en: acción, comedia, drama, terror
   - Tipo: **\*\***\_**\*\***
   - Por qué: **\*\***\_**\*\***

5. Predecir cuántas unidades se venderán el próximo mes
   - Tipo: **\*\***\_**\*\***
   - Por qué: **\*\***\_**\*\***

6. Determinar si un cliente está satisfecho, neutral o insatisfecho
   - Tipo: **\*\***\_**\*\***
   - Por qué: **\*\***\_**\*\***

7. Predecir el precio de acciones de Apple mañana
   - Tipo: **\*\***\_**\*\***
   - Por qué: **\*\***\_**\*\***

8. Identificar si una imagen contiene un rostro humano o no
   - Tipo: **\*\***\_**\*\***
   - Por qué: **\*\***\_**\*\***

9. Estimar cuántos kilómetros puede recorrer un coche con un tanque lleno
   - Tipo: **\*\***\_**\*\***
   - Por qué: **\*\***\_**\*\***

10. Clasificar correos en: trabajo, personal, promociones, spam
    - Tipo: **\*\***\_**\*\***
    - Por qué: **\*\***\_**\*\***

**Respuestas al final del documento**

---

## 🔍 2. UNSUPERVISED LEARNING (Aprendizaje No Supervisado)

### 🎯 Concepto clave:

**Aprende SIN un "profesor". Busca patrones por su cuenta.**

**Analogía:**
Como organizar tu armario sin instrucciones. TÚ decides qué va con qué (agrupar camisetas, pantalones, ropa de invierno, etc.) basándote en similitudes que observas.

---

### 📋 Características del No Supervisado:

✅ **Tienes datos SIN etiquetas (sin respuestas)**

- Ejemplo: 10,000 registros de clientes pero sin categorías definidas

❌ **NO le dices qué buscar**

- El algoritmo decide qué patrones son importantes

✅ **Descubre estructura oculta en los datos**

- Ejemplo: Agrupa clientes similares automáticamente

✅ **Útil para exploración de datos**

- "¿Qué patrones hay aquí que no conozco?"

---

### 🎯 Tipos principales de No Supervisado:

#### 1️⃣ CLUSTERING (Agrupamiento)

**¿Qué hace?** Agrupa datos similares en "clusters" (grupos)

**Pregunta que responde:** "¿Qué cosas son parecidas?"

**Ejemplos:**

**1. Segmentación de clientes:**

- Entrada: Datos de 10,000 clientes (edad, compras, navegación)
- SIN decirle cuántos grupos hay
- Salida: El algoritmo encuentra 4 grupos:
  - Grupo 1: Jóvenes compradores frecuentes de tecnología
  - Grupo 2: Familias que compran juguetes
  - Grupo 3: Profesionales que compran ropa formal
  - Grupo 4: Seniors que compran productos de salud

**2. Organización de documentos:**

- Entrada: 1,000 artículos de noticias sin categorizar
- Salida: Agrupa automáticamente en temas:
  - Deportes
  - Política
  - Tecnología
  - Entretenimiento

**3. Detección de anomalías:**

- Agrupa transacciones "normales"
- Las que NO encajan en ningún grupo → posible fraude

---

**Algoritmos comunes de Clustering:**

- **K-Means:** El más común, define K grupos
- **Hierarchical Clustering:** Crea árbol de grupos
- **DBSCAN:** Encuentra grupos de densidad

**Para el examen:** Solo necesitas saber QUÉ es clustering y ejemplos.

---

#### 2️⃣ DIMENSIONALITY REDUCTION (Reducción de Dimensionalidad)

**¿Qué hace?** Simplifica datos complejos manteniendo info importante

**Problema que resuelve:**
Tienes datos con 100 columnas (features), pero trabajar con tantas es difícil y lento.

**Solución:**
Reduce a 10 columnas principales que capturan la mayor parte de la información.

**Ejemplo:**

- Tienes 1,000 fotos de productos (cada pixel es una columna = miles de columnas)
- Reduce a 50 características principales
- Más rápido de procesar, misma información

**Algoritmos:**

- PCA (Principal Component Analysis) - el más común

**Para el examen:** Menos importante que clustering, solo saber que existe.

---

### 🎯 SUPERVISADO vs NO SUPERVISADO: Comparación

| Aspecto        | SUPERVISADO                           | NO SUPERVISADO              |
| -------------- | ------------------------------------- | --------------------------- |
| **Datos**      | Con etiquetas (respuestas)            | Sin etiquetas               |
| **Objetivo**   | Predecir respuestas para datos nuevos | Descubrir patrones ocultos  |
| **Pregunta**   | "¿Cuál es la respuesta?"              | "¿Qué estructura hay aquí?" |
| **Ejemplo**    | Predecir si email es spam             | Agrupar emails similares    |
| **Uso común**  | 80% de proyectos ML                   | 20% de proyectos ML         |
| **Evaluación** | Fácil (compara con respuestas reales) | Difícil (no hay "correcta") |

---

### 📝 EJERCICIO 2: Supervisado o No Supervisado (10 min)

**Para cada caso, identifica el tipo de ML:**

1. Tienes 5,000 clientes con datos de edad, compras y navegación. Quieres agruparlos en segmentos para marketing personalizado, pero NO sabes cuántos grupos hay ni qué características tienen.
   - Tipo: **\*\***\_**\*\***
   - Por qué: **\*\***\_**\*\***

2. Tienes 50,000 emails etiquetados como "spam" o "no spam". Quieres entrenar un modelo para clasificar emails nuevos.
   - Tipo: **\*\***\_**\*\***
   - Subtipo: **\*\***\_**\*\***

3. Tienes datos de 100,000 transacciones bancarias SIN etiquetar. Quieres encontrar grupos de comportamiento similar para detectar patrones inusuales.
   - Tipo: **\*\***\_**\*\***
   - Por qué: **\*\***\_**\*\***

4. Tienes histórico de 10 años de ventas mensuales con promociones, temporada, etc. Quieres predecir ventas del próximo mes.
   - Tipo: **\*\***\_**\*\***
   - Subtipo: **\*\***\_**\*\***

5. Tienes 20,000 artículos de noticias SIN categorizar. Quieres organizarlos automáticamente en temas.
   - Tipo: **\*\***\_**\*\***
   - Por qué: **\*\***\_**\*\***

**Respuestas al final del documento**

---

## 🎮 3. REINFORCEMENT LEARNING (Aprendizaje por Refuerzo)

### 🎯 Concepto clave:

**Aprende por PRUEBA Y ERROR con sistema de recompensas y castigos.**

**Analogía:**
Como entrenar a un perro:

- Hace algo bien → golosina (recompensa) 🦴
- Hace algo mal → nada (castigo)
- Aprende qué acciones maximizan las recompensas

---

### 📋 Características del Refuerzo:

✅ **Aprende de la experiencia**

- No le das ejemplos con respuestas
- Prueba acciones y ve qué pasa

✅ **Recibe feedback (recompensas/castigos)**

- Acción buena → +puntos
- Acción mala → -puntos

✅ **Objetivo: maximizar recompensas totales**

- No solo la recompensa inmediata, sino a largo plazo

✅ **Aprende una "política" (estrategia)**

- En situación X, hacer acción Y

---

### 💡 Ejemplos reales:

**1. AlphaGo (Google DeepMind)**

- Juega millones de partidas de Go contra sí mismo
- Gana → recompensa
- Pierde → castigo
- Aprendió a vencer al campeón mundial

**2. Coches autónomos**

- Conduce en simulación
- Llega bien al destino → recompensa
- Choca → castigo grande
- Aprende a conducir seguro

**3. Robots industriales**

- Robot aprende a ensamblar piezas
- Ensamblaje correcto → recompensa
- Pieza mal colocada → castigo
- Optimiza velocidad y precisión

**4. Videojuegos**

- Bot aprende a jugar Mario Bros
- Avanzar → recompensa pequeña
- Conseguir moneda → recompensa media
- Completar nivel → recompensa grande
- Morir → castigo grande

**5. Optimización de centros de datos**

- Google usa RL para enfriar data centers
- Reduce temperatura con menos energía → recompensa
- Aprende configuración óptima

---

### ⚠️ IMPORTANTE para el examen:

**Reinforcement Learning:**

- ✅ Conoce QUÉ es y ejemplos
- ✅ Sabe que aprende por prueba y error
- ✅ Sistema de recompensas/castigos
- ❌ NO necesitas saber algoritmos (Q-Learning, etc.)
- ❌ NO es el foco principal del AI-900
- ⚠️ Aparece brevemente en el examen (~2-3 preguntas máximo)

---

## 📊 TABLA COMPARATIVA COMPLETA

| Tipo                            | Datos                      | Objetivo              | Cómo aprende                            | Ejemplo              |
| ------------------------------- | -------------------------- | --------------------- | --------------------------------------- | -------------------- |
| **Supervisado - Regresión**     | Con etiquetas (números)    | Predecir números      | De ejemplos con respuestas              | Predecir precio casa |
| **Supervisado - Clasificación** | Con etiquetas (categorías) | Predecir categorías   | De ejemplos con respuestas              | Detectar spam        |
| **No Supervisado - Clustering** | Sin etiquetas              | Agrupar similares     | Buscando patrones                       | Segmentar clientes   |
| **No Supervisado - Reducción**  | Sin etiquetas              | Simplificar datos     | Encontrando principales características | PCA de imágenes      |
| **Refuerzo**                    | De experiencia             | Maximizar recompensas | Prueba y error                          | AlphaGo, robots      |

---

## 🎯 DECISION TREE: ¿Qué tipo de ML usar?

```
┌─ ¿Tienes datos con RESPUESTAS/ETIQUETAS conocidas?
│
├─ SÍ → SUPERVISADO
│  │
│  ├─ ¿La respuesta es un NÚMERO continuo?
│  │  ├─ SÍ → REGRESIÓN
│  │  │      Ejemplo: Predecir precio, temperatura, ventas
│  │  │
│  │  └─ NO → CLASIFICACIÓN
│  │         Ejemplo: Spam/No spam, Gato/Perro
│  │
│
├─ NO → ¿Quieres AGRUPAR datos similares?
│  │
│  ├─ SÍ → NO SUPERVISADO (Clustering)
│  │      Ejemplo: Segmentar clientes
│  │
│  └─ NO → ¿Es un problema de DECISIONES SECUENCIALES?
│         │
│         ├─ SÍ → REFUERZO
│         │      Ejemplo: Entrenar robot, juegos
│         │
│         └─ NO → Probablemente NO SUPERVISADO
│                (Reducción de dimensionalidad)
```

---

## 📝 EJERCICIO 3: Identificación completa (15 min)

**Para cada caso, identifica:**
a) Tipo de ML
b) Subtipo (si aplica)
c) Por qué

---

**Caso 1:**
Netflix quiere predecir qué calificación (1-5 estrellas) dará un usuario a una película que aún no ha visto, basándose en sus calificaciones anteriores.

a) Tipo: **\*\***\_**\*\***
b) Subtipo: **\*\***\_**\*\***
c) Por qué: **\*\***\_\*\*\*\*\*\*

---

**Caso 2:**
Una empresa tiene 50,000 artículos en su inventario sin categorizar. Quiere organizarlos automáticamente en grupos de productos similares.

a) Tipo: **\*\***\_**\*\***
b) Subtipo: **\*\***\_**\*\***
c) Por qué: **\*\***\_**\*\***

---

**Caso 3:**
Un hospital quiere predecir si un paciente tiene alto, medio o bajo riesgo de diabetes basándose en análisis de sangre y datos históricos de 10,000 pacientes diagnosticados.

a) Tipo: **\*\***\_**\*\***
b) Subtipo: **\*\***\_**\*\***
c) Por qué: **\*\***\_**\*\***

---

**Caso 4:**
Una startup está entrenando un robot para que aprenda a jugar ajedrez jugando millones de partidas y recibiendo puntos por ganar.

a) Tipo: **\*\***\_**\*\***
b) Subtipo: **\*\***\_**\*\***
c) Por qué: **\*\***\_**\*\***

---

**Caso 5:**
Spotify tiene datos de 100 millones de canciones sin etiquetar. Quiere agruparlas automáticamente en géneros basándose en características de audio.

a) Tipo: **\*\***\_**\*\***
b) Subtipo: **\*\***\_**\*\***
c) Por qué: **\*\***\_**\*\***

---

## ✅ TAREAS DE HOY (Lunes)

### 1. Microsoft Learn (45 min)

**Módulos a completar:**

- **"Fundamentos del aprendizaje automático"**
- **"Exploración de conceptos de aprendizaje automático"**
- **"Identificación de técnicas comunes de ML"**

Link: https://learn.microsoft.com/es-es/training/paths/get-started-with-artificial-intelligence-on-azure/

---

### 2. Completa los 3 ejercicios (30 min)

- Ejercicio 1: Regresión o Clasificación (10 min)
- Ejercicio 2: Supervisado o No Supervisado (10 min)
- Ejercicio 3: Identificación completa (10 min)

---

### 3. Crea Flashcards (15 min)

**Crea estas 15 tarjetas:**

**Tarjeta 1:**

- Frente: "¿Qué tipo de ML usa datos CON etiquetas/respuestas?"
- Atrás: "Supervisado (Supervised Learning)"

**Tarjeta 2:**

- Frente: "¿Qué tipo de ML predice NÚMEROS continuos?"
- Atrás: "Supervisado - Regresión"

**Tarjeta 3:**

- Frente: "¿Qué tipo de ML predice CATEGORÍAS?"
- Atrás: "Supervisado - Clasificación"

**Tarjeta 4:**

- Frente: "Ejemplo de Regresión"
- Atrás: "Predecir precio de casa ($250,000), temperatura (25°C), ventas (15,340 unidades)"

**Tarjeta 5:**

- Frente: "Ejemplo de Clasificación"
- Atrás: "Spam/No spam, Gato/Perro, Fraude/No fraude"

**Tarjeta 6:**

- Frente: "¿Qué tipo de ML usa datos SIN etiquetas?"
- Atrás: "No Supervisado (Unsupervised Learning)"

**Tarjeta 7:**

- Frente: "¿Qué hace Clustering?"
- Atrás: "Agrupa datos similares en grupos (clusters) sin decirle cuáles son los grupos"

**Tarjeta 8:**

- Frente: "Ejemplo de Clustering"
- Atrás: "Segmentar clientes en grupos similares, organizar artículos por temas"

**Tarjeta 9:**

- Frente: "¿Qué tipo de ML aprende por prueba y error?"
- Atrás: "Reinforcement Learning (Aprendizaje por Refuerzo)"

**Tarjeta 10:**

- Frente: "Ejemplo de Reinforcement Learning"
- Atrás: "AlphaGo jugando Go, robots aprendiendo tareas, coches autónomos"

**Tarjeta 11:**

- Frente: "Diferencia clave: Regresión vs Clasificación"
- Atrás: "Regresión = números continuos (precio). Clasificación = categorías discretas (spam/no spam)"

**Tarjeta 12:**

- Frente: "Diferencia: Supervisado vs No Supervisado"
- Atrás: "Supervisado = CON respuestas conocidas. No Supervisado = SIN respuestas, busca patrones"

**Tarjeta 13:**

- Frente: "¿Cuándo usar Regresión?"
- Atrás: "Cuando necesito predecir un NÚMERO: precio, temperatura, cantidad, tiempo, edad"

**Tarjeta 14:**

- Frente: "¿Cuándo usar Clasificación?"
- Atrás: "Cuando necesito predecir una CATEGORÍA: spam/no spam, tipo de producto, diagnóstico"

**Tarjeta 15:**

- Frente: "¿Cuándo usar Clustering?"
- Atrás: "Cuando tengo datos sin etiquetar y quiero encontrar grupos similares automáticamente"

---

## 📝 CONCEPTOS CLAVE DEL LUNES

**Memoriza:**

- Los 3 tipos de ML: Supervisado, No Supervisado, Refuerzo
- Supervisado tiene 2 subtipos: Regresión y Clasificación
- Regresión = números, Clasificación = categorías
- No Supervisado: Clustering agrupa similares
- Refuerzo: aprende por prueba y error
- La mayoría de proyectos usa Supervisado (~80%)

---

## 🎓 PREGUNTAS TIPO EXAMEN

### Pregunta 1:

**Una empresa quiere predecir cuántos productos venderá el próximo trimestre basándose en datos históricos de ventas, promociones y temporada. ¿Qué tipo de técnica de machine learning debería usar?**

A) Clasificación
B) Regresión ✅
C) Clustering
D) Reinforcement learning

**Por qué B:** Predecir una CANTIDAD (número de productos) = Regresión

---

### Pregunta 2:

**Un banco tiene datos históricos de 50,000 préstamos con información sobre si cada préstamo fue pagado completamente o no. Quieren entrenar un modelo para predecir si nuevos solicitantes pagarán su préstamo. ¿Qué tipo de machine learning es este?**

A) Regresión supervisada
B) Clasificación supervisada ✅
C) Clustering no supervisado
D) Reinforcement learning

**Por qué B:** Predice CATEGORÍA (pagará / no pagará) con datos históricos CON respuestas = Clasificación supervisada

---

### Pregunta 3:

**Una empresa de retail tiene datos de comportamiento de 100,000 clientes pero NO tiene categorías definidas. Quieren descubrir automáticamente grupos de clientes con comportamientos similares. ¿Qué técnica deberían usar?**

A) Clasificación supervisada
B) Regresión supervisada
C) Clustering no supervisado ✅
D) Reinforcement learning

**Por qué C:** Datos SIN etiquetas + quieren agrupar similares = Clustering no supervisado

---

### Pregunta 4:

**¿Cuál es la diferencia principal entre regresión y clasificación?**

A) Regresión usa más datos que clasificación
B) Regresión predice números continuos, clasificación predice categorías discretas ✅
C) Regresión es más rápida que clasificación
D) Regresión necesita más memoria que clasificación

**Por qué B:** La diferencia fundamental es el tipo de salida: número vs categoría

---

### Pregunta 5:

**Un sistema aprende a jugar videojuegos jugando miles de partidas, recibiendo puntos por ganar y perdiendo puntos por perder. ¿Qué tipo de machine learning es este?**

A) Supervisado
B) No supervisado
C) Reinforcement learning ✅
D) Clasificación

**Por qué C:** Aprende por prueba y error con sistema de recompensas = Refuerzo

---

## 📊 TABLA PARA DECIDIR QUÉ USAR

### Usa esta tabla cuando enfrentes un problema:

| Si necesitas...                            | Usa...                    | Ejemplo                        |
| ------------------------------------------ | ------------------------- | ------------------------------ |
| Predecir un NÚMERO                         | Regresión supervisada     | Precio, temperatura, ventas    |
| Predecir una CATEGORÍA (y tienes ejemplos) | Clasificación supervisada | Spam/no spam, fraude/no fraude |
| AGRUPAR cosas similares (sin etiquetas)    | Clustering no supervisado | Segmentar clientes             |
| Sistema que aprende de EXPERIENCIA         | Reinforcement learning    | Robots, juegos, trading        |
| Simplificar datos complejos                | Dimensionality reduction  | PCA para visualización         |

---

## ✅ CHECKLIST LUNES

- [ ] Entiendo perfectamente los 3 tipos de ML
- [ ] Sé la diferencia entre Regresión y Clasificación
- [ ] Puedo dar ejemplos de cada tipo
- [ ] Sé cuándo usar cada tipo de ML
- [ ] Completé los 3 ejercicios
- [ ] Creé 15 flashcards nuevas
- [ ] Repasé flashcards de Semana 1 (10 min)
- [ ] Puedo explicar cada tipo en voz alta

---

## 📚 RESPUESTAS A LOS EJERCICIOS

### EJERCICIO 1: Regresión o Clasificación

1. **Días para llegar un paquete:** Regresión
   - Por qué: Predice un NÚMERO (3 días, 5.5 días, etc.)

2. **Transacción fraudulenta o legítima:** Clasificación
   - Por qué: Predice una CATEGORÍA (fraude / no fraude)

3. **Estimar salario:** Regresión
   - Por qué: Predice un NÚMERO ($45,000, $60,500, etc.)

4. **Clasificar películas:** Clasificación
   - Por qué: Predice una CATEGORÍA (acción, comedia, drama, terror)

5. **Unidades a vender:** Regresión
   - Por qué: Predice un NÚMERO (15,340 unidades)

6. **Satisfacción del cliente:** Clasificación
   - Por qué: Predice una CATEGORÍA (satisfecho / neutral / insatisfecho)

7. **Precio de acciones:** Regresión
   - Por qué: Predice un NÚMERO ($150.25, $151.00, etc.)

8. **Contiene rostro o no:** Clasificación
   - Por qué: Predice una CATEGORÍA (sí / no)

9. **Kilómetros con tanque lleno:** Regresión
   - Por qué: Predice un NÚMERO (450 km, 520 km, etc.)

10. **Clasificar correos:** Clasificación
    - Por qué: Predice una CATEGORÍA (trabajo / personal / promociones / spam)

---

### EJERCICIO 2: Supervisado o No Supervisado

1. **Agrupar clientes sin saber grupos:** No Supervisado (Clustering)
   - Por qué: NO tienes etiquetas, quieres descubrir grupos automáticamente

2. **Clasificar emails spam:** Supervisado (Clasificación)
   - Por qué: Tienes emails CON etiquetas (spam/no spam)

3. **Encontrar patrones en transacciones:** No Supervisado (Clustering)
   - Por qué: Datos SIN etiquetar, buscas patrones ocultos

4. **Predecir ventas futuras:** Supervisado (Regresión)
   - Por qué: Tienes histórico CON valores conocidos, predices un número

5. **Organizar artículos en temas:** No Supervisado (Clustering)
   - Por qué: Artículos SIN categorizar, quieres agrupar por similitud

---

### EJERCICIO 3: Identificación completa

**Caso 1 (Netflix calificaciones):**

- a) Supervisado
- b) Regresión
- c) Predice un NÚMERO (1-5 estrellas) con datos históricos CON respuestas conocidas

**Caso 2 (Inventario sin categorizar):**

- a) No Supervisado
- b) Clustering
- c) Datos SIN etiquetas, quiere agrupar productos similares automáticamente

**Caso 3 (Riesgo diabetes):**

- a) Supervisado
- b) Clasificación (multiclase)
- c) Predice CATEGORÍA (alto/medio/bajo) con datos históricos CON diagnósticos conocidos

**Caso 4 (Robot jugando ajedrez):**

- a) Reinforcement Learning
- b) N/A
- c) Aprende por prueba y error, recibe recompensas por ganar partidas

**Caso 5 (Spotify agrupar canciones):**

- a) No Supervisado
- b) Clustering
- c) Canciones SIN etiquetar por género, agrupa automáticamente por características similares

---

## 🎊 ¡EXCELENTE TRABAJO EN EL LUNES!

**Lo que has logrado hoy:**

✅ **Dominas los 3 tipos de ML en profundidad**

- Supervisado (Regresión y Clasificación)
- No Supervisado (Clustering)
- Refuerzo

✅ **Sabes CUÁNDO usar cada tipo**

- Decision tree mental
- Ejemplos claros de cada uno

✅ **Puedes identificar el tipo correcto en situaciones reales**

- 15+ ejercicios completados
- Práctica con casos reales

✅ **Entiendes la diferencia clave: Regresión vs Clasificación**

- Números vs Categorías
- Ejemplos concretos

---

## 📅 MAÑANA (Martes):

**Tema:** Regresión y sus métricas en detalle

- RMSE, MAE, R² - ¿qué significan?
- Cómo saber si un modelo de regresión es bueno
- Interpretar resultados
- Ejemplos prácticos

**Prepárate para:** Conceptos un poco más técnicos, pero con ejemplos claros

---

## 💡 ANTES DE TERMINAR HOY

**Repaso mental rápido (5 min):**

Cierra los ojos y visualiza:

- Los 3 tipos de ML como un árbol
- Ejemplos concretos de cada uno
- ¿Cuándo usarías cada tipo?

**Repasa tus flashcards nuevas 2 veces**

**Autoevaluación:**
¿Puedo explicar en voz alta la diferencia entre Regresión y Clasificación?

- Si SÍ → ¡Perfecto! Estás listo para mañana
- Si NO → Repasa la sección de Regresión vs Clasificación 5 min más

---

**¡Descansa bien! Mañana profundizamos en Regresión.** 💪🚀

---

## 📊 PROGRESO SEMANA 2

```
Lunes:     ████████████████████ 100% ✅
Martes:    ░░░░░░░░░░░░░░░░░░░░   0%
Miércoles: ░░░░░░░░░░░░░░░░░░░░   0%
Jueves:    ░░░░░░░░░░░░░░░░░░░░   0%
Viernes:   ░░░░░░░░░░░░░░░░░░░░   0%
Sábado:    ░░░░░░░░░░░░░░░░░░░░   0%
```

**Horas Semana 2:** 1.5/10 horas completadas (15%) ✅
**Progreso Total:** 11.5/60 horas (19.2%) 📈
