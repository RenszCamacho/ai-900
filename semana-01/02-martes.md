## 📖 MARTES (1.5 horas) - Tipos de IA y Machine Learning

### 🎯 Objetivo del día

Entender los diferentes tipos de Machine Learning y cuándo usar cada uno

---

### 🧠 LOS 3 TIPOS DE MACHINE LEARNING

#### 1️⃣ SUPERVISADO = Aprender con profesor 👨‍🏫

**¿Qué es?**
Le das ejercicios CON las respuestas correctas. La máquina aprende de ejemplos etiquetados.

**Analogía:**
Como estudiar con un libro que tiene las soluciones al final. Haces ejercicios, miras la respuesta, aprendes del error.

**Ejemplos reales:**

- **Filtro de spam:** Le muestras emails etiquetados "spam" o "no spam"
- **Reconocer perros vs gatos:** Le das fotos etiquetadas "perro" o "gato"
- **Predecir precios de casas:** Le das casas con sus precios reales

**Dos sub-tipos importantes:**

**A) REGRESIÓN** → Predecir NÚMEROS

- Predecir precio de una casa: $250,000
- Predecir temperatura mañana: 25°C
- Predecir ventas del mes: 15,340 unidades

**B) CLASIFICACIÓN** → Predecir CATEGORÍAS

- ¿Es spam o no spam?
- ¿Es perro, gato o pájaro?
- ¿Cliente comprará o no comprará?

---

#### 2️⃣ NO SUPERVISADO = Aprender solo 🔍

**¿Qué es?**
Le das datos SIN respuestas. La máquina busca patrones por su cuenta.

**Analogía:**
Como organizar tu armario sin instrucciones. Tú decides qué va con qué (agrupar camisetas, pantalones, etc.)

**Ejemplo real: CLUSTERING (Agrupación)**

- **Segmentar clientes:** La IA agrupa clientes similares sin que tú le digas quiénes son similares
  - Grupo 1: Jóvenes que compran tecnología
  - Grupo 2: Familias que compran juguetes
  - Grupo 3: Profesionales que compran ropa formal
- **Recomendaciones de música:** Spotify agrupa canciones similares

**Diferencia clave con supervisado:**

- Supervisado: "Esto ES un perro" (tú le dices)
- No supervisado: "Encuentra grupos de animales parecidos" (él decide)

---

#### 3️⃣ POR REFUERZO = Aprender jugando 🎮

**¿Qué es?**
Aprende por prueba y error. Recibe recompensas por buenas acciones y castigos por malas.

**Analogía:**
Como entrenar a un perro con premios. Hace algo bien → golosina. Hace algo mal → nada.

**Ejemplos reales:**

- **AlphaGo:** Aprendió a jugar Go jugando millones de partidas
- **Coches autónomos:** Aprenden a conducir practicando (simulaciones)
- **Videojuegos:** Bots que aprenden a jugar solos

**Para el examen:** Este tipo se menciona pero no es tan importante como los otros dos.

---

### 📊 COMPARACIÓN VISUAL

```
┌─────────────────────┬──────────────────┬─────────────────────┐
│   SUPERVISADO       │  NO SUPERVISADO  │   REFUERZO          │
├─────────────────────┼──────────────────┼─────────────────────┤
│ Con respuestas      │ Sin respuestas   │ Prueba y error      │
│ "Esto ES un gato"   │ "Busca grupos"   │ "Premio/castigo"    │
│ Ejemplo: Spam       │ Ejemplo: Cluster │ Ejemplo: AlphaGo    │
└─────────────────────┴──────────────────┴─────────────────────┘
```

---

### 🎯 CUADRO RESUMEN (¡Memoriza esto!)

| Tipo                            | ¿Qué hace?          | Ejemplo cotidiano           |
| ------------------------------- | ------------------- | --------------------------- |
| **Supervisado - Regresión**     | Predecir números    | Precio de casa, temperatura |
| **Supervisado - Clasificación** | Predecir categorías | Spam/no spam, perro/gato    |
| **No supervisado - Clustering** | Agrupar similares   | Segmentar clientes          |
| **Refuerzo**                    | Aprender jugando    | Videojuegos, robots         |

---

### ✅ TAREAS DE HOY (Martes)

#### 1. Microsoft Learn (60 min)

**Módulos a completar:**

- **"Fundamentos del aprendizaje automático"**
- **"¿Qué es el aprendizaje automático?"**

[Empieza con la Inteligencia Artificial en Azure](https://learn.microsoft.com/es-es/training/paths/get-started-with-artificial-intelligence-on-azure/)

**TIP:** Si un módulo tiene 45 min estimados, a ti te tomará 60 min. Es normal al principio.

---

#### 2. Ejercicio: Identifica el tipo de ML (20 min)

**Para cada situación, identifica qué tipo de ML usarías:**

**Situación 1:** Quieres que tu app prediga cuántos días tardará en llegar un paquete.

- Tipo: **\*\***\_\_\_**\*\***
- ¿Por qué?: **\*\***\_\_\_**\*\***

**Situación 2:** Tienes 50,000 clientes y quieres agruparlos en categorías similares, pero no sabes cuáles.

- Tipo: **\*\***\_\_\_**\*\***
- ¿Por qué?: **\*\***\_\_\_**\*\***

**Situación 3:** Quieres clasificar emails automáticamente en "trabajo", "personal" o "spam".

- Tipo: **\*\***\_\_\_**\*\***
- ¿Por qué?: **\*\***\_\_\_**\*\***

**Situación 4:** Quieres predecir si un cliente comprará o no comprará tu producto.

- Tipo: **\*\***\_\_\_**\*\***
- ¿Por qué?: **\*\***\_\_\_**\*\***

**Situación 5:** Necesitas predecir el precio de un coche usado basándote en su marca, año y kilometraje.

- Tipo: **\*\***\_\_\_**\*\***
- ¿Por qué?: **\*\***\_\_\_**\*\***

---

#### 3. Crea Flashcards en Anki (10 min)

**Crea estas 8 tarjetas:**

**Tarjeta 1:**

- Frente: "¿Qué es Machine Learning?"
- Atrás: "Enseñar a computadoras a aprender de datos sin programar cada regla"

**Tarjeta 2:**

- Frente: "¿Qué tipo de ML usa datos CON respuestas?"
- Atrás: "Supervisado (Supervised Learning)"

**Tarjeta 3:**

- Frente: "¿Qué tipo de ML predice NÚMEROS?"
- Atrás: "Regresión (ejemplo: precio de casa, temperatura)"

**Tarjeta 4:**

- Frente: "¿Qué tipo de ML predice CATEGORÍAS?"
- Atrás: "Clasificación (ejemplo: spam/no spam, gato/perro)"

**Tarjeta 5:**

- Frente: "¿Qué tipo de ML agrupa datos similares SIN respuestas previas?"
- Atrás: "No supervisado - Clustering"

**Tarjeta 6:**

- Frente: "Ejemplo de Regresión"
- Atrás: "Predecir precio de casas, temperatura, ventas (números continuos)"

**Tarjeta 7:**

- Frente: "Ejemplo de Clasificación"
- Atrás: "Detectar spam, reconocer perros/gatos, diagnóstico médico (categorías)"

**Tarjeta 8:**

- Frente: "Diferencia: Supervisado vs No supervisado"
- Atrás: "Supervisado = tienes respuestas (etiquetas). No supervisado = no tienes respuestas (busca patrones solo)"

---

### 📝 CONCEPTOS CLAVE DEL MARTES

**Memoriza estos:**

- **Supervisado:** Aprender CON respuestas
- **No supervisado:** Aprender SIN respuestas
- **Regresión:** Predecir NÚMEROS (ej: precio)
- **Clasificación:** Predecir CATEGORÍAS (ej: spam/no spam)
- **Clustering:** Agrupar cosas similares
- **Refuerzo:** Aprender por prueba y error

---

### 💡 AUTOEVALUACIÓN (5 min)

**Explícate a ti mismo en VOZ ALTA (sí, en voz alta):**

1. ¿Qué es Machine Learning supervisado? Dame un ejemplo
2. ¿Cuál es la diferencia entre regresión y clasificación?
3. ¿Cuándo usarías clustering?
4. ¿Puedes predecir el precio de un coche con clasificación? ¿Por qué sí o no?

**Si puedes explicarlo en voz alta, LO ENTENDISTE. Si no, repasa esa parte.**

---

### 🎯 EJERCICIO EXTRA (Opcional - 10 min)

**Piensa en tu trabajo o vida diaria:**

1. Identifica 2 problemas que podrías resolver con **Regresión**:
   - Ejemplo: Predecir cuánto gastaré en supermercado este mes
   - Tu ejemplo 1: **\*\***\_\_\_**\*\***
   - Tu ejemplo 2: **\*\***\_\_\_**\*\***

2. Identifica 2 problemas que podrías resolver con **Clasificación**:
   - Ejemplo: Clasificar mis emails automáticamente
   - Tu ejemplo 1: **\*\***\_\_\_**\*\***
   - Tu ejemplo 2: **\*\***\_\_\_**\*\***

---

### ✅ CHECKLIST MARTES

- [ ] Leí módulos de Microsoft Learn sobre ML
- [ ] Entiendo los 3 tipos de ML (supervisado, no supervisado, refuerzo)
- [ ] Sé la diferencia entre regresión y clasificación
- [ ] Resolví el ejercicio de identificar tipos de ML
- [ ] Creé 8 flashcards en Anki
- [ ] Me autoevalué en voz alta
- [ ] Repasé flashcards del lunes (5 min)

---

### 📚 RESPUESTAS AL EJERCICIO (no mires antes de intentarlo)

**Situación 1 (días del paquete):** Regresión supervisada

- Por qué: Predice un NÚMERO (días)

**Situación 2 (agrupar clientes):** No supervisado - Clustering

- Por qué: No sabes las categorías, la IA las descubre

**Situación 3 (clasificar emails):** Clasificación supervisada

- Por qué: Predice CATEGORÍAS (trabajo/personal/spam)

**Situación 4 (comprará o no):** Clasificación supervisada

- Por qué: Predice CATEGORÍA (sí/no = 2 categorías)

**Situación 5 (precio coche usado):** Regresión supervisada

- Por qué: Predice un NÚMERO (precio)

---

### 🎊 FINAL DEL MARTES

**¡Bien hecho!** Ya entiendes los fundamentos de ML. Mañana veremos Azure.

**Antes de dormir:**

- Repasa tus flashcards 5 minutos
- Piensa en qué tipo de ML usan tus apps favoritas

**Nos vemos mañana miércoles para crear tu cuenta de Azure 🚀**

---

## 📊 PROGRESO SEMANA 1

```
Lunes:   ████████████████████ 100% ✅
Martes:  ████████████████████ 100% ✅
Miércoles: ░░░░░░░░░░░░░░░░░░░░   0%
Jueves:    ░░░░░░░░░░░░░░░░░░░░   0%
Viernes:   ░░░░░░░░░░░░░░░░░░░░   0%
Sábado:    ░░░░░░░░░░░░░░░░░░░░   0%
```

**Total Semana 1:** 2/10 horas completadas (20%) 💪
