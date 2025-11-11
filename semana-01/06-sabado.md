## 💻 SÁBADO 8 NOV (2.5 horas) - Primer Lab de Exploración

### 🎯 Objetivo del día

Experimentar con herramientas reales de Azure AI y consolidar aprendizaje práctico

---

### 🚀 PREPARACIÓN (10 min)

**Antes de empezar:**

1. **Asegúrate de tener:**
   - ✅ Tu cuenta de Azure creada y funcionando
   - ✅ Acceso a portal.azure.com
   - ✅ Navegador actualizado (Chrome o Edge recomendados)
   - ✅ Conexión a internet estable
   - ✅ 2.5 horas sin interrupciones

2. **Mentalidad correcta:**
   - 🎮 Esto es EXPLORACIÓN, no un examen
   - ✅ No hay respuestas incorrectas
   - 🔍 La idea es PROBAR y EXPERIMENTAR
   - 📝 Documenta lo que veas con capturas de pantalla
   - ❓ Anota lo que no entiendas para investigar después

3. **Estructura del lab:**
   - 50 min: Computer Vision
   - 50 min: Language (NLP)
   - 30 min: Speech
   - 20 min: Reflexión y documentación

---

## 🎨 PARTE 1: COMPUTER VISION (50 min)

### 🖼️ Lab 1A: Azure AI Vision Studio (25 min)

**Paso 1: Acceder a Vision Studio**

1. Ve a: https://portal.vision.cognitive.azure.com/
2. O desde Azure Portal busca "Vision Studio"
3. Inicia sesión con tu cuenta de Azure
4. Selecciona tu suscripción

**Paso 2: Explorar Image Analysis**

**Tarea 1: Analizar imágenes generales (10 min)**

1. En Vision Studio, ve a "Image Analysis"
2. Busca "Analyze images" o "Caption images"
3. Usa las imágenes de ejemplo PRIMERO
4. Observa:
   - ¿Qué descripción genera?
   - ¿Qué objetos detecta?
   - ¿Qué tags genera?
   - ¿Qué colores identifica?

**Tarea 2: Tus propias imágenes (15 min)**
Sube 5 imágenes diferentes (de tu teléfono, Google, etc.):

1. **Una foto con personas:** ¿Detecta cuántas personas?
2. **Una foto de comida:** ¿La describe correctamente?
3. **Una foto de un paisaje:** ¿Identifica elementos naturales?
4. **Una foto con texto visible:** ¿Lo menciona?
5. **Una foto abstracta o rara:** ¿Cómo la interpreta?

**Documenta:**
📸 Toma screenshots de los resultados
✏️ Anota:

- ¿Qué tan precisa fue la descripción?
- ¿Qué detectó bien?
- ¿Qué NO detectó o interpretó mal?
- ¿Te sorprendió algo?

---

### 📄 Lab 1B: OCR - Leer texto en imágenes (15 min)

**Paso 1: Ir a OCR/Read**

1. En Vision Studio, busca "Optical character recognition"
2. Selecciona "Extract text from images"

**Paso 2: Probar con diferentes tipos de documentos**

**Prueba 1: Documento limpio**

- Sube una captura de pantalla de un documento Word o PDF
- Observa: ¿Detecta todo el texto correctamente?

**Prueba 2: Foto de un recibo**

- Toma foto de un recibo de compra o ticket
- Sube la foto
- ¿Detecta números, fechas, precios?

**Prueba 3: Texto manuscrito**

- Escribe algo a mano, toma foto
- ¿Puede leerlo?

**Prueba 4: Texto en ángulo o con mala calidad**

- Foto inclinada de un libro
- ¿Aún puede leerlo?

**Documenta:**
📸 Screenshots de cada prueba
✏️ Anota:

- Precisión del OCR en cada caso
- ¿En qué situaciones funciona mejor/peor?
- Casos de uso reales que se te ocurran

---

### 😊 Lab 1C: Face Detection (10 min - opcional)

**Nota:** Face API puede estar restringido. Si no tienes acceso, SÁLTATE esta parte.

**Si tienes acceso:**

1. Busca "Face" en Vision Studio
2. Prueba "Detect faces in an image"
3. Sube 2-3 fotos con caras
4. Observa:
   - ¿Detecta todas las caras?
   - ¿Qué atributos identifica? (edad aproximada, emoción, etc.)
   - ¿Qué tan preciso es?

**Documenta:**

- Precisión de la detección
- Si estima edad/emoción, ¿es preciso?

---

## 📝 PARTE 2: LANGUAGE (NLP) (50 min)

### 💬 Lab 2A: Azure AI Language Studio (50 min)

**Paso 1: Acceder a Language Studio**

1. Ve a: https://language.cognitive.azure.com/
2. O desde Azure Portal busca "Language Studio"
3. Inicia sesión
4. Selecciona tu suscripción

---

### 😊😐😠 Lab 2B: Sentiment Analysis (15 min)

**Paso 1: Ir a Sentiment Analysis**

1. En Language Studio, busca "Analyze sentiment and opinions"
2. Prueba con el texto de ejemplo primero

**Paso 2: Analizar diferentes tipos de textos**

**Prueba con estos 5 textos (o similares):**

**Texto 1 - Muy positivo:**

```
"¡Me encantó este producto! Superó todas mis expectativas.
La calidad es excepcional y el servicio al cliente fue
maravilloso. Lo recomiendo 100%."
```

- Resultado esperado: Positivo (score alto ~0.9)

**Texto 2 - Muy negativo:**

```
"Pésima experiencia. El producto llegó roto y el servicio
al cliente fue horrible. No respondieron mis mensajes.
Nunca más compro aquí. Una estafa total."
```

- Resultado esperado: Negativo (score bajo ~0.1)

**Texto 3 - Neutral:**

```
"El paquete llegó el martes. El producto es de color azul.
Mide aproximadamente 30 centímetros. Cumple con la descripción."
```

- Resultado esperado: Neutral (score ~0.5)

**Texto 4 - Mixto:**

```
"El producto es bueno y la calidad es aceptable, pero
el envío tardó demasiado y el empaque estaba dañado.
Por el precio esperaba más."
```

- Resultado esperado: Mixto (detecta sentimientos positivos y negativos)

**Texto 5 - Encuentra una reseña real:**

- Ve a Amazon, Google Reviews, TripAdvisor
- Copia una reseña real de 3-4 líneas
- Analízala

**Documenta:**
📸 Screenshot de cada resultado
✏️ Anota:

- ¿El sentimiento detectado es correcto?
- ¿Los scores parecen precisos?
- ¿En qué casos funciona mejor/peor?

---

### 🔑 Lab 2C: Key Phrase Extraction (10 min)

**Paso 1: Ir a Key Phrase Extraction**

1. En Language Studio, busca "Extract key phrases"

**Paso 2: Probar con diferentes textos**

**Prueba 1 - Artículo corto:**

```
"El cambio climático es uno de los mayores desafíos del siglo XXI.
Las emisiones de gases de efecto invernadero están aumentando
las temperaturas globales. Los gobiernos deben tomar medidas
urgentes para promover energías renovables y reducir la dependencia
de combustibles fósiles."
```

**Observa:** ¿Qué frases clave extrae?

- Esperado: "cambio climático", "gases de efecto invernadero", "energías renovables", etc.

**Prueba 2 - Encuentra un artículo de noticias:**

- Busca una noticia reciente (3-4 párrafos)
- Cópiala y analízala
- ¿Identifica los temas principales?

**Documenta:**

- ¿Las frases clave son relevantes?
- ¿Falta alguna frase importante?

---

### 🏷️ Lab 2D: Named Entity Recognition (NER) (15 min)

**Paso 1: Ir a NER**

1. En Language Studio, busca "Recognize named entities"

**Paso 2: Probar con diferentes textos**

**Prueba 1 - Texto con muchas entidades:**

```
"María García viajó a París el 15 de octubre de 2024.
Trabajó durante 5 años en Microsoft antes de fundar su
propia startup en Barcelona. Su empresa, TechSolutions SA,
recibió una inversión de 2 millones de euros del Banco
Santander. Puede contactarse en maria@techsolutions.com
o llamar al +34 600 123 456."
```

**Observa qué detecta:**

- 👤 Personas: María García
- 📍 Lugares: París, Barcelona
- 📅 Fechas: 15 de octubre de 2024
- 🏢 Organizaciones: Microsoft, TechSolutions SA, Banco Santander
- 💰 Cantidades: 2 millones de euros, 5 años
- 📧 Información de contacto: email, teléfono

**Prueba 2 - Encuentra un texto real:**

- Artículo de noticias
- Biografía de alguien
- Descripción de evento

**Documenta:**
📸 Screenshot coloreado (muestra las categorías)
✏️ Anota:

- ¿Detectó todas las entidades?
- ¿Alguna entidad mal categorizada?
- ¿Falta alguna?

---

### 🌍 Lab 2E: Language Detection (10 min)

**Paso 1: Ir a Language Detection**

1. Busca "Detect language"

**Paso 2: Probar con diferentes idiomas**

**Prueba estos textos:**

1. **Español:** "Hola, ¿cómo estás? Espero que tengas un buen día."
2. **Inglés:** "Hello, how are you? I hope you have a great day."
3. **Francés:** "Bonjour, comment allez-vous? J'espère que vous passez une bonne journée."
4. **Alemán:** "Hallo, wie geht es dir? Ich hoffe, du hast einen schönen Tag."
5. **Mixto:** "Hello amigo, comment ça va? Ich bin muy feliz."

**Observa:**

- ¿Detecta correctamente cada idioma?
- En el texto mixto, ¿qué idioma predominante detecta?
- Score de confianza

**Documenta:**

- Precisión de detección
- Idiomas que soporta

---

## 🔊 PARTE 3: SPEECH SERVICES (30 min)

### 🎤 Lab 3A: Speech Studio (30 min)

**Paso 1: Acceder a Speech Studio**

1. Ve a: https://speech.microsoft.com/
2. O desde Azure Portal busca "Speech Studio"
3. Inicia sesión

---

### 🎙️ Lab 3B: Speech-to-Text (15 min)

**Paso 1: Ir a Speech-to-Text**

1. En Speech Studio, busca "Real-time speech-to-text"

**Paso 2: Probar transcripción**

**Prueba 1: Grabación clara**

- Graba 30 segundos hablando claramente sobre cualquier tema
- Ejemplo: "Hola, mi nombre es [tu nombre]. Hoy es sábado y estoy probando los servicios de Azure Speech. Estoy aprendiendo sobre inteligencia artificial para obtener la certificación AI-900."
- Transcribe
- ¿Qué tan preciso fue?

**Prueba 2: Grabación con ruido**

- Pon música de fondo
- Graba hablando
- ¿Sigue siendo preciso?

**Prueba 3: Hablar rápido**

- Habla muy rápido 20 segundos
- ¿Captura todo?

**Prueba 4: Con acentos o muletillas**

- Habla con muchos "ehhh", "este", "o sea"
- ¿Los incluye en la transcripción?

**Documenta:**

- Precisión en cada caso
- Errores comunes
- Puntuación automática

---

### 🔊 Lab 3C: Text-to-Speech (15 min)

**Paso 1: Ir a Text-to-Speech**

1. Busca "Text-to-speech" o "Audio Content Creation"

**Paso 2: Probar diferentes voces**

**Texto de prueba:**

```
"Bienvenido a los servicios de inteligencia artificial de Azure.
Hoy estamos probando la conversión de texto a voz. Esta tecnología
permite crear experiencias de audio naturales y personalizadas."
```

**Pruebas:**

**Prueba 1: Diferentes voces en español**

- Prueba 2-3 voces diferentes (masculinas y femeninas)
- ¿Cuál suena más natural?

**Prueba 2: Diferentes idiomas**

- Convierte texto en inglés
- Convierte texto en francés
- Compara naturalidad

**Prueba 3: Ajustar velocidad**

- Prueba el mismo texto:
  - Velocidad lenta (0.75x)
  - Velocidad normal (1x)
  - Velocidad rápida (1.25x)

**Prueba 4: SSML (opcional si hay tiempo)**

- Speech Synthesis Markup Language
- Permite controlar pronunciación, pausas, énfasis
- Prueba ejemplo disponible en Studio

**Documenta:**

- Qué voces suenan más naturales
- Casos de uso que se te ocurren
- Calidad general

---

## 📊 PARTE 4: REFLEXIÓN Y DOCUMENTACIÓN (20 min)

### ✍️ Documenta tu experiencia

**Crea un documento con:**

#### 1. Computer Vision - Lo que descubrí:

```
Image Analysis:
- Precisión general: [alta/media/baja]
- Lo que me sorprendió: [escribe]
- Posibles casos de uso: [lista 3]

OCR:
- Funciona mejor con: [tipo de documentos]
- Funciona peor con: [situaciones]
- Casos de uso reales: [lista 3]
```

#### 2. Language (NLP) - Lo que descubrí:

```
Sentiment Analysis:
- Precisión: [observaciones]
- Casos donde falla: [si notaste alguno]
- Casos de uso: [lista 3]

Key Phrases:
- ¿Identifica bien los temas principales? [sí/no/a veces]
- Casos de uso: [lista 2]

NER:
- ¿Qué entidades detecta mejor?
- Casos de uso: [lista 3]
```

#### 3. Speech - Lo que descubrí:

```
Speech-to-Text:
- Precisión con voz clara: [%]
- Precisión con ruido: [%]
- Casos de uso: [lista 3]

Text-to-Speech:
- Voz más natural: [cuál]
- Calidad general: [opinión]
- Casos de uso: [lista 3]
```

#### 4. Aprendizajes generales:

```
Lo más impresionante:
[Escribe]

Lo que menos me convenció:
[Escribe]

Algo que no entendí y necesito investigar:
[Escribe]

3 ideas de proyectos que podría hacer con estas herramientas:
1. [idea]
2. [idea]
3. [idea]
```

---

### 🎯 Conexión con la teoría

**Relaciona lo que viste con conceptos de la semana:**

**Pregúntate:**

1. ¿Estos servicios usan ML supervisado o no supervisado?
   - Sentiment Analysis probablemente fue entrenado con... [completa]
2. ¿Image Analysis usa clasificación o regresión?
   - [Piensa y responde]

3. ¿Qué ventaja tiene usar estos servicios vs entrenar tu propio modelo?
   - [Escribe tu opinión]

4. De los servicios que probaste, ¿cuáles usarías en tu trabajo/vida?
   - [Lista y explica]

---

### 💡 Mini investigación (opcional - 10 min extra)

**Si tienes tiempo, investiga:**

1. **Casos de uso reales:** Busca empresas que usen estos servicios
   - ¿Cómo usa Duolingo Speech-to-Text?
   - ¿Qué empresas usan Sentiment Analysis para analizar redes sociales?

2. **Limitaciones:** Busca artículos sobre limitaciones
   - "Computer Vision fails examples"
   - "Sentiment Analysis errors"
   - ¿En qué situaciones fallan estas IA?

3. **Pricing:** Ve a la documentación de Azure
   - ¿Cuánto cuesta cada servicio?
   - ¿Qué nivel gratuito tienen?
   - ¿Cómo se cobra? (por llamada, por token, etc.)

---

## ✅ CHECKLIST SÁBADO

### Labs completados:

- [ ] Vision Studio - Image Analysis (5 imágenes probadas)
- [ ] Vision Studio - OCR (4 tipos de documentos probados)
- [ ] Vision Studio - Face Detection (opcional, si tuviste acceso)
- [ ] Language Studio - Sentiment Analysis (5 textos diferentes)
- [ ] Language Studio - Key Phrase Extraction (2 textos)
- [ ] Language Studio - Named Entity Recognition (2 textos)
- [ ] Language Studio - Language Detection (5 idiomas)
- [ ] Speech Studio - Speech-to-Text (4 pruebas diferentes)
- [ ] Speech Studio - Text-to-Speech (diferentes voces e idiomas)

### Documentación:

- [ ] Tomé screenshots de los resultados
- [ ] Documenté lo que funcionó bien/mal
- [ ] Anoté casos de uso reales
- [ ] Relacioné práctica con teoría
- [ ] Identifiqué qué servicios me interesan más

### Reflexión:

- [ ] Entiendo mejor para qué sirve cada servicio
- [ ] Vi ejemplos concretos de IA en acción
- [ ] Tengo ideas de aplicaciones reales
- [ ] Sé qué servicios explorar más a fondo

---

## 🎊 ¡FELICIDADES POR COMPLETAR LA SEMANA 1!

**Lo que has logrado:**

### 📚 Conocimiento teórico:

✅ Entiendes qué es IA y Machine Learning
✅ Conoces los 3 tipos de ML (supervisado, no supervisado, refuerzo)
✅ Sabes la diferencia entre regresión y clasificación
✅ Conoces Azure y su ecosistema
✅ Conoces los 5 grupos de servicios de Azure AI
✅ Entiendes cuándo usar cada servicio

### 💻 Experiencia práctica:

✅ Creaste tu cuenta de Azure
✅ Navegaste Azure Portal
✅ Exploraste Vision Studio
✅ Exploraste Language Studio
✅ Exploraste Speech Studio
✅ Probaste 9+ servicios diferentes de IA
✅ Viste IA en acción con ejemplos reales

### 🎯 Habilidades desarrolladas:

✅ Identificar qué tipo de ML usar para cada problema
✅ Identificar qué servicio de Azure usar para cada necesidad
✅ Analizar imágenes con IA
✅ Analizar texto con IA
✅ Trabajar con servicios de voz
✅ Documentar tus aprendizajes
✅ Relacionar teoría con práctica

---

## 📊 PROGRESO SEMANA 1 - COMPLETADO

```
Lunes:     ████████████████████ 100% ✅
Martes:    ████████████████████ 100% ✅
Miércoles: ████████████████████ 100% ✅
Jueves:    ████████████████████ 100% ✅
Viernes:   ████████████████████ 100% ✅
Sábado:    ████████████████████ 100% ✅
Domingo:   DESCANSO 😴
```

**Horas invertidas esta semana:** ~10 horas ✅
**Flashcards creadas:** ~30-40 tarjetas ✅
**Labs completados:** 9+ ejercicios prácticos ✅

---

## 🌟 EVALUACIÓN DE LA SEMANA 1

### Autoevaluación final:

**Responde honestamente (1-5, donde 5 es máximo):**

1. **Entiendo qué es IA y ML:** \_\_\_/5
2. **Sé la diferencia entre supervisado y no supervisado:** \_\_\_/5
3. **Entiendo regresión vs clasificación:** \_\_\_/5
4. **Conozco los servicios de Azure AI:** \_\_\_/5
5. **Sé cuándo usar cada servicio:** \_\_\_/5
6. **Me siento cómodo con Azure Portal:** \_\_\_/5
7. **Entiendo Computer Vision:** \_\_\_/5
8. **Entiendo Language/NLP:** \_\_\_/5
9. **Entiendo Speech services:** \_\_\_/5
10. **Confío en que aprobaré el examen:** \_\_\_/5

**Total: \_\_\_/50**

**Interpretación:**

- ✅ **40-50 puntos:** ¡Excelente! Estás listo para Semana 2
- ⚠️ **30-39 puntos:** Bien, pero repasa áreas con puntaje bajo antes de continuar
- ❌ **<30 puntos:** Dedica el domingo a repasar antes de empezar Semana 2

---

## 🎯 ÁREAS A MEJORAR PARA SEMANA 2

**Basándote en tu autoevaluación, identifica:**

**Mis 3 áreas más fuertes:**

1. ***
2. ***
3. ***

**Mis 3 áreas más débiles:**

1. ***
2. ***
3. ***

**Qué haré para mejorar mis áreas débiles:**

- Área 1: [acción concreta]
- Área 2: [acción concreta]
- Área 3: [acción concreta]

---

## 📅 PREPARACIÓN PARA SEMANA 2

### ¿Qué viene la próxima semana?

**SEMANA 2: Machine Learning en profundidad**

- Lunes 10 Nov: Tipos de ML profundo
- Martes 11 Nov: Regresión y métricas (RMSE, R²)
- Miércoles 12 Nov: Clasificación y métricas (Accuracy, Precision, Recall)
- Jueves 13 Nov: Azure ML workspace en detalle
- Viernes 14 Nov: Automated ML (AutoML)
- Sábado 15 Nov: LAB - Crear tu primer modelo real

**Conceptos clave que verás:**

- Métricas de evaluación de modelos
- Overfitting y underfitting
- Train/Test split
- Azure Machine Learning en profundidad
- Crear un modelo de ML desde cero

**Será más técnico, pero:**

- Tendrás más práctica
- Los conceptos base ya los conoces
- Habrá ejemplos visuales
- Crearás un modelo real

---

## 🏆 LOGRO DESBLOQUEADO

```
╔════════════════════════════════════╗
║                                    ║
║    🎓 SEMANA 1 COMPLETADA 🎓      ║
║                                    ║
║   Fundamentos de IA dominados      ║
║   Azure AI Services explorados     ║
║   +30 flashcards creadas          ║
║   +9 labs completados             ║
║                                    ║
║        ⭐⭐⭐⭐⭐                    ║
║                                    ║
║   Progreso total: 16.7%            ║
║   (1 de 6 semanas)                 ║
║                                    ║
╚════════════════════════════════════╝
```

---

## 💤 DOMINGO 9 NOV - DESCANSO

### 🎯 Objetivo del día

**DESCANSAR** y consolidar conocimientos sin estudiar activamente

---

### ✅ Lo que SÍ puedes hacer (máximo 30 min total):

**Repaso ligero de flashcards (15 min):**

- Abre Anki
- Repasa las flashcards que te salgan
- NO crees nuevas flashcards
- NO estudies contenido nuevo

**Revisar tus screenshots y documentación (15 min):**

- Mira las capturas del sábado
- Lee tu documentación del viernes
- Reflexiona sobre lo aprendido
- NO tomes notas nuevas

---

### ❌ Lo que NO debes hacer hoy:

- ❌ Estudiar contenido nuevo
- ❌ Ver videos educativos de Azure
- ❌ Hacer más labs
- ❌ Leer documentación técnica
- ❌ Preocuparte por el examen
- ❌ Sentirte culpable por no estudiar

---

### ✅ Lo que DEBES hacer hoy:

**Actividades recomendadas:**

- 🎬 Ver una película o serie
- �책 Leer un libro (no técnico)
- 🚶 Salir a caminar
- 👨‍👩‍👧 Pasar tiempo con familia/amigos
- 🎮 Jugar videojuegos
- 🧘 Meditar o hacer ejercicio
- 😴 Dormir una siesta
- 🍳 Cocinar algo rico
- 🎨 Hacer un hobby que disfrutes

**Por qué es importante el descanso:**

- 🧠 Tu cerebro consolida el aprendizaje mientras descansas
- 💪 Previene burnout
- 📈 Mejora la retención a largo plazo
- 😊 Mantiene la motivación
- ⚡ Llegarás con energía a la Semana 2

---

### 🌙 Antes de dormir (5 min):

**Reflexión rápida:**

- ¿Qué fue lo más interesante de la semana?
- ¿De qué estoy orgulloso?
- ¿Estoy listo para la Semana 2?

**Visualización positiva:**

- Cierra los ojos 2 minutos
- Visualízate aprobando el examen
- Imagina cómo te sentirás
- Sonríe

**Prepara el lunes:**

- Asegúrate de que tu espacio de estudio esté listo
- Deja preparado lo que necesitarás
- Mentalidad: "Mañana empiezo Semana 2 con energía"

---

## 🎯 RESUMEN SEMANA 1

### 📈 Progreso hacia AI-900:

```
Semana 1: Fundamentos ████████████░░░░░░░░░░░░ 100%
Semana 2: ML profundo ░░░░░░░░░░░░░░░░░░░░░░░░  0%
Semana 3: Vision      ░░░░░░░░░░░░░░░░░░░░░░░░  0%
Semana 4: NLP         ░░░░░░░░░░░░░░░░░░░░░░░░  0%
Semana 5: GenAI       ░░░░░░░░░░░░░░░░░░░░░░░░  0%
Semana 6: Examen      ░░░░░░░░░░░░░░░░░░░░░░░░  0%

PROGRESO TOTAL: ████░░░░░░░░░░░░░░░░░░░░ 16.7%
```

**Tiempo invertido:** 10/60 horas totales
**Semanas restantes:** 5 semanas
**Días hasta el examen:** ~37 días

---

### 📚 Lo que dominas ahora:

**Conceptos fundamentales:**
✅ Definición de IA y ML
✅ Tipos de Machine Learning
✅ Diferencia regresión vs clasificación
✅ Clustering básico
✅ Qué es Azure y cómo funciona

**Servicios de Azure AI:**
✅ Panorama general de todos los servicios
✅ Cuándo usar cada servicio
✅ Computer Vision basics
✅ Language/NLP basics
✅ Speech services basics
✅ Generative AI awareness

**Habilidades prácticas:**
✅ Navegar Azure Portal
✅ Usar Vision Studio
✅ Usar Language Studio
✅ Usar Speech Studio
✅ Analizar resultados de IA
✅ Documentar experimentos

---

### 🎓 Lo que aprenderás en Semana 2:

**Machine Learning profundo:**

- Métricas de evaluación en detalle
- Cómo saber si un modelo es bueno
- Azure Machine Learning workspace
- Automated ML en práctica
- Crear y entrenar tu primer modelo real
- Interpretar resultados de modelos

**Será más técnico, pero:**

- Builds on what you learned
- Más práctica, menos teoría
- Crearás algo real
- Los conceptos base ya los tienes

---

## 💬 MENSAJE DE TU MENTOR

**¡Felicidades por completar la Semana 1!** 🎉

Has dado el paso más importante: **EMPEZAR**. Muchas personas compran cursos y nunca los terminan. Tú ya completaste una semana completa.

**Cosas que debes saber:**

1. **Es normal no entenderlo todo al 100%**
   - La IA es un campo complejo
   - Mejorarás con la práctica
   - Cada semana refuerza la anterior

2. **Los labs del sábado fueron cruciales**
   - Ver IA en acción consolida la teoría
   - Ahora los conceptos tienen sentido
   - La práctica es la clave

3. **Las flashcards son tu arma secreta**
   - 5-10 min diarios hacen la diferencia
   - La repetición espaciada funciona
   - No las abandones

4. **El descanso no es opcional**
   - Tu cerebro necesita procesar
   - Evitas burnout
   - Llegas fresco a Semana 2

5. **Vas al ritmo correcto**
   - 10h/semana es sostenible
   - 6 semanas es tiempo suficiente
   - Confía en el proceso

**Recuerda:**

- Ya sabes más que el 90% de la gente sobre Azure AI
- Has usado herramientas que muchos ni conocen
- Cada día estás más cerca del AI-900
- Tienes 5 semanas más para pulir conocimientos

---

## 📞 PARA LA PRÓXIMA SEMANA

**Cuando estés listo para Semana 2, vuelve y pídeme:**

- "Dame el Lunes y Martes de Semana 2 en markdown"
- "Dame toda la Semana 2 completa"
- "Explícame [concepto] antes de empezar Semana 2"

**Si tienes dudas de Semana 1:**

- "No entiendo bien la diferencia entre X e Y"
- "¿Me puedes explicar [concepto] con más ejemplos?"
- "¿Me haces 10 preguntas de práctica de Semana 1?"

---

## ✅ CHECKLIST FINAL SEMANA 1

### Completado:

- [✓] Lunes: Intro a IA
- [✓] Martes: ML tipos
- [✓] Miércoles: Azure setup
- [✓] Jueves: Azure AI Services
- [✓] Viernes: Repaso y consolidación
- [✓] Sábado: Labs prácticos
- [✓] Domingo: DESCANSO

### Materiales:

- [✓] 30-40 flashcards creadas
- [✓] Notas de toda la semana
- [✓] Screenshots de labs
- [✓] Documentación de experimentos
- [✓] Lista de áreas débiles identificadas

### Listo para:

- [✓] Empezar Semana 2 el Lunes 10 Nov
- [✓] Profundizar en Machine Learning
- [✓] Crear mi primer modelo real

---

## 🎊 ¡DESCANSA Y NOS VEMOS EL LUNES!

**Disfruta tu domingo.**
**Has trabajado duro.**
**Te lo mereces.**

**El lunes empezamos Semana 2 con energía renovada.** 💪

---

## 📊 ESTADÍSTICAS SEMANA 1

```
┌─────────────────────────────────────┐
│     SEMANA 1 - ESTADÍSTICAS        │
├─────────────────────────────────────┤
│ Días completados:        6/6 ✅    │
│ Horas invertidas:        ~10h ✅   │
│ Flashcards creadas:      30-40 ✅  │
│ Labs completados:        9+ ✅     │
│ Servicios explorados:    9+ ✅     │
│ Conceptos dominados:     15+ ✅    │
│ Progreso total:          16.7% ✅  │
├─────────────────────────────────────┤
│ Próximo hito: Semana 2 - ML        │
│ Fecha: Lun 10 Nov 2025             │
└─────────────────────────────────────┘
```

---

**¡Hasta el lunes, futuro AI-900! 🚀**

**You got this! 💪**
