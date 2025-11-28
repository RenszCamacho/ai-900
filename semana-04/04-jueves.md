# 📚 AI-900 | SEMANA 4 - JUEVES 28 NOV

## 🤖 Conversational AI - Question Answering y Bots

---

## 🎯 OBJETIVOS DEL DÍA

Al finalizar hoy, serás capaz de:

- ✅ Explicar qué es Conversational AI y sus componentes
- ✅ Entender cómo funciona Azure Question Answering
- ✅ Conocer Azure Bot Service y sus capacidades
- ✅ Diferenciar entre bots simples y bots inteligentes
- ✅ Entender Conversational Language Understanding (CLU)
- ✅ Identificar casos de uso reales de chatbots

**Tiempo estimado:** 1.5 horas  
**Nivel de dificultad:** ⭐⭐⭐⚪⚪ (Media)

---

## 📖 PARTE 1: ¿QUÉ ES CONVERSATIONAL AI? (15 min)

### 🤖 Definición

**Conversational AI** (IA Conversacional) es la tecnología que permite a las máquinas mantener **conversaciones naturales** con humanos a través de texto o voz.

```
CONVERSACIÓN TRADICIONAL (sin IA):
Usuario: "¿Cuál es el horario?"
Bot: "No entiendo. Presione 1 para ventas, 2 para soporte..."
❌ Frustrante, rígido, no natural

CONVERSATIONAL AI:
Usuario: "¿Cuál es el horario?"
Bot: "Nuestro horario de atención es de lunes a viernes,
      de 9:00 AM a 6:00 PM. ¿Necesitas algo más?"
✅ Natural, flexible, útil
```

---

### 🧩 Componentes de Conversational AI

```
ARQUITECTURA DE UN BOT INTELIGENTE:

1. 👂 INPUT PROCESSING (Procesamiento de Entrada)
   - Speech-to-Text (si es voz)
   - Language Detection
   - Normalización del texto

2. 🧠 UNDERSTANDING (Comprensión)
   - Intent Recognition: ¿Qué quiere el usuario?
   - Entity Extraction: ¿Qué información específica menciona?
   - Context Management: ¿Qué conversación previa hay?

3. 💭 PROCESSING (Procesamiento)
   - Question Answering: Buscar respuesta en KB
   - Business Logic: Ejecutar acciones
   - API Calls: Consultar sistemas externos

4. 💬 RESPONSE GENERATION (Generación de Respuesta)
   - Natural Language Generation
   - Personalización
   - Text-to-Speech (si es voz)

5. 📊 LEARNING (Aprendizaje)
   - Analytics de conversaciones
   - Mejora continua del modelo
```

---

### 🎭 Tipos de Bots

#### 1️⃣ **Bots Basados en Reglas (Rule-based)**

```
FUNCIONAMIENTO:
If-Then-Else statements

EJEMPLO:
If user_input == "hola":
    return "¡Hola! ¿En qué puedo ayudarte?"
If user_input == "horario":
    return "Nuestro horario es 9-6"

VENTAJAS:
✅ Simple de implementar
✅ Predecible
✅ Bueno para flujos lineales

DESVENTAJAS:
❌ No entiende variaciones
❌ No aprende
❌ Limitado a escenarios pre-programados
```

#### 2️⃣ **Bots con IA (AI-powered)**

```
FUNCIONAMIENTO:
Modelos de Machine Learning

EJEMPLO:
User: "Quisiera saber a qué hora abren"
Bot entiende:
- Intent: ConsultarHorario
- No requiere palabras exactas

VENTAJAS:
✅ Entiende lenguaje natural
✅ Aprende de conversaciones
✅ Maneja variaciones
✅ Más flexible

DESVENTAJAS:
❌ Más complejo de implementar
❌ Requiere entrenamiento
❌ Puede dar respuestas inesperadas
```

---

## 📖 PARTE 2: AZURE QUESTION ANSWERING (30 min)

### 💡 ¿Qué es Azure Question Answering?

**Azure Question Answering** (anteriormente QnA Maker) es un servicio que permite crear bots de preguntas y respuestas **sin escribir código**.

```
CONCEPTO SIMPLE:

TÚ PROPORCIONAS:
- Base de conocimientos (documentos, FAQs, URLs)
- Pares de preguntas-respuestas

AZURE CREA:
- Un servicio que puede responder preguntas
- Maneja variaciones de preguntas
- Devuelve respuestas con confidence score
```

---

### 🏗️ Cómo Funciona Question Answering

#### Paso 1: Crear Knowledge Base (Base de Conocimientos)

```
FUENTES QUE PUEDES USAR:

1️⃣ DOCUMENTOS:
   - PDFs
   - Word docs
   - Excel (FAQs estructurados)

2️⃣ URLs:
   - Páginas de FAQ de tu sitio web
   - Documentación online
   - Manuales de productos

3️⃣ ENTRADA MANUAL:
   Pregunta: "¿Cuál es el horario de atención?"
   Respuesta: "Lunes a viernes, 9 AM - 6 PM"

4️⃣ CONVERSACIONES (Chitchat):
   - Small talk pre-construido
   - "Hola", "Gracias", "Adiós"
```

**Ejemplo de Knowledge Base:**

```
ENTRADA DESDE URL (www.tienda.com/faq):

PREGUNTA 1: ¿Cuál es la política de devoluciones?
RESPUESTA: Aceptamos devoluciones dentro de 30 días...

PREGUNTA 2: ¿Cómo puedo rastrear mi pedido?
RESPUESTA: Puedes rastrear tu pedido ingresando el número...

PREGUNTA 3: ¿Hacen envíos internacionales?
RESPUESTA: Sí, enviamos a más de 50 países...

Azure automáticamente:
✅ Extrae las preguntas y respuestas
✅ Crea el modelo
✅ Entrena variaciones
```

---

#### Paso 2: El Sistema Aprende Variaciones

```
PREGUNTA ORIGINAL EN KB:
"¿Cuál es el horario de atención?"

EL SISTEMA ENTIENDE VARIACIONES:
✅ "¿A qué hora abren?"
✅ "¿Cuándo están abiertos?"
✅ "Horario de la tienda"
✅ "¿Hasta qué hora atienden?"
✅ "¿Qué días trabajan?"

TODAS devuelven la MISMA respuesta:
"Lunes a viernes, 9 AM - 6 PM"
```

---

#### Paso 3: Confidence Scores

```
USUARIO PREGUNTA: "¿Puedo devolver un producto?"

SISTEMA BUSCA EN KB Y ENCUENTRA:

Match 1: "¿Cuál es la política de devoluciones?"
Confidence: 0.92 (92%) ✅ MUY ALTA

Match 2: "¿Cómo hago un cambio?"
Confidence: 0.45 (45%) ⚠️ BAJA

Match 3: "¿Puedo cancelar mi pedido?"
Confidence: 0.30 (30%) ❌ MUY BAJA

SISTEMA DEVUELVE:
La respuesta del Match 1 (0.92 confidence)
```

**Configuración de Thresholds:**

```
PUEDES CONFIGURAR:

High Threshold (0.80 - 1.00):
→ Bot responde con confianza

Medium Threshold (0.50 - 0.79):
→ Bot pregunta: "¿Te refieres a X?"

Low Threshold (0.00 - 0.49):
→ Bot dice: "No encontré respuesta,
             ¿puedes reformular?"
```

---

### 🔧 Características Avanzadas

#### 1️⃣ **Multi-turn Conversations (Conversaciones Multi-turno)**

```
ESCENARIO: Soporte técnico

USUARIO: "Mi impresora no funciona"
BOT: "¿Qué tipo de problema tienes?"
     [A] No enciende
     [B] No imprime
     [C] Atascos de papel

USUARIO: "No imprime"
BOT: "¿La impresora está conectada a la red?"

USUARIO: "Sí"
BOT: "¿Hay tinta en los cartuchos?"

→ Conversación contextual, no una sola pregunta-respuesta
```

**Cómo se configura:**

```
EN KNOWLEDGE BASE:

PREGUNTA PRINCIPAL: "Problemas con impresora"
RESPUESTA: "¿Qué tipo de problema?"

  FOLLOW-UP 1: "No enciende"
  RESPUESTA: "Verifica que esté conectada..."

  FOLLOW-UP 2: "No imprime"
  RESPUESTA: "¿Está conectada a la red?"

    SUB-FOLLOW-UP: "Sí, está conectada"
    RESPUESTA: "¿Hay tinta?"
```

---

#### 2️⃣ **Active Learning (Aprendizaje Activo)**

```
PROCESO:

1. USUARIOS HACEN PREGUNTAS
   "¿Aceptan pagos con Bizum?"
   → No hay respuesta exacta en KB

2. SISTEMA SUGIERE MATCHES CERCANOS
   "¿Quizás se refiere a 'métodos de pago'?"

3. TÚ (ADMINISTRADOR) REVISAS
   ✅ Sí, esa pregunta debe asociarse a "métodos de pago"
   ❌ No, necesito crear nueva respuesta

4. SISTEMA APRENDE
   Próxima vez que alguien pregunte sobre Bizum
   → Automáticamente usa la respuesta correcta

BENEFICIO:
El bot mejora automáticamente con el uso real
```

---

#### 3️⃣ **Metadata y Filtrado**

```
USO: Respuestas diferentes según contexto

EJEMPLO: E-commerce con productos diferentes

PRODUCTO: Laptop
PREGUNTA: "¿Tiene garantía?"
RESPUESTA: "Sí, 2 años de garantía"
METADATA: {"producto": "laptop"}

PRODUCTO: Camiseta
PREGUNTA: "¿Tiene garantía?"
RESPUESTA: "30 días de devolución sin preguntas"
METADATA: {"producto": "ropa"}

CUANDO USUARIO PREGUNTA:
Context: {"producto": "laptop"}
→ Respuesta: "2 años de garantía"

Context: {"producto": "ropa"}
→ Respuesta: "30 días de devolución"
```

---

#### 4️⃣ **Sinónimos**

```
PROBLEMA:
Usuarios usan palabras diferentes para lo mismo

SOLUCIÓN: Definir sinónimos

EJEMPLO:

SINÓNIMOS CONFIGURADOS:
"PC" = "computadora" = "ordenador" = "laptop"
"celular" = "móvil" = "teléfono" = "smartphone"

RESULTADO:
Usuario pregunta: "¿Venden PCs?"
Sistema entiende: "¿Venden computadoras?"
→ Devuelve respuestas sobre computadoras
```

---

### 💼 Casos de Uso de Question Answering

#### 1️⃣ **FAQ Automatizado para Sitios Web**

```
ESCENARIO: E-commerce con 500 visitas/día

ANTES:
- 50 personas/día preguntan lo mismo
- Agentes responden manualmente
- Tiempo promedio: 5 minutos por consulta
- Costo: Alto (salarios de agentes)

DESPUÉS (con Question Answering):
- Bot responde 80% de preguntas comunes
- Tiempo de respuesta: Instantáneo
- Solo 10 consultas complejas van a humanos
- Ahorro: 75% en costos de soporte

EJEMPLO DE FLUJO:
Usuario en sitio web → Click en "Chat"
Usuario: "¿Hacen envíos a Perú?"
Bot (1 segundo después): "Sí, enviamos a toda América Latina..."
```

---

#### 2️⃣ **Soporte de TI Interno**

```
CASO: Empresa con 1,000 empleados

KNOWLEDGE BASE contiene:
- "¿Cómo resetear mi contraseña?"
- "¿Cómo conectarme a la VPN?"
- "¿Cómo instalar Office?"
- "¿A quién contacto si mi laptop no enciende?"

BENEFICIO:
- Empleados obtienen respuestas 24/7
- Reduce tickets a IT en 60%
- IT se enfoca en problemas complejos
```

---

#### 3️⃣ **Onboarding de Nuevos Empleados**

```
BOT: "HR Buddy"

PREGUNTAS TÍPICAS:
- "¿Cómo solicito vacaciones?"
- "¿Dónde veo mi recibo de nómina?"
- "¿Cuál es el código de vestimenta?"
- "¿Cómo funciona el sistema de beneficios?"

VALOR:
Nuevos empleados no necesitan molestar a RR.HH.
para preguntas básicas
```

---

#### 4️⃣ **Documentación de Productos**

```
ESCENARIO: Empresa SaaS con producto complejo

KNOWLEDGE BASE desde:
- Manual de usuario (PDF de 200 páginas)
- Documentación técnica
- Release notes
- Tutoriales en blog

RESULTADO:
Usuario: "¿Cómo exporto datos a CSV?"
Bot: "Aquí te explico paso a paso..."
     [con enlace a documentación relevante]

Mucho más rápido que buscar en 200 páginas
```

---

## 📖 PARTE 3: AZURE BOT SERVICE (25 min)

### 🤖 ¿Qué es Azure Bot Service?

**Azure Bot Service** es una plataforma completa para **crear, publicar y gestionar** bots inteligentes.

```
QUESTION ANSWERING vs BOT SERVICE:

QUESTION ANSWERING:
→ El "cerebro" (responde preguntas)
→ Backend/lógica

BOT SERVICE:
→ La "interfaz" (cómo los usuarios interactúan)
→ Canales de comunicación
→ Orquestación
```

**Analogía:**

```
Question Answering = Motor del auto
Bot Service = Todo el auto completo (volante, ruedas, carrocería)
```

---

### 🌐 Canales de Despliegue

**Bot Service permite publicar tu bot en múltiples canales:**

```
CANALES SOPORTADOS:

💬 WEB:
   - Widget de chat en tu sitio web
   - Página de chat dedicada

📱 MÓVIL:
   - Aplicaciones iOS/Android nativas

💼 MICROSOFT:
   - Microsoft Teams ⭐ (muy usado en empresas)
   - Skype
   - Outlook

📧 EMAIL:
   - Responder emails automáticamente

🗨️ MENSAJERÍA:
   - Facebook Messenger
   - Telegram
   - WhatsApp (con Business API)
   - Slack
   - Line

🔊 VOZ:
   - Cortana
   - Alexa (con adaptador)

🌐 CUSTOM:
   - Direct Line API (tu propia app)
```

**¿Por qué es poderoso?**

```
ESCRIBES EL BOT UNA VEZ
↓
SE DESPLIEGA EN 10+ CANALES
↓
Usuarios interactúan desde donde prefieran
```

---

### 🏗️ Arquitectura de Bot Service

```
COMPONENTES:

1️⃣ BOT LOGIC (Lógica del Bot)
   - Escrito en C#, Python, JavaScript, o Java
   - Maneja conversaciones
   - Integra con servicios (Question Answering, LUIS, etc.)

2️⃣ BOT CONNECTOR
   - Conecta tu bot con canales
   - Maneja autenticación
   - Traduce formatos de mensajes

3️⃣ CHANNELS
   - Donde los usuarios interactúan
   - Cada canal tiene su UI específica

4️⃣ BACKEND SERVICES
   - Question Answering
   - Conversational Language Understanding (CLU)
   - Azure Cognitive Search
   - Bases de datos
   - APIs propias
```

**Flujo de conversación:**

```
Usuario en Teams: "¿Cuál es mi saldo?"
   ↓
Bot Connector recibe mensaje
   ↓
Bot Logic procesa
   ↓
Llama a API de banco
   ↓
Genera respuesta: "Tu saldo es $1,500"
   ↓
Bot Connector envía a Teams
   ↓
Usuario ve respuesta en Teams
```

---

### 🎨 Características de Bot Service

#### 1️⃣ **Adaptive Cards**

```
¿Qué son?
Mensajes ricos e interactivos (no solo texto)

EJEMPLO:

Texto simple:
"Tienes 3 pedidos pendientes: #123, #456, #789"

Adaptive Card:
┌─────────────────────────────┐
│ 📦 Tus Pedidos Pendientes   │
├─────────────────────────────┤
│ Pedido #123                 │
│ Estado: En tránsito         │
│ [Ver detalles] [Rastrear]   │
├─────────────────────────────┤
│ Pedido #456                 │
│ Estado: Preparando          │
│ [Ver detalles] [Cancelar]   │
├─────────────────────────────┤
│ Pedido #789                 │
│ Estado: Entregado ✓         │
│ [Ver detalles] [Reordenar]  │
└─────────────────────────────┘
```

**Ventajas:**

- Visuales
- Interactivos (botones)
- Mejor UX que texto plano

---

#### 2️⃣ **Dialogs (Diálogos)**

```
¿Qué son?
Flujos de conversación estructurados

EJEMPLO: Reservar cita médica

Dialog "ReservarCita":
  BOT: "¿Para qué especialidad necesitas la cita?"
  USER: "Cardiología"

  BOT: "¿Qué día prefieres?"
  USER: "El próximo viernes"

  BOT: "¿Horario de mañana (9-12) o tarde (2-6)?"
  USER: "Mañana"

  BOT: "Perfecto. Cita de cardiología, viernes 1 dic, 10 AM"
       [Confirmar] [Cambiar]
```

**Tipos de Dialogs:**

- **Waterfall**: Secuencia lineal de pasos
- **Component**: Reutilizable en múltiples flujos
- **Adaptive**: Flujos condicionales complejos

---

#### 3️⃣ **State Management (Gestión de Estado)**

```
PROBLEMA:
Bot necesita "recordar" información durante conversación

SOLUCIÓN: 3 tipos de estado

1. USER STATE (Estado de Usuario)
   - Persiste entre conversaciones
   - Ejemplo: Nombre, preferencias, idioma

2. CONVERSATION STATE (Estado de Conversación)
   - Dura solo durante la conversación actual
   - Ejemplo: Carrito de compras temporal

3. PRIVATE CONVERSATION STATE
   - Específico de canal/bot en conversación grupal
```

**Ejemplo práctico:**

```
CONVERSACIÓN 1 (Lunes):
USER: "Me llamo Juan"
BOT: "Encantado, Juan" [guarda en USER STATE]

CONVERSACIÓN 2 (Miércoles):
USER: "Hola"
BOT: "¡Hola de nuevo, Juan!" [recupera de USER STATE]
     "¿En qué puedo ayudarte hoy?"
```

---

#### 4️⃣ **Proactive Messaging**

```
¿Qué es?
Bot inicia conversación (no espera a que usuario escriba)

CASOS DE USO:

📢 NOTIFICACIONES:
   "Tu pedido #123 acaba de ser enviado"

⏰ RECORDATORIOS:
   "Tienes una reunión en 15 minutos"

🎉 MENSAJES DE MARKETING:
   "¡Nueva oferta en productos que te gustan!"

⚠️ ALERTAS:
   "Actividad sospechosa detectada en tu cuenta"
```

---

### 💼 Casos de Uso de Bot Service

#### 1️⃣ **Asistente de Empleados en Microsoft Teams**

```
ESCENARIO: Empresa con 5,000 empleados

BOT: "IT HelpDesk Bot" en Teams

FUNCIONALIDADES:
- Responde preguntas comunes (Question Answering)
- Crea tickets automáticamente
- Consulta estado de equipos
- Reserva salas de reuniones

EJEMPLO:
Empleado: "Mi VPN no funciona"
Bot: "He creado el ticket #456. IT responderá en 2 horas.
     Mientras tanto, ¿has intentado reiniciar?"
```

---

#### 2️⃣ **Bot de Ventas en WhatsApp**

```
CASO: Tienda de ropa

BOT en WhatsApp Business:

Cliente: "Hola, busco jeans"
Bot: "¡Perfecto! Tenemos:"
     [Adaptive Card con imágenes]
     - Jeans clásicos - $50
     - Jeans rotos - $65
     - Jeans ajustados - $55
     [Ver más]

Cliente: Click en "Jeans clásicos"
Bot: "¿Qué talla necesitas?"
Cliente: "32"
Bot: "Tenemos en stock. ¿Añadir al carrito?"
```

---

#### 3️⃣ **Chatbot de Banca en Aplicación Móvil**

```
BOT: Asistente bancario

CAPACIDADES:
- Consultar saldo
- Ver movimientos
- Transferir dinero
- Pagar servicios
- Reportar tarjeta robada
- Agendar cita en sucursal

SEGURIDAD:
- Autenticación biométrica
- Verificación de transacciones
- Cifrado end-to-end

EJEMPLO:
Usuario: "Quiero transferir $500 a mi mamá"
Bot: "¿A qué cuenta?"
Usuario: "La que termina en 4532"
Bot: "Transferir $500 a cuenta ***4532"
     "Por favor confirma con tu huella digital"
[Usuario confirma]
Bot: "✅ Transferencia completada"
```

---

#### 4️⃣ **Soporte de E-learning en Slack**

```
BOT: "Study Buddy" para curso online

INTEGRADO EN SLACK:

Alumno: "@StudyBuddy ¿Cuándo es la entrega del proyecto?"
Bot: "El proyecto final vence el 15 de diciembre"
     "Todavía tienes 18 días 📅"

Alumno: "@StudyBuddy ¿Dónde encuentro el material de la semana 3?"
Bot: "Aquí está el material de la semana 3:"
     🔗 Lecturas
     🔗 Video conferencia
     🔗 Ejercicios

+ Recordatorios proactivos:
Bot: "⏰ Recordatorio: El quiz de hoy cierra en 2 horas"
```

---

## 📖 PARTE 4: CONVERSATIONAL LANGUAGE UNDERSTANDING (CLU) (15 min)

### 🧠 ¿Qué es CLU?

**Conversational Language Understanding** (anteriormente LUIS - Language Understanding) es el servicio que permite que tu bot **entienda la intención** del usuario.

```
PROBLEMA:
Usuario NO dice exactamente lo que quieres escuchar

EJEMPLOS de la misma intención:

Intent: ReservarVuelo
✅ "Quiero volar a Madrid"
✅ "Necesito un boleto a Madrid"
✅ "Quisiera reservar un vuelo Madrid"
✅ "Me puedes ayudar a ir a Madrid"
✅ "Vuelo Madrid please"

CLU entiende que TODAS tienen la misma intención
```

---

### 🎯 Conceptos Clave de CLU

#### 1️⃣ **Intents (Intenciones)**

```
¿Qué quiere hacer el usuario?

EJEMPLOS:

Intent: ReservarVuelo
Intent: CancelarReserva
Intent: ConsultarEstado
Intent: CambiarFecha
Intent: SolicitarReembolso
```

#### 2️⃣ **Entities (Entidades)**

```
¿Qué información específica menciona?

EJEMPLO:

Usuario: "Quiero volar a Madrid el 15 de diciembre"

INTENT: ReservarVuelo
ENTITIES:
  - Destino: "Madrid"
  - Fecha: "15 de diciembre"
```

#### 3️⃣ **Utterances (Expresiones)**

```
Ejemplos de cómo los usuarios expresan cada intent

INTENT: ReservarVuelo

UTTERANCES para entrenar:
- "Quiero volar a [destino]"
- "Necesito un boleto a [destino]"
- "Reservar vuelo para [destino]"
- "Me voy a [destino] el [fecha]"
- "Boleto [origen] a [destino]"

Cuantos más ejemplos, mejor entiende el modelo
```

---

### 🏗️ Cómo Funciona CLU

```
PROCESO:

1. ENTRENAR MODELO
   - Defines intents
   - Defines entities
   - Proporcionas utterances de ejemplo
   - CLU aprende patrones

2. PUBLICAR MODELO
   - Modelo disponible via API

3. EN RUNTIME
   Usuario: "Necesito cancelar mi reserva del viernes"

   CLU analiza →
   {
     "topIntent": "CancelarReserva",
     "score": 0.95,
     "entities": {
       "fecha": "viernes"
     }
   }

4. TU BOT PROCESA
   If intent == "CancelarReserva":
       cancelar_reserva(entities["fecha"])
```

---

### 🔄 Question Answering vs CLU

```
QUESTION ANSWERING:
- Para preguntas con respuestas fijas
- "¿Cuál es el horario?" → "9 AM - 6 PM"
- Knowledge base
- No ejecuta acciones

CLU:
- Para entender intenciones
- "Quiero cancelar" → INTENT: Cancelar
- Ejecuta lógica de negocio
- Requiere código para acciones

CUÁNDO USAR CADA UNO:

QUESTION ANSWERING:
✅ FAQs informativas
✅ Documentación
✅ Políticas/procedimientos

CLU:
✅ Bots transaccionales
✅ Reservas, compras, cancelaciones
✅ Acciones en sistemas
```

---

### 💼 Caso de Uso Combinado

```
BOT DE RESTAURANTE:

QUESTION ANSWERING para:
- "¿Cuál es el menú del día?"
- "¿Tienen opciones vegetarianas?"
- "¿Dónde están ubicados?"
→ Respuestas de knowledge base

CLU para:
- "Quiero reservar una mesa para 4 personas"
  → INTENT: ReservarMesa
  → ENTITY: numPersonas=4
  → ACCIÓN: Llamar a sistema de reservas

- "Necesito cancelar mi reserva"
  → INTENT: CancelarReserva
  → ACCIÓN: Buscar y cancelar en sistema

RESULTADO:
Bot que responde preguntas Y ejecuta acciones
```

---

## 🎯 CONCEPTOS CLAVE PARA EL EXAMEN AI-900

### ✅ DEBES SABER:

1. **Conversational AI:**
   - IA que permite conversaciones naturales
   - Combina NLP, Speech, y lógica de negocio

2. **Question Answering:**
   - Crea bots de FAQ sin código
   - Knowledge base de preguntas-respuestas
   - Confidence scores y thresholds
   - Active learning mejora con uso

3. **Bot Service:**
   - Plataforma para crear y publicar bots
   - Múltiples canales (Teams, Web, WhatsApp, etc.)
   - Adaptive Cards, Dialogs, State Management

4. **CLU (Conversational Language Understanding):**
   - Entiende intenciones del usuario
   - Extrae entidades
   - Para bots transaccionales

5. **Diferencias clave:**
   - QnA = Respuestas fijas
   - CLU = Entender intenciones y ejecutar acciones

---

## 🎴 FLASHCARDS PARA HOY

Crea estas 10 flashcards:

1. **P:** ¿Qué es Conversational AI?  
   **R:** Tecnología que permite a las máquinas mantener conversaciones naturales con humanos

2. **P:** ¿Qué es Azure Question Answering?  
   **R:** Servicio para crear bots de FAQ sin código, usando knowledge base de preguntas-respuestas

3. **P:** ¿Qué es un Knowledge Base en Question Answering?  
   **R:** Base de conocimientos con pares de preguntas-respuestas, puede crearse desde docs, URLs o manual

4. **P:** ¿Qué es Azure Bot Service?  
   **R:** Plataforma para crear, publicar y gestionar bots en múltiples canales

5. **P:** ¿Qué canales soporta Bot Service?  
   **R:** Web, Teams, Slack, WhatsApp, Facebook Messenger, Telegram, Email, y más

6. **P:** ¿Qué son Adaptive Cards?  
   **R:** Mensajes ricos e interactivos con botones, imágenes y formularios (no solo texto)

7. **P:** ¿Qué es CLU (Conversational Language Understanding)?  
   **R:** Servicio que entiende la intención del usuario y extrae entidades de conversaciones

8. **P:** Diferencia entre Question Answering y CLU  
   **R:** QnA da respuestas fijas de KB; CLU entiende intenciones para ejecutar acciones

9. **P:** ¿Qué es un Intent en CLU?  
   **R:** La intención o acción que el usuario quiere realizar (ReservarVuelo, Cancelar, etc.)

10. **P:** ¿Qué es Active Learning en Question Answering?  
    **R:** Capacidad del sistema de mejorar automáticamente aprendiendo de preguntas reales de usuarios

---

## 📝 EJERCICIO PRÁCTICO (20 min)

### Tarea 1: Diseñar un Bot

**Escenario:** Tienda de libros online

**Tu tarea:** Decide qué servicio usar para cada funcionalidad

```
FUNCIONALIDADES REQUERIDAS:

1. "¿Cuál es la política de devoluciones?"
   Servicio: _________________
   Razón: _________________

2. "Quiero comprar el libro '1984' de Orwell"
   Servicio: _________________
   Razón: _________________

3. "¿Tienen libros de ciencia ficción?"
   Servicio: _________________
   Razón: _________________

4. "Necesito cancelar mi pedido #12345"
   Servicio: _________________
   Razón: _________________

5. "¿Hacen envíos a provincias?"
   Servicio: _________________
   Razón: _________________
```

**RESPUESTAS:**

```
1. Question Answering
   Razón: Respuesta fija, FAQ

2. CLU + lógica de negocio
   Razón: Intent: ComprarLibro, Entity: título
          Requiere acción (agregar a carrito)

3. Question Answering o CLU
   Razón: Puede ser FAQ o búsqueda con intent

4. CLU + lógica de negocio
   Razón: Intent: CancelarPedido, Entity: número pedido
          Requiere acción en sistema

5. Question Answering
   Razón: Respuesta fija, FAQ
```

---

### Tarea 2: Identificar Canales

Para cada caso, sugiere el mejor canal:

```
CASO 1: Soporte IT interno de empresa
Canal sugerido: _________________

CASO 2: Tienda de ropa casual para millennials
Canal sugerido: _________________

CASO 3: Banco con clientes mayores de 50 años
Canal sugerido: _________________

CASO 4: Startup tech B2B
Canal sugerido: _________________
```

**RESPUESTAS:**

```
1. Microsoft Teams (empresas usan Teams)
2. WhatsApp, Instagram (millennials están ahí)
3. Web chat, SMS, Teléfono (menos tech-savvy)
4. Slack, Email, Web (profesionales)
```

---

## ✅ CHECKLIST DE HOY

Antes de terminar, verifica:

- [ ] Entiendo qué es Conversational AI
- [ ] Conozco cómo funciona Question Answering
- [ ] Sé qué es un Knowledge Base y cómo crearlo
- [ ] Entiendo confidence scores y thresholds
- [ ] Conozco Azure Bot Service y sus canales
- [ ] Sé qué son Adaptive Cards y Dialogs
- [ ] Entiendo qué es CLU y para qué sirve
- [ ] Puedo diferenciar QnA vs CLU
- [ ] Conozco casos de uso reales
- [ ] He creado las 10 flashcards
- [ ] He completado los ejercicios

---

## 🎯 PARA MAÑANA (Viernes 29 Nov)

**Tema:** Repaso General de la Semana 4 + Mini Examen de NLP

Prepárate para:

- Repasar todos los conceptos de NLP
- Mini examen de práctica
- Consolidar conocimientos
- Identificar áreas que necesitan más estudio

---

## 📚 RECURSOS ADICIONALES

### 🔗 Microsoft Learn (GRATIS):

- "Build a bot with Azure Bot Service"
- "Create a question answering solution"
- "Build a conversational language understanding model"

### 🧪 LAB Recomendado:

- Crear un bot simple con Question Answering
- Probar Bot Framework Composer (herramienta visual)

### 📖 Documentación:

- https://learn.microsoft.com/azure/bot-service/
- https://learn.microsoft.com/azure/ai-services/language-service/question-answering/

---

**¡Excelente trabajo hoy! 🎉**  
Has completado los servicios principales de NLP/Conversational AI.

**Tiempo total:** ~1.5 horas  
**Progreso:** Semana 4 - Día 4/6 ✅

**Mañana cierras la semana de NLP con un repaso completo! 💪**
