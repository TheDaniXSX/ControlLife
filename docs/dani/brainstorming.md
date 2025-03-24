# Brainstorming

## Ideas
- Widget para visualización y acciones rapidas(añadir input por audio).
- Texto de los proyectos en .md con edicion mediante algo similar a Cursor.
- Emociones
- Gastos
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

## Videos
[Creo una APP Android en MINUTOS por IA GRATIS 📱 Tutorial FÁCIL con Cursor y Android Studio](https://www.youtube.com/watch?v=krIwmy014XA) 00:14

[Build a Local-First Real-Time Shopping List App with Expo, TinyBase, Clerk & Cloudflare](https://www.youtube.com/watch?v=HqOiB2tDM8Q&t=948s) 04:37

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