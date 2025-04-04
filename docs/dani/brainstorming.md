# Brainstorming

## Ideas

### Funcionalidades

- Widget para visualización y acciones rapidas(añadir input por audio).
- Texto de los proyectos en .md con edicion mediante algo similar a Cursor.
- Emociones
- Gastos
- Listas de la compra
- Ideas
- Objetivos
- TODOs
- Seguimiento de tareas
- Calendario
- Temas:
    + Videos
    + Curiosidades
    + Apuntes
    + Cheatsheets
- Proyectos:
    + Ideas rapidas
    + TODOs
    + Recursos
    + Documentos desarrollo
    + Imagenes
- Usar Scribe
- Usar Claude 3.5/3.7
- Usar GPT4o/GPT4.5
- LocalFirst
    + Fast
    + Multi-device
    + Offline
    + Collaborative
    + Longevity
    + Privacy
    + User control

### Estetica

[Pinterest/apps](https://es.pinterest.com/thedanixsx/apps/)

[Figma/ControlLife](https://www.figma.com/design/rRGX3H5JxvSDjekj4XBnRH/ControlLife?node-id=0-1&p=f&t=kpvJkiM06LNlmynw-0)

### Desarrollo

#### App shopping list


#### App FinTech




## Videos
### Code with Beto

[How to build local-first native apps with LiveStore and Expo](https://youtu.be/zQIhJqYU1Qw?si=YRfPyXVaVND5fxH-) 00:29:33

- Expo
- LiveStore

[Build a Local-First Real-Time Shopping List App with Expo, TinyBase, Clerk & Cloudflare](https://youtu.be/HqOiB2tDM8Q?si=ljbjzw05zM8ZrDvZ) 04:37:27

[GitHub](https://codewithbeto.dev/projects/shopping-list-app)

- Expo
- @clerk/clerk-expo : for autentication
- @clerk/types : type safety
- @clerk/clerk-expo : for autentication
- expo-crypto : needed for clerk and unique identifiers for objects
- expo-camera : using the camera for QR codes
- react-native-qrcode-svg : generate QR codes
- react-native-svg : needed for qrcode
- expo-network : make easy for network status
- reconnecting-websocket : make easy reconections
- tinybase : local data base
- expo-sqlite : needed for tinybase
- Cloudflare : cloud data base, durable objects

[Build a Modern Multi-User Chat App with React Native, Expo, Clerk & Appwrite (Real-Time)](https://youtu.be/HKJdqJIDtMs?si=D26eYz1I3pA9gQUC) 01:52:39

[GitHub](https://codewithbeto.dev/projects/modern-chat-app)

- @clerk/clerk-expo: Core Clerk SDK for Expo/React Native apps
- @clerk/types: TypeScript types for Clerk
- @clerk/expo-passkeys: Enables passkey (biometric) authentication
- expo-secure-store: Provides secure storage for tokens
- expo-auth-session & expo-web-browser: Required for OAuth flows (Google Sign-in)
- expo-crypto: Handles cryptographic operations
- expo-build-properties: Configures native build settings

### Simon Grimm

[Airbnb Clone with React Native (Expo Router, Authentication, Reanimated, Clerk)](https://youtu.be/iWzUZiVoiR0?si=X4fcljKkBhjgQNUb) 04:41:31

[GitHub](https://github.com/Galaxies-dev/airbnb-clone-react-native)

- Expo
- expo-router v2 : file-based
- @clerk/clerk-expo : for user authentication, add Sign-in with Apple and Google Auth
- react-native-reanimated for animations

[Build a WhatsApp Clone with React Native (Expo Router, Reanimated, Clerk, Gestures, Gifted Chat)](https://youtu.be/VUhaDTKYBJU?si=JxVdNCBPaoRUpGGE) 04:06:07

[GitHub](https://github.com/Galaxies-dev/whatsapp-clone-react-native)

- Expo
- expo-router : file-based
- @clerk/clerk-expo : for user authentication, add Sign-in with Apple and Google Auth
- react-native-reanimated : for animations
- react-native-gesture-handler : gestures recognition
- react-native-gifted-chat : chat UI

[Build a FinTech Clone with React Native (API Routes, Zustand, Tanstack Query, FaceID, Charts, Clerk)](https://youtu.be/iDZBeIgcixk?si=nYYIN7HRxtOgnkNC) 05:34:52

[GitHub](https://github.com/Galaxies-dev/fintech-clone-react-native)

- Expo
- expo-router : file-based navigation, layouts, shared components
- @clerk/clerk-expo : for user authentication, SMS OTP
- API Routes
- reanimated : for powerful animations
- zustand : MMKV for state management
- gesture handler : for gestures
- zeego : for native menus
- CoinMarketCap API : for crypto prices
- tanstack query
- FaceID
- Victory Native XL : for charts

[Build a Threads Clone with React Native (Convex, Clerk, Sentry, Expo)](https://youtu.be/D-DUZNeVlRE?si=hvXGXN4au37BZZ-K) 06:21:05

[GitHub](https://github.com/Galaxies-dev/todoist-clone-react-native)

- Expo
- expo-router : file-based navigation, layouts, shared components
- @clerk/clerk-expo : for user authentication, add Sign-in with Apple, Google Auth and Instagram
- convex : backend logic
- convex database : for data storage
- convex file storage : for file storage
- convex actions : for push notifications
- sentry : for error tracking
- haptics : for haptic feedback
- expo notifications : for push notifications
- reanimated : for powerful animations
- image zoom : for image zoom component

[Build a Todoist Clone with React Native (RevenueCat, Clerk, Sentry, Expo, Reanimated, SQLite)](https://youtu.be/_k5v0KOfNZ0?si=xyGc0daMpTmxNeI9) 05:32:08

[GitHub](https://github.com/Galaxies-dev/todoist-clone-react-native)

- Expo
- expo-router : file-based navigation, layouts, shared components
- @clerk/clerk-expo : for user authentication, add Sign-in with Apple and Google Auth
- sentry : error tracking
- revenueCat : suscriptions and pay-walls
- expo-sqlite : for storing chats and messages
- react hook : form for form handling
- calendars : for calendar component
- bouncy checkbox : for checkbox component
- haptics : for haptic feedback
- reanimated : 3 for animations
- gesture handler : for gestures
- RN MMKV : for efficient key/value storage
- sonner native : for toast notifications

### Others

[How to Develop Mobile Apps for Android and iOS using Cursor AI Coding in React Native and Expo 2025](https://youtu.be/fSJj16UM990?si=x_opbUeIy8A11UZd) 00:41:25

[La forma más rápida de crear una aplicación móvil (IA + Expo = Magia)](https://youtu.be/fJb6f2Sw4Ek?si=aGkW5jwZbrlne2eG) 00:09:50

[]()
## Documentación

[Android Studio](https://developer.android.com)

[Expo](https://docs.expo.dev)

[ChatGPT](https://platform.openai.com/docs/overview)

[Scribe](https://elevenlabs.io/docs/api-reference/speech-to-text/convert)

[]()

## Objetivo

### Visión y Propósito

ControlLife es una aplicación Android avanzada diseñada para el bienestar emocional y mental, que permite a los usuarios registrar, analizar y visualizar sus estados emocionales y pensamientos a lo largo del tiempo. El propósito fundamental es proporcionar una herramienta personal intuitiva que ayude a los usuarios a aumentar su autoconciencia emocional mediante el registro sistemático de sus experiencias.

### Funcionalidades Principales
1. Sistema de Registro Emocional
    - **Entradas detalladas:** Cada registro incluirá fecha/hora automática, descripción de la situación desencadenante (opcional), emociones experimentadas y/o pensamientos asociados y consecuencias (opcional).
    - **Categorización emocional:** Sistema de etiquetado con emociones primarias (alegría, tristeza, miedo, ira, sorpresa, asco) y secundarias para análisis posterior. (Posibilidad de tener unas emociones cerradas y que el usuario tenga que ceñirse a ellas)
    - **Entrada dual:**
        + Entrada de texto directamente en los campos a cubrir del registro.
        + Entrada por voz mediante la API ElevenLabs Scribe, con transcripción automática. Procesamiento avanzado con IA (ChatGPT) para extraer y categorizar automáticamente elementos emocionales del texto

2. Visualización y Análisis
    - **Línea temporal:** Visualización cronológica de registros
    - **Patrones emocionales:** Gráficos y estadísticas que muestran tendencias emocionales semanales/mensuales (Futuro)

3. Componentes de Interfaz
    - **Widget personalizable:** Para acceso rápido desde la pantalla principal, mostrando registros recientes y acceso directo a nuevos registros tanto por texto como por voz.
    - **Notificaciones sutiles:** Recordatorios configurables para mantener la constancia en el registro

### Diseño y Experiencia de Usuario
1. Estética Visual
    - **Paleta cromática:** Esquema de colores armónico basado en la psicología del color, con tonos primarios tranquilizantes y acentos emocionales
    - **Modo claro/oscuro:** Adaptación automática según preferencias del sistema y hora del día

 2. Principios de Diseño
    - **Minimalismo funcional:** Interfaces limpias sin elementos distractores
    - **Diseño adaptativo:** Optimizado para diferentes tamaños de pantalla y orientaciones
    - **Navegación intuitiva:** Gestos naturales y transiciones fluidas entre secciones

### Accesibilidad y Personalización
- **Alto contraste:** Modo especial para usuarios con discapacidad visual
- **Compatibilidad con lectores de pantalla:** Etiquetas semánticas para todas las funciones
- **Temas personalizables:** Permitir al usuario adaptar la interfaz a sus preferencias estéticas
- **Opciones de fuente:** Variedad de tipos y tamaños para mejorar la legibilidad

### Seguridad y Privacidad
- **Cifrado local:** Protección de datos sensibles en el dispositivo
- **Autenticación biométrica:** Opción de proteger la aplicación mediante huella digital o reconocimiento facial
- **Exportación segura:** Posibilidad de respaldar y exportar registros en formatos protegidos

## Decisiones técnicas y arquitectura del Proyecto

### Entorno de Desarrollo

- **Plataforma:** Android
- **IDE:** Android Studio (última versión)
- **Lenguaje:** Kotlin
- **Dispositivo de Prueba:** Google Pixel 9 Pro XL
- **Patrón de Diseño:** MVVM (Model-View-ViewModel) para separar lógicas de presentación y negocio
- **Dependencias y Librerías:**
    + Android Jetpack (Room, LiveData, ViewModel)
    + Hilt o Koin para inyección de dependencias
    + Retrofit o similar para llamadas a APIs

### Funcionalidades de la Aplicación

- **Widget:**
    + Muestra el último registro ingresado
    + Botón "+" para abrir directamente la pantalla de creación de un nuevo registro
    + Botón de audio para iniciar la grabación
- **Registro de Situaciones:**
    + Los registros contienen fecha/ hora, descripción de la situación y emociones/ consecuencias
    + Permitir entrada manual y por voz
- **Grabación y Procesamiento de Audio:**
    + Uso de la API de grabación nativa de Android (MediaRecorder o AudioRecord)
    + Procesamiento STT: Integración con una API de conversión de voz a texto (por ejemplo, OpenAI Whisper, a pesar de que en el enunciado se menciona "ChatGPT STT", se opta por Whisper, que es el estándar actual)
    + Formateo del Texto: Envío del texto obtenido a la API de ChatGPT (GPT-3.5 o GPT-4) para extraer y formatear la información (fecha, situación, emociones)

### Base de Datos y Sincronización

- **Base de Datos Online:** Firebase Firestore, aprovechando su capacidad de sincronización en tiempo real y soporte para persistencia offline
- **Base de Datos Local:** Android Room para almacenar los registros recientes y permitir la operación sin conexión
- **Estrategia de Sincronización:** 
    + Los nuevos registros se guardan localmente y se sincronizan con Firestore en cuanto se detecte conexión
    + El widget muestra la información extraída del almacenamiento local

### Herramientas de Backend y API

- **Firebase:** 
    + Autenticación (si se requiere, en versiones futuras)
    + Firestore para la base de datos
    + Cloud Functions para lógica extra (opcional, para procesamientos o notificaciones)
- **APIs Externas:**
    + Scribe de ElevenLabs para STT
    + ChatGPT API o Claude API para el formateo y extracción de información estructurada
- **Gestión de Versiones:** Git, con repositorio en GitHub (o GitLab)
- **CI/ CD:** Configuración de GitHub Actions para pruebas automatizadas y despliegue continuo