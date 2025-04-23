# Pregunta

Vale, he estado viendo unos cuantos tutoriales y que dependencias usan. A continuacion te paso el resumen de lo que he anotado, hay anotaciones incompletas. Pero quiero que basandote en ello me devuelvas que hace cada una de las dependecias, cuales necesitan a otras para trabajar y demas informacion interesante. No quiero que investigues soluciones distintas a las que yo te paso, solo quiero que organices y expandas la informacion de las que yo te paso unificandolas en una sola lista de dependecias. Estos son mis apuntes:

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

# Respuesta

Perfecto. Basándome en tus apuntes, aquí tienes una **lista unificada, organizada y explicada** de todas las dependencias que mencionaste, indicando qué hace cada una, si depende de otra, y cualquier dato relevante para tu desarrollo:

---

### 🧱 **Infraestructura base**

- **Expo**  
  Framework sobre React Native que simplifica el desarrollo, compilación y despliegue de apps móviles. Aporta APIs nativas, emulador rápido y configuración mínima.  
  > Base de casi todos los proyectos que mencionas.

- **expo-router**  
  Sistema de navegación basado en el sistema de archivos (file-based routing). Facilita el manejo de rutas y layouts en Expo/React Native.  
  > Alternativa moderna a `react-navigation`. Muy útil en apps grandes.

---

### 🔐 **Autenticación (Clerk)**

- **@clerk/clerk-expo**  
  SDK principal de Clerk para apps Expo. Permite autenticación con email, Google, Apple, SMS, OTP, biometría, etc.  
  > Requiere `expo-crypto`, `expo-secure-store` y `expo-auth-session` para ciertos métodos.

- **@clerk/types**  
  Tipos de TypeScript para usar Clerk con mayor seguridad de tipos.

- **@clerk/expo-passkeys**  
  Añade autenticación con **passkeys** (FaceID, TouchID, huella, etc.). Necesita dispositivos compatibles.

---

### 🛠️ **Expo Utilities & APIs**

- **expo-crypto**  
  Operaciones criptográficas. Usado por Clerk para hashes y generar identificadores únicos.

- **expo-secure-store**  
  Almacenamiento seguro (cifrado) de tokens, como el `sessionId` de Clerk. Requiere iOS/Android moderno.

- **expo-auth-session**  
  Necesaria para flujos OAuth como Google o Apple login con Clerk.

- **expo-web-browser**  
  Utilizada en conjunto con `expo-auth-session` para abrir la pantalla de autenticación externa.

- **expo-network**  
  Permite detectar el estado de red del dispositivo (conectado/desconectado).

- **expo-camera**  
  Acceso a la cámara. Se usa en apps que escanean códigos QR.

- **expo-sqlite**  
  Base de datos SQL local embebida. Usada por `tinybase` o directamente para persistencia.  
  > No es tan reactiva como otras opciones, pero es ampliamente soportada.

- **expo-build-properties**  
  Modifica propiedades nativas de compilación (como `minSdkVersion`, flags de compilador, etc.).

- **expo-notifications**  
  Manejo de **push notifications**. Requiere configuración en servidores de backend y servicios como Firebase.

- **expo-haptics** (a veces solo `haptics`)  
  Proporciona retroalimentación háptica (vibraciones) para interacciones del usuario.

---

### 📡 **Comunicación & Sincronización**

- **reconnecting-websocket**  
  WebSocket con reconexión automática. Útil si usas servicios como LiveStore o backend propio.

- **tinybase**  
  Motor de base de datos reactiva in-memory (pero con plugins para persistencia, como SQLite).  
  > Muy útil para **estado local-first sincronizable**. Necesita `expo-sqlite` para persistencia.

- **LiveStore**  
  Capa de sincronización sobre TinyBase. Permite que varios clientes compartan una base en tiempo real (p. ej., mediante WebSocket + CRDTs).  
  > Aún experimental. Usa WebSockets y necesita un backend que lo soporte (ej. Cloudflare Durable Objects).

---

### ☁️ **Backends y almacenamiento en la nube**

- **Cloudflare Durable Objects**  
  Backend serverless que mantiene **estado por cliente/conexión**. Se usa con LiveStore para sincronización.  
  > Necesita implementar lógica del lado del servidor.

- **Convex** (convex, convex actions, convex file storage, convex database)  
  Plataforma backend **reactiva** y serverless: base de datos, lógica (actions), almacenamiento y suscripciones en tiempo real.  
  > Alternativa a Firebase o Supabase. Muy buena para LocalFirst y sincronización directa con clientes React Native.

---

### 🧠 **State Management & Queries**

- **zustand**  
  Librería de gestión de estado basada en hooks. Simple y rápida. Puede usarse con MMKV para persistencia.

- **tanstack query**  
  Herramienta para manejar **queries y sincronización de datos** (antes React Query). Automatiza fetch, caché, sincronización, invalidación.

- **RN MMKV**  
  Wrapper de `MMKV` (lib nativa de almacenamiento clave/valor de WeChat). Súper rápido y persistente.  
  > Se usa con `zustand` para guardar el estado.

---

### 💬 **UI y componentes interactivos**

- **react-native-reanimated**  
  Animaciones complejas y de alto rendimiento (nativo). Versión 3 es la más reciente.  
  > Requiere configuración especial en Babel y en `babel.config.js`.

- **react-native-gesture-handler**  
  Soporte para gestos nativos (swipes, drags, taps). Necesario para Reanimated y apps con UI avanzada.

- **react-native-qrcode-svg**  
  Genera códigos QR en SVG. Depende de `react-native-svg`.

- **react-native-svg**  
  Soporte SVG en React Native. Base para gráficos, íconos vectoriales, QR, etc.

- **react-native-gifted-chat**  
  UI lista para apps de mensajería (estilo WhatsApp). Maneja lista de mensajes, burbujas, input, etc.

- **Victory Native XL**  
  Gráficas y charts en React Native. Requiere `react-native-svg`.

- **zeego**  
  Librería para menús y elementos UI tipo “nativo”. Útil para crear menús contextuales y modales bonitos.

- **react-hook-form**  
  Gestión eficiente de formularios (validación, control, etc.).

- **bouncy checkbox**  
  Checkbox animado y estilizado.

- **calendars**  
  Componente de calendario personalizable.

- **sonner native**  
  Notificaciones tipo “toast” (alertas temporales) para apps móviles.

---

### 🧪 **Testing, errores, analítica**

- **sentry**  
  Rastreo de errores en producción. Captura errores, trazas, rendimiento, etc.

---

### 💰 **Monetización**

- **revenueCat**  
  Gestión de suscripciones y compras dentro de la app. Ideal para paywalls y monetización móvil.

---

### ✅ Relaciones entre dependencias

- `@clerk/clerk-expo` necesita:
  - `expo-auth-session` + `expo-web-browser` (para OAuth)
  - `expo-crypto` (identificadores únicos)
  - `expo-secure-store` (guardar token seguro)

- `tinybase` requiere:
  - `expo-sqlite` si se quiere persistencia local

- `react-native-qrcode-svg` requiere:
  - `react-native-svg`

- `react-native-reanimated` y `react-native-gesture-handler` a menudo se usan juntos

- `zustand` puede combinarse con:
  - `RN MMKV` (para persistencia del estado)

- `LiveStore`, `Convex`, `Cloudflare Durable Objects`:
  - Todos pueden cumplir función de backend/sync en tiempo real. No se usan juntos, sino que se elige uno.

---

¿Quieres que te genere un archivo con esta lista de dependencias ya formateada para usar en un proyecto, o que la convierta a una tabla para verla más fácilmente?

# Pregunta

Vale, entoces se ha decidido que el desarrollo se hara en Expo.

Quiero primero que desarrolles que es expo-router y su alternativa react-navigation asi como otras alternativas si es que las hay y que aportan cada uno dando una comparativa de pros y coontras.

Siguiente quiero que hagamos los mismo con Clerk-expo, alternativas , caracteristicacs, que aportan y comparativa pros y contras.

Siguiente quiero que hagamos los mismo con Cloudflare durable object y convex, alternativas , caracteristicacs, que aportan y comparativa pros y contras.

Ten en cuenta que la aplicacion que se va a hacer es local first y va a almacenar cantitades grandes de tablas de datos, relaciones entre datos, videos, audios, imagenes, graficos, largos textos y un sistema para escribir con lapices como slim pen o apple pencil que entiendo que se guardaria en formato vectorial.

Teniendo en cuenta todo esto valorar lo que te he dicho y hazme un informe

# Respuesta

Genial, prepararé un informe completo comparando:

1. **expo-router vs react-navigation y otras alternativas**.
2. **Clerk-expo vs otras soluciones de autenticación**.
3. **Cloudflare Durable Objects vs Convex y otras opciones de backend/sincronización**.

Tendré en cuenta que:
- La app será multiplataforma (iOS, Android, Web, Windows).
- Necesita ser "local-first" con sincronización eficiente.
- Requiere autenticación social.
- Aceptas servicios en la nube o autogestionados.
- Prioriza facilidad de desarrollo sin muchas limitaciones.

Te mostraré pros y contras de cada opción en relación con tu caso (almacenamiento de datos, medios, vectores, textos, sincronización, desarrollo rápido, etc.).

Te aviso cuando el informe esté listo.

# Informe comparativo de tecnologías para una app Expo multiplataforma (iOS, Android, Web, Windows)

**Introducción:** Se plantea desarrollar una aplicación *local-first* con Expo (React Native) que funcione en iOS, Android, Web y Windows. «Local-first» implica que la app debe funcionar mayormente offline almacenando datos localmente, y sincronizar rápidamente los cambios cuando haya conexión. La aplicación manejará grandes volúmenes de datos tabulares con relaciones, archivos multimedia pesados (videos, audios, imágenes), gráficos, textos largos y también datos de *escritura vectorial* (p. ej. trazos de stylus tipo Slim Pen o Apple Pencil). Este informe analiza comparativamente tecnologías clave en tres áreas: 

- **Enrutamiento de la app:** Expo Router vs React Navigation vs otras alternativas.
- **Autenticación de usuarios:** Clerk (clerk-expo) vs Firebase Auth vs Supabase Auth vs Auth0 (y otros).
- **Backend local-first y sincronización de datos:** Cloudflare Durable Objects vs Convex vs otras soluciones (SQLite local + bibliotecas tipo RxDB/WatermelonDB, Firebase/Firestore, Supabase, Appwrite, PocketBase, etc.).

Para cada tecnología se discuten características, facilidades de desarrollo, rendimiento/escala, soporte multiplataforma y limitaciones relevantes al caso. Al final, se sugieren tipos de bases de datos (relacionales, documentos, vectoriales o híbridas) más adecuados, con sus pros y contras para este escenario.

---

## 1. Enrutamiento: Expo Router vs React Navigation vs otras alternativas

Una de las primeras decisiones es elegir la biblioteca de navegación (enrutamiento) para gestionar las pantallas de la app. Dado que la app apunta a **múltiples plataformas incluyendo web**, es importante que la solución de routing soporte **URL y deep linking** de forma unificada en móvil y web. Las opciones destacadas en el ecosistema React Native son **Expo Router** (propia de Expo) y **React Navigation** (estándar de la comunidad), además de otras como **React Native Navigation** de Wix u otros routers.

### Expo Router (Expo Router)

Expo Router es la solución de enrutamiento introducida por el equipo de Expo. Se basa internamente en React Navigation, pero aporta un **enfoque de routing basado en archivos** (*file-based routing*) al estilo de Next.js, simplificando la configuración de las pantallas ([Expo Router vs React Navigation: A Comprehensive Comparison | Attract Group](https://attractgroup.com/blog/expo-router-vs-react-navigation-a-comprehensive-comparison/#:~:text=Expo%20Router%20is%20a%20navigation,Expo%20Router%20is%20worth%20considering)) ([Introduction to Expo Router - Expo Documentation](https://docs.expo.dev/router/introduction/#:~:text=Expo%20Router%20is%20a%20file,Android%2C%20iOS%2C%20and%20web)). Sus características clave incluyen:

- **Convención sobre configuración:** Automatiza la definición de rutas en base a la estructura de archivos dentro del directorio `app/`. Por ejemplo, crear `app/home.js` genera automáticamente la ruta `/home` sin configuraciones manuales ([Expo Router vs React Navigation: A Comprehensive Comparison | Attract Group](https://attractgroup.com/blog/expo-router-vs-react-navigation-a-comprehensive-comparison/#:~:text=Expo%20Router%20makes%20setup%20easy,project%20and%20saves%20you%20time)). Esto reduce el código de boilerplate y facilita añadir pantallas rápidamente.
- **Integración nativa con Expo:** Al ser desarrollado por Expo, funciona sin fricción con Expo Go y las herramientas Expo. Incluye compatibilidad inmediata con funcionalidades Expo (actualizaciones OTA, etc.) y aprovecha la CLI de Expo.
- **Navegación universal (móvil + web):** Cada pantalla tiene asignada una URL por defecto. Expo Router habilita el deep linking y la navegación web de forma automática, haciendo que las pantallas sean accesibles vía URL en la versión web ([Introduction to Expo Router - Expo Documentation](https://docs.expo.dev/router/introduction/#:~:text=Expo%20Router%20is%20a%20file,Android%2C%20iOS%2C%20and%20web)) ([Introduction to Expo Router - Expo Documentation](https://docs.expo.dev/router/introduction/#:~:text=,evaluation%20in)). Soporta **renderizado estático en web** para mejorar SEO y performance ([Migrate from React Navigation - Expo Documentation](https://docs.expo.dev/router/migrate/from-react-navigation/#:~:text=Pitch)), lo que permite indexar el contenido de la app en buscadores.
- **Características avanzadas:** Provee *type-safety* en la navegación (integración con TypeScript para validar rutas y parámetros), *lazy loading* de pantallas (carga diferida) y *deferred bundling* para optimizar el rendimiento ([Introduction to Expo Router - Expo Documentation](https://docs.expo.dev/router/introduction/#:~:text=any%20route%20in%20your%20app,APIs%20at%20the%20route%20level)) ([Migrate from React Navigation - Expo Documentation](https://docs.expo.dev/router/migrate/from-react-navigation/#:~:text=Pitch)). También maneja automáticamente incoming links sin conexión (*offline-first linking*) y ofrece Fast Refresh unificado en Android, iOS y web para acelerar el desarrollo ([Introduction to Expo Router - Expo Documentation](https://docs.expo.dev/router/introduction/#:~:text=any%20route%20in%20your%20app,a%20unified%20navigation%20structure%2C%20with)).
- **Facilidad de uso:** Para proyectos nuevos o desarrolladores principiantes, Expo Router resulta muy sencillo: no requiere configurar navegadores ni stacks manualmente; basta con organizar los archivos. Esto acelera el desarrollo de MVPs o apps con plazos ajustados ([Expo Router vs React Navigation: A Comprehensive Comparison | Attract Group](https://attractgroup.com/blog/expo-router-vs-react-navigation-a-comprehensive-comparison/#:~:text=,and%20mobile%20without%20extra%20configuration)).

**Limitaciones de Expo Router:** Al ser relativamente nuevo (surgió en 2023) todavía está madurando. Algunas de sus desventajas o consideraciones son: 
- Menor flexibilidad en personalización extrema de la navegación comparado con React Navigation. Por ejemplo, Expo Router maneja parámetros de búsqueda (query params) de forma limitada: solo permite valores primitivos serializables (número, booleano, string) en la URL, evitando pasar objetos o funciones como parámetros ([Exploring Navigation Solutions in React Native: Expo Router vs. React Navigation | by Pallavikhedle | Medium](https://medium.com/@pallavi8khedle/exploring-navigation-solutions-in-react-native-expo-router-vs-react-navigation-37c270d45a7b#:~:text=developers%2C%20React%20Navigation%20boasts%20extensive,contributed%20resources%2C%20and%20ongoing%20support)). Esto impone cierta restricción en cómo se envían datos complejos entre pantallas.
- Si la app requiere patrones inusuales (por ejemplo, reiniciar el stack de navegación globalmente, flujos de varias pilas independientes) puede ser menos trivial, ya que Expo Router asume convenciones estándar. La documentación de Expo desaconseja ciertos usos (como `resetRoot`) sugiriendo reestructurar la navegación en lugar de hacks ([Migrate from React Navigation - Expo Documentation](https://docs.expo.dev/router/migrate/from-react-navigation/#:~:text=migration,for%20the%20initial%20route)).
- **Soporte multiplataforma:** Expo Router soporta oficialmente Android, iOS y web de manera unificada. ¿Y Windows? Dado que Expo Router depende de React Navigation debajo, en teoría podría funcionar con React Native Windows si React Navigation lo soporta. Sin embargo, Expo como plataforma aún no ofrece soporte *out-of-the-box* para compilar en Windows (típicamente se requiere ejectar y usar React Native Windows). Por tanto, usar Expo Router en una app Windows nativa podría requerir trabajo adicional. Alternativamente, la versión web de la app podría usarse en Windows (PWA o Electron) para evitar un binario nativo. Esto es un detalle a considerar según cómo se quiera implementar la pata de Windows.

En resumen, Expo Router brilla por su **simplicidad y su capacidad de navegación universal web+nativo** sin configurar deep links manualmente. Es ideal si se usa Expo y se desea rapidez de desarrollo y URL en web sin complicaciones ([Expo Router vs React Navigation: A Comprehensive Comparison | Attract Group](https://attractgroup.com/blog/expo-router-vs-react-navigation-a-comprehensive-comparison/#:~:text=,and%20mobile%20without%20extra%20configuration)) ([Introduction to Expo Router - Expo Documentation](https://docs.expo.dev/router/introduction/#:~:text=Expo%20Router%20is%20a%20file,Android%2C%20iOS%2C%20and%20web)).

### React Navigation

React Navigation es la librería de navegación más consolidada en React Native. Ha sido el estándar de facto durante años, con un amplio soporte de la comunidad. Algunas de sus características y ventajas:

- **Gran flexibilidad y potencia:** Ofrece múltiples navegadores predefinidos – *stack navigator*, *tab bottom navigator*, *drawer navigator*, etc., que pueden combinarse y anidarse para construir flujos de navegación complejos ([Exploring Navigation Solutions in React Native: Expo Router vs. React Navigation | by Pallavikhedle | Medium](https://medium.com/@pallavi8khedle/exploring-navigation-solutions-in-react-native-expo-router-vs-react-navigation-37c270d45a7b#:~:text=1,contributed%20resources%2C%20and%20ongoing%20support)). Permite control total sobre las transiciones, gestos, encabezados personalizados, etc. Esto la hace apta para apps con requisitos muy específicos de navegación (animaciones personalizadas, flujos condicionales, etc.).
- **Ecosistema y comunidad:** Cuenta con años de madurez, extensa documentación y *plugins*/extensiones oficiales y de terceros. Por ejemplo, integración con Redux, utilidades para deep linking, manejo avanzado de estado de navegación, etc. La comunidad activa significa más ejemplos y soluciones disponibles para problemas comunes ([React Navigation vs. Expo Router | Dev Genius](https://blog.devgenius.io/react-navigation-vs-ae9fc06630ba#:~:text=Pros%20of%20React%20Navigation)) ([React Navigation vs. Expo Router | Dev Genius](https://blog.devgenius.io/react-navigation-vs-ae9fc06630ba#:~:text=Cons%20of%20React%20Navigation)).
- **Multiplataforma:** React Navigation fue diseñado para React Native (Android/iOS) pero también **soporta la web** mediante *React Native Web*. Tiene un sistema de *linking* configurable para mapear rutas a URLs cuando se ejecuta en un navegador ([React Navigation on Web](https://reactnavigation.org/docs/web-support/#:~:text=React%20Navigation%20on%20Web%20React,well%20as%20on%20the%20web)) ([Configuring links - React Navigation](https://reactnavigation.org/docs/configuring-links/#:~:text=Configuring%20links%20,deep%20links%20in%20React)). Esto permite usar la misma lógica de navegación en móvil y en una web (aunque la configuración inicial es manual). No obstante, no ofrece *renderizado estático* ni SEO por sí mismo; simplemente maneja el historial del navegador y las URLs para hacer deep linking.
- **Control manual:** A diferencia de Expo Router, aquí el desarrollador define explícitamente las pantallas en cada navegador y sus rutas. Esto conlleva más *boilerplate* pero también la capacidad de ajustar cada detalle. Por ejemplo, se puede interceptar la forma en que se construyen las URLs o estados de navegación con funciones `getPathFromState` personalizadas, etc., cosa que Expo Router abstrae automáticamente ([Migrate from React Navigation - Expo Documentation](https://docs.expo.dev/router/migrate/from-react-navigation/#:~:text=Along%20with%20all%20the%20benefits,rendering%20on%20web%2C%20and%20more)). 

**Desventajas o consideraciones de React Navigation:**
- **Mayor complejidad inicial:** Requiere configurar navegadores, crear objetos de navegación y envolver la app con los proveedores correspondientes. Para novatos o proyectos rápidos, este esfuerzo extra se nota. La curva de aprendizaje es algo más pronunciada, sobre todo en apps grandes con navegación anidada ([React Navigation vs. Expo Router | Dev Genius](https://blog.devgenius.io/react-navigation-vs-ae9fc06630ba#:~:text=1,can%20be%20challenging%20for%20beginners)).
- **Configuración de web manual:** Si se desea soporte web, el desarrollador debe definir la configuración de linking (mapear rutas a pantallas, manejar parámetros en la URL). No es difícil pero sí un paso manual adicional, mientras que Expo Router lo hace automáticamente. También, React Navigation no puede hacer *pre-render* de páginas para SEO; la app web resultante funciona más como una SPA tradicional.
- **Peso en la app:** React Navigation es una dependencia adicional con muchas funcionalidades. Expo Router al final también la incluye, pero si uno no usa Expo, igualmente React Navigation añade cierto peso (aunque suele ser aceptable para la mayoría de apps).
- **Multiplataforma (Windows):** React Navigation funciona en cualquier entorno React Native (Android, iOS, web via RN Web). Para React Native Windows, es principalmente JavaScript así que podría funcionar, pero es posible que ciertos navegadores (ej. Drawer que depende de Gestos nativas) no estén implementados en Windows. La documentación oficial no menciona Windows explícitamente, por lo que su soporte en esa plataforma puede requerir pruebas o contribuciones de la comunidad.

En resumen, React Navigation es **robusta y altamente personalizable** – la elección segura para aplicaciones complejas o fuera del ecosistema Expo. Ofrece **mayor control** al desarrollador al costo de más configuración y conocimiento necesario. Es compatible con Expo (puede usarse en un proyecto Expo en lugar de Expo Router si se desea) y también con proyectos *bare* React Native.

### Otras alternativas de navegación

Además de las dos anteriores, existen otras soluciones, aunque con consideraciones particulares:

- **React Native Navigation (RNN) de Wix:** Es una librería de navegación distinta, que *no* se basa en JavaScript/React Navigation sino que utiliza **navegación 100% nativa** en cada plataforma. Esto logra transiciones y rendimiento muy cercanos a apps nativas puras. Puede ser ventajosa para aplicaciones que necesitan una navegación extremadamente fluida en Android/iOS o aprovechar componentes nativos de navegación. **Desventaja:** No es compatible con React Native Web, por lo que **no sirve para la parte web**. Tampoco se integra fácilmente con Expo (requiere ejectar, porque usa módulos nativos). Su API es diferente a React Navigation, lo que añade complejidad. Dado que nuestro proyecto requiere también web, RNN quedaría descartada salvo que se hicieran dos implementaciones separadas (una para web con React Router, por ejemplo, y RNN para móvil), lo cual añade mucha complejidad innecesaria.
- **React Router + React Native Web:** Algunas aplicaciones web-móvil unificadas optan por usar React Router (el router típico de React web) para gestionar la navegación en la versión web, mientras en móvil usan React Navigation, y luego tratan de compartir código de pantalla con una capa adaptadora (ej. usando una librería llamada *Solito* para compartir rutas). Este enfoque funciona, pero Expo Router precisamente nació para evitar tener que mantener dos sistemas distintos. Solito + Next.js + React Navigation era una solución popular antes; Expo Router unifica esa idea en uno solo. Por ello, usar React Router separadamente solo tendría sentido si se prefiere una arquitectura Next.js para web por algún motivo y React Navigation para móvil. Sin embargo, dado que Expo Router ya ofrece rutas web con Next.js-like routing, no parece necesario salirse de Expo Router/React Navigation.
- **Otros routers experimentales:** Por ejemplo, *TanStack Router* o *wouter* u otros routers universales. En React Native no son comunes; la mayoría de devs usan los anteriores. Expo Router de hecho aprovecha la experiencia de Next.js routing para RN.

**Comparativa de soluciones de enrutamiento:** A continuación se resumen las opciones principales de navegación, evaluadas frente a los criterios clave:

| Solución de Routing             | Facilidad de desarrollo                        | Rendimiento y características        | Soporte multiplataforma              | Limitaciones relevantes             |
|---------------------------------|-----------------------------------------------|--------------------------------------|--------------------------------------|-------------------------------------|
| **Expo Router** (Expo/React Nav)| **Alta.** Configuración casi cero gracias al routing por convención; ideal para empezar rápido ([Expo Router vs React Navigation: A Comprehensive Comparison | Attract Group](https://attractgroup.com/blog/expo-router-vs-react-navigation-a-comprehensive-comparison/#:~:text=,and%20mobile%20without%20extra%20configuration)). Integración perfecta con Expo CLI y Expo Go. | Basado en React Navigation, rendimiento nativo. Añade deep linking automático, URLs para web, *lazy loading* y *static pre-render* para SEO ([Migrate from React Navigation - Expo Documentation](https://docs.expo.dev/router/migrate/from-react-navigation/#:~:text=Pitch)). | **Android/iOS/Web** soportados de forma unificada (un solo código). Windows nativo no soportado directamente por Expo; se usaría versión web en Windows o ejectar. | Menos personalizable en casos extremos. Algunas restricciones en parámetros (solo tipos simples en URLs) ([Exploring Navigation Solutions in React Native: Expo Router vs. React Navigation | by Pallavikhedle | Medium](https://medium.com/@pallavi8khedle/exploring-navigation-solutions-in-react-native-expo-router-vs-react-navigation-37c270d45a7b#:~:text=developers%2C%20React%20Navigation%20boasts%20extensive,contributed%20resources%2C%20and%20ongoing%20support)). Nueva (menos probada que React Nav). Requiere estructura de archivos específica. |
| **React Navigation**           | **Media.** Requiere definir manualmente stacks y screens; algo de curva de aprendizaje si la navegación es compleja ([React Navigation vs. Expo Router | Dev Genius](https://blog.devgenius.io/react-navigation-vs-ae9fc06630ba#:~:text=1,can%20be%20challenging%20for%20beginners)). Buena documentación y ejemplos disponibles. | Muy **flexible**: múltiples tipos de navegadores (pilas, tabs, drawer) combinables ([Exploring Navigation Solutions in React Native: Expo Router vs. React Navigation | by Pallavikhedle | Medium](https://medium.com/@pallavi8khedle/exploring-navigation-solutions-in-react-native-expo-router-vs-react-navigation-37c270d45a7b#:~:text=1,contributed%20resources%2C%20and%20ongoing%20support)). Permite transiciones personalizadas, control total. Rendimiento bueno, aunque las animaciones van en JavaScript (no tan fluidas como nativas puras). | **Android/iOS/Web**. Web mediante React Native Web con deep linking configurable ([React Navigation on Web](https://reactnavigation.org/docs/web-support/#:~:text=React%20Navigation%20on%20Web%20React,well%20as%20on%20the%20web)). No ofrece SEO nativo (SPA puro). En **Windows**, teóricamente funciona (JS puro), pero algunas gestos/transiciones podrían no estar implementados. | Requiere más código y configuración (declare routes manualmente). Para web, configuración de linking adicional. Menos “automágico” que Expo Router. Documentación extensa pero puede ser abrumadora para novatos. |
| **React Native Navigation** (Wix)| **Baja con Expo.** No compatible sin ejectar (requiere instalación nativa). API distinta a React Navigation, aprendizaje aparte. | **Nativo puro**: cada pantalla usa controladores nativos, animaciones ultra fluidas. Excelente rendimiento en transiciones complejas. | **Android/iOS** únicamente. **No soporta Web ni Windows.** Pensado solo para apps móviles puras. | No usable con Expo Managed. Sin soporte web; no se ajusta al requisito multiplataforma web. Comunidad más reducida vs React Navigation. |
| **React Router + RN Web**      | **Media-Alta.** En la web facilita SEO y Next.js, pero integrar con RN móvil requiere patrones adicionales (Solito) y duplicar lógica de rutas. | En web, rendimiento de Next.js/SPA. En móvil, React Navigation independiente. No hay una solución unificada; mayor complejidad de mantenimiento. | **Web** (React Router) + **Android/iOS** (React Navigation), pero como sistemas separados. Windows podría usar la web. | Duplicación de esfuerzo. Susceptible a inconsistencias entre plataformas. Solo viable si se desea aprovechar Next.js por separado. |

*En términos generales*, para una app Expo con web, **Expo Router** aparece como la mejor elección por su **sencillez y soporte universal de URL**. **React Navigation** seguiría siendo excelente opción si se requiere más control o ya se tiene experiencia con ella – de hecho, Expo Router es un *wrapper* de React Navigation con extras ([Migrate from React Navigation - Expo Documentation](https://docs.expo.dev/router/migrate/from-react-navigation/#:~:text=Both%20React%20Navigation%20and%20Expo,the%20concepts%20are%20the%20same)), por lo que **no son excluyentes**: se puede empezar con Expo Router y, si algo no encaja, siempre es posible usar APIs de React Navigation directamente dentro de Expo. Por otro lado, soluciones nativas puras como Wix Navigation no cumplen el requisito web, y dividir la navegación entre web y móvil con distintas librerías añade complejidad que solo se justifica en casos especiales. 

**Conclusión de enrutamiento:** Dado el escenario (Expo, multiplataforma incluyendo web, necesidad de rápido desarrollo pero también posibilidad de escalabilidad), **Expo Router** es muy recomendable. Aprovecha las ventajas de React Navigation pero eliminando fricción en Expo y habilitando la web sin configuración adicional ([Migrate from React Navigation - Expo Documentation](https://docs.expo.dev/router/migrate/from-react-navigation/#:~:text=Pitch)). React Navigation convencional seguiría siendo una alternativa sólida si se prefiere control detallado o si en el futuro se sale del entorno Expo.

---

## 2. Autenticación: Clerk (clerk-expo) vs Firebase Auth vs Supabase Auth vs Auth0 (y otros)

La autenticación de usuarios es otro pilar de la aplicación. Se busca comparar **Clerk (y su SDK para Expo)** con otras soluciones populares de autenticación como **Firebase Authentication**, **Supabase Auth** y **Auth0**, evaluando la integración en Expo, soporte de *login* social, compatibilidad multiplataforma y funcionamiento offline.

**Requisitos clave de autenticación:** Registro/inicio de sesión de usuarios, posiblemente con **proveedores OAuth sociales** (Google, Apple, Facebook, etc.), mantener la sesión entre reinicios de la app, y en la medida de lo posible permitir operar offline (al menos que la sesión persista sin conexión). Dado que la app es local-first, podría necesitar que el usuario pueda usarla offline una vez autenticado, sincronizando cuando vuelva a haber conexión.

### Clerk (clerk-expo)

[Clerk](https://clerk.dev) es una plataforma de gestión de identidades relativamente nueva que ha ganado popularidad por ofrecer componentes de UI ya hechos y una integración sencilla en aplicaciones web y móviles. **Clerk Expo** es el SDK específico para React Native/Expo. Características de Clerk:

- **Integración con Expo:** Clerk ofrece un SDK oficial para Expo (`@clerk/clerk-expo`) con componentes de interfaz preconstruidos (pantallas de login, forms) y *hooks* para manejar usuarios. Está diseñado para funcionar dentro de aplicaciones Expo (incluso en Expo Go durante desarrollo). Esto reduce mucho el trabajo de implementar pantallas de autenticación, ya que Clerk provee flujos listos y seguros.
- **Autenticación multifactor y social:** Clerk soporta diversos métodos de auth: email/password, envío de códigos (OTP), Web3 wallets, y múltiples proveedores OAuth sociales comunes (Google, GitHub, Facebook, Twitter, Apple, etc.) ([Sign-up & Sign-in: Social connections (OAuth) - Clerk](https://clerk.com/docs/authentication/social-connections/overview#:~:text=Learn%20how%20to%20effortlessly%20add,Google%2C%20Facebook%2C%20Github%20and%20more)). Activar proveedores sociales es tan sencillo como configurarlos en el panel de Clerk y habilitarlos para la aplicación (por ejemplo, un usuario reporta en Reddit que solo debió activar las conexiones sociales deseadas en el dashboard de Clerk) ([Problem with clerk authentication : r/expo - Reddit](https://www.reddit.com/r/expo/comments/16rbvja/problem_with_clerk_authentication/#:~:text=Problem%20with%20clerk%20authentication%20%3A,Downvote)). Esto lo pone a la par de Auth0 en cuanto a amplitud de opciones sociales.
- **UI y experiencia de usuario:** Una de las fortalezas de Clerk es traer **componentes de UI personalizables** para login/registro, recuperación de contraseña, perfil de usuario, etc. Esto agiliza el desarrollo ya que no hay que diseñar estas pantallas desde cero. La apariencia es moderna y se puede adaptar a la marca. Otras soluciones como Firebase o Supabase ofrecen principalmente APIs, pero no un UI completo (Firebase tiene *FirebaseUI* para web nativo, pero no para RN; Supabase tiene algunos componentes para web también, pero en RN tocaría implementarlo o usar terceros).
- **Sesiones persistentes y manejo de tokens:** Clerk gestiona internamente la persistencia de la sesión del usuario. Provee métodos para obtener el token JWT o de sesión actual (`getToken()`), que se usan para llamadas a APIs protegidas. Importante: Clerk ha incorporado recientemente una **funcionalidad experimental de soporte offline** en Expo, permitiendo cachear credenciales y recursos del usuario para inicializar la app sin conexión ([Expo: Enable offline support in your Expo app](https://clerk.com/docs/references/expo/offline-support#:~:text=The%20Clerk%20Expo%20SDK%20provides,without%20requiring%20an%20internet%20connection)) ([Expo: Enable offline support in your Expo app](https://clerk.com/docs/references/expo/offline-support#:~:text=,disruptions%20caused%20by%20network%20failures)). Con `ClerkProvider` y la propiedad `__experimental__resourceCache`, la app Expo puede arrancar y obtener el usuario autenticado desde caché si no hay red ([Expo: Enable offline support in your Expo app](https://clerk.com/docs/references/expo/offline-support#:~:text=It%20offers%20the%20following%20benefits%3A)). Esto significa que un usuario previamente autenticado puede seguir usando la app offline (Clerk devuelve los datos de usuario y un token almacenado seguro). Esta característica está en beta, pero muestra que Clerk está considerando el caso offline.
- **Developer Experience:** Clerk es *developer-friendly*. Su documentación es elogiada por la claridad, y el producto en general se percibe muy pulido ([Comparing Auth from Supabase, Firebase, Auth.js, Ory, Clerk and others](https://blog.hyperknot.com/p/comparing-auth-providers#:~:text=Clerk%20is%20a%20polished%20solution,beautiful%2C%20as%20is%20their%20documentation)). Ofrece un dashboard administrativo web para ver usuarios, ajustar políticas (por ej. duración de sesión configurable hasta 10 años si se desea ([Comparing Auth from Supabase, Firebase, Auth.js, Ory, Clerk and others](https://blog.hyperknot.com/p/comparing-auth-providers#:~:text=Have%20a%20look%20at%20configuring,what%20I%20was%20looking%20for))) y monitorear autenticaciones. En aplicaciones Next.js/Web Clerk es muy sencillo de integrar con sus Provider y componentes. En Expo, el SDK facilita el *OAuth flow* redirigiendo a la web o usando un WebView para el login social (es necesario configurar URLs de callback en el dashboard de Clerk, pero hay guías para ello).

**Limitaciones y consideraciones de Clerk:**
- **Precio:** Clerk es un servicio comercial. Tiene un plan gratuito limitado (hasta 5 mil usuarios activos al mes con funciones básicas, según documentación pública a 2023) y luego planes de pago que escalan con la cantidad de usuarios. Un análisis señala que 10,000 usuarios activos/mes costarían unos \$550 en el plan Business ([Comparing Auth from Supabase, Firebase, Auth.js, Ory, Clerk and others](https://blog.hyperknot.com/p/comparing-auth-providers#:~:text=)). Si la app es de modelo *freemium* con muchísimos usuarios no pagos, esto podría resultar caro (p.ej. con solo 1-2% de usuarios de pago, $550 podría ser la mitad de los ingresos) ([Comparing Auth from Supabase, Firebase, Auth.js, Ory, Clerk and others](https://blog.hyperknot.com/p/comparing-auth-providers#:~:text=would%20be%20max%201,for%20a%20polished%20auth%20solution)). Sin embargo, para aplicaciones con usuarios de alto valor o de empresa, pagar ~\$0.055 por usuario activo puede ser aceptable por la calidad del servicio (Clerk ha logrado inversión y su producto es sólido ([Comparing Auth from Supabase, Firebase, Auth.js, Ory, Clerk and others](https://blog.hyperknot.com/p/comparing-auth-providers#:~:text=Clerk%20is%20a%20polished%20solution,beautiful%2C%20as%20is%20their%20documentation))). En comparación, Firebase Auth y Supabase Auth son gratuitos o muy económicos hasta cierto umbral de MAUs.
- **Vendor lock-in:** Integrar Clerk significa confiar en un servicio externo para identidades. Migrar a otra solución más adelante podría requerir que los usuarios revaliden contraseñas o portar datos de OAuth (lo cual no es trivial). Siempre es un riesgo con servicios de Auth como Auth0/Clerk.
- **Requiere Internet para login:** Obviamente para el proceso de autenticación inicial se necesita conexión. Clerk no permite “registrar usuarios offline” (ninguna solución mainstream lo hace). Lo que sí permite es funcionar offline **después** de haber iniciado sesión previamente gracias al cache de token (como se mencionó). Si un usuario nunca ha hecho login y está offline, no podrá hacerlo hasta conectarse.

En general, Clerk se destaca por su **facilidad de integración en Expo** (SDK dedicado, UI lista) y por soportar de forma **amplia autenticación social** y flujos modernos, con un plus interesante de **inicio offline con sesión cacheada** ([Expo: Enable offline support in your Expo app](https://clerk.com/docs/references/expo/offline-support#:~:text=,disruptions%20caused%20by%20network%20failures)). Es ideal para equipos pequeños que quieren “delegar” todo el manejo de usuarios a un servicio especializado.

### Firebase Authentication

Firebase Auth es la solución de autenticación de Google Firebase, muy probada en multitud de aplicaciones. Sus puntos principales:

- **Integración con Expo:** Firebase Auth se puede usar en Expo mediante la biblioteca JavaScript oficial de Firebase (no requiere módulos nativos para Auth básica). Configurar Firebase Auth implica inicializar el SDK con las credenciales del proyecto y usar métodos como `signInWithEmailAndPassword`, `signInWithCredential` (para OAuth) etc. Para **login social**, Firebase ofrece atajos para Google, Facebook, Apple, etc., pero en entorno móvil Expo usualmente esto se implementa usando *Web OAuth flows* (por ejemplo, `GoogleAuthProvider` junto con `AuthSession` de Expo para obtener un token de Google y pasarlo a Firebase). Firebase no proporciona una UI nativa en RN; el desarrollador implementa las pantallas o usa librerías de terceros. Aun así, hay guías y el proceso es conocido.
- **Características:** Admite email/contraseña, teléfono (SMS OTP), y OAuth con Google, Facebook, Twitter, Microsoft, Apple, GitHub, etc. Maneja la gestión de usuarios, verificación de email, resets de contraseña, etc. Todo a través de llamadas a su API. Los SDKs de Firebase guardan automáticamente la sesión (el token de actualización) en el dispositivo, de modo que si el usuario cierra y abre la app, permanece autenticado sin tener que re-login (hasta que expire el token y falle la renovación, normalmente tokens duran ~1h pero se renuevan con refresh tokens detrás de escena).
- **Persistencia offline:** Firebase Auth en sí no tiene un “modo offline” más allá de la persistencia mencionada de credenciales. Es decir, un usuario autenticado puede abrir la app sin conexión y Firebase le dará el usuario actual de la sesión cacheada. Sin embargo, cualquier acción que requiera contactar al servidor (p. ej. reautenticar, refrescar token expirado, o acceder a perfiles de otros usuarios) no funcionará offline. Lo importante es que **la sesión perdura offline** (hasta cierto límite). Esto permite que, en una app local-first, si el usuario ya inició sesión antes de perder la conexión, pueda seguir usando la app con sus datos locales.
- **Multiplataforma:** Firebase Auth tiene SDKs nativos para Android, iOS, Web. En Expo (que usa JS), se usa el SDK web que funciona bien en React Native. En Windows (si se hace app UWP) no hay SDK nativo oficial, pero podría usarse el SDK web de Firebase Auth dentro de la app (si tiene un motor web). Alternativamente, para Windows quizá la app se empaquete como Electron o PWA, donde el SDK web funciona sin problemas. En general, Firebase ofrece **amplio soporte multiplataforma** (incluso Unity, C++ etc., aunque esos no aplican aquí).
- **Ventajas adicionales:** Si ya se va a usar Firebase para otras cosas (p. ej. Firestore, Storage), usar Firebase Auth encaja perfectamente, y habilita **seguridad con reglas** (ej. reglas de Firestore que usan `auth.uid`). Además, es gratuito hasta proyectos de tamaño considerable (Firebase Auth gratis hasta 10k verificaciones de teléfono/mes, OAuth ilimitado con ciertas cuotas de uso, etc.). La escala está probada – aplicaciones con millones de usuarios usan Firebase Auth. También simplifica mucho la implementación de *push notifications* segmentadas o personalización, ya que se integra con otros servicios de Firebase.

**Limitaciones de Firebase Auth:**
- **Interfaz:** No provee interfaces pre-hechas en RN, se debe crear las pantallas de login/registro manualmente (o integrar algún paquete UI externo).
- **OAuth en Expo:** Mientras Clerk/Auth0 abstraen el OAuth, con Firebase en Expo típicamente se usan *detours*: para Google, usar `AuthSession` para obtener un token Google y luego pasar a Firebase (`signInWithCredential`), o usar el flujo *web popup* de Firebase Auth (que en RN termina abriendo un navegador). Son pasos adicionales a configurar (claves OAuth en Google console, deep link redirect, etc.). Es factible pero un poco laborioso comparado con Clerk que ya lo trae integrado.
- **No roles/permisos avanzados:** Firebase Auth solo autentica; para autorización fina (roles de usuario) hay que manejarlo aparte (p. ej. almacenando roles en la base de datos).
- **Modelo de datos fijo:** Los usuarios de Firebase Auth tienen campos predefinidos (email, nombre, foto, etc.). Si se requieren atributos personalizados, hay que guardarlos en Firestore/Realtime DB aparte. Otras soluciones como Supabase Auth permiten “sincronizar” con perfiles en la base SQL, y Auth0/Clerk permiten metadata de usuario también. Firebase Auth tiene *custom claims*, pero son globales por usuario, no un perfil completo.

En general, Firebase Auth es **fiable, gratuito en su mayoría y multiplataforma**. En Expo funciona bien aunque los flujos de OAuth requieren un poco de trabajo. No ofrece offline más allá de la sesión persistente, lo cual suele ser suficiente: es decir, con Firebase Auth el usuario puede trabajar offline usando datos locales mientras su token JWT siga válido en memoria (o hasta que Firebase necesite refrescarlo, lo cual sin internet no podrá y eventualmente podría caducar el acceso a servicios protegidos, pero eso suele tomar horas).

### Supabase Auth

Supabase es una plataforma Backend-as-a-Service abierta, basada en Postgres. Supabase Auth es su módulo de autenticación que se inspira en Firebase Auth pero usando un servidor GoTrue (el mismo de Netlify Identity/Beta). Características:

- **Integración con Expo:** Supabase proporciona un paquete JS (`@supabase/supabase-js`) que funciona en React Native/Expo. La integración es similar a Firebase: inicializar el cliente con URL y *anon key*, luego usar métodos como `supabase.auth.signInWithPassword({email, password})` o `signInWithOAuth({ provider: 'google' })`. Para *login* social, Supabase Auth abre una URL en el navegador (por ejemplo, la página de autenticación de Supabase) y redirige de vuelta mediante deep link. En Expo, esto implica configurar la *redirect URL* (que en desarrollo puede ser algo como `exp://...redirect`) y manejar ese retorno. Supabase no ofrece componentes de UI listos en React Native; el desarrollador implementa las pantallas o integra una librería UI (hay algunas iniciativas de comunidad).
- **Soporta múltiples métodos:** Email/contraseña, magia por correo (*magic link*), OAuth con proveedores populares (Google, Facebook, GitHub, Gitlab, Discord, Twitter, Apple, etc.). Configurar OAuth en Supabase requiere obtener credenciales API de cada proveedor y añadirlas en la configuración del proyecto (similar a Firebase). También soporta SMS OTP (vía integración con third-parties) y WebAuthn (login con dispositivos).
- **Integración con base de datos:** Una diferencia es que en Supabase, cuando un usuario se registra, típicamente se crea una fila asociada en la tabla `auth.users`. Se puede configurar un *hook* para insertar un perfil en otra tabla pública. El desarrollador maneja roles/permisos usando Postgres roles o mediante Row-Level Security en tablas vinculadas al user ID. Esto da más **flexibilidad para datos de perfil** comparado con Firebase Auth.
- **Persistencia de sesión:** El cliente de Supabase Auth almacena el token de acceso y refresh token localmente (en AsyncStorage o SecureStore). Esto permite reanudar la sesión sin conexión de manera similar a Firebase – los datos de usuario actual están disponibles offline. Supabase también implementó recientemente la capacidad de auto-refrescar el token de forma transparente. Si la app está offline cuando toque refrescar, probablemente el token expire hasta reconexión, pero el usuario aún figurará logueado localmente (habría que manejar errores hasta que vuelva conexión).
- **Multiplataforma:** Al ser básicamente un servicio web (API REST/GraphQL), Supabase Auth funciona en cualquier plataforma con su librería JS. Para web hay un widget simple opcional (Supabase Auth UI) pero en RN no. En Windows, se puede usar igual que en Expo Android/iOS (mientras haya un entorno JS). No hay SDK nativo para .NET o similar, pero se podría llamar a la REST API directamente si hiciera falta. En resumen, es suficientemente multiplataforma a nivel cliente web/JS.

**Limitaciones de Supabase Auth:**
- **Offline support:** Supabase no ofrece un mecanismo offline-first integrado para Auth. De hecho, hay discusiones donde el equipo reconoce que implementar *offline support* completo es muy difícil dado que exponen directamente Postgres (lo que hace complicado sincronizar el estado sin conexión) ([Using Supabase offline #357 - GitHub](https://github.com/orgs/supabase/discussions/357#:~:text=Using%20Supabase%20offline%20%23357%20,all%20of%20Postgres%27%20API%20surface)). No obstante, para Auth en concreto, la expectativa es similar a Firebase: tener sesión persistida pero no más. No hay algo como el *offline cache* experimental que Clerk tiene. 
- **Madurez y ecosistema:** Supabase Auth es más nuevo que Firebase Auth. Puede haber menos recursos de comunidad específicamente para RN, aunque su documentación es buena. Algunos detalles (como la redirección OAuth en aplicaciones móviles) fueron agregando mejoras con el tiempo. Para Expo en particular, a veces se apoya en *AuthSession* igual que Firebase para el callback. No es difícil pero es un área donde Clerk/Auth0 aún tienen ventaja en DX.
- **Dependencia del backend principal:** Si se usa Supabase Auth, es probable que se use también Supabase DB y Storage. Esto es bueno si todo encaja, pero hay cierto *lock-in* en el stack Supabase. Migrar Auth a otra plataforma posteriormente costaría esfuerzo (exportar usuarios, etc.).
- **Cuotas:** Supabase es gratuito hasta cierto punto (bastante generoso para desarrollo: usuarios ilimitados, solo se mide el consumo de recursos). En producción, sus planes pagos son competitivos y uno puede auto-hospedar supabase para control total. 

En general, Supabase Auth es **muy similar a Firebase Auth en funcionalidades**, pero en un ecosistema open source. Si se planea usar Supabase (Postgres) para datos, tiene sentido usar su Auth para integrarlo con reglas de Row Level Security fácilmente. En Expo funciona correctamente, pero no simplifica la interfaz como Clerk – requiere implementar flows de UI. Su capacidad offline es limitada a mantener la sesión activa; no permite autenticación inicial offline.

### Auth0

Auth0 es un proveedor de identidad veterano y orientado a empresas, ahora parte de Okta. Se especializa en ofrecer un servicio de autenticación altamente configurable, con soporte de **OAuth sociales, SSO corporativo (SAML, OIDC), multifactor, reglas personalizadas, etc.**. 

- **Integración con Expo:** Auth0 no tiene SDK específico para Expo, pero sí uno para React Native (`react-native-auth0`) que requiere configuración nativa (lo cual no funciona en Expo Go a menos que se use la variante Dev Client). Alternativamente, se integra mediante *AuthSession* en Expo: es decir, redirigir a las páginas de Auth0 (un dominio `.auth0.com`) y después de login obtener el token. Auth0 provee muchas opciones de flujos (PKCE, implícito, etc.), lo que puede ser complejo de configurar correctamente. En Expo, lo usual es usar `AuthSession.startAsync` con la URL de autorización de Auth0.
- **Soporte de proveedores:** Auth0 soporta **prácticamente cualquier método de autenticación**: credenciales, SMS, email link, más de una docena de proveedores sociales, además de conexiones empresariales (LDAP, SAML, Google Workspace, Office365, etc.) configurables. Es muy potente en ese sentido, adecuado si la app llegara a requerir login de usuarios corporativos o similar. También tiene capacidades de *rules* o *actions* que son scripts ejecutados en cada login para implementar lógica personalizada (por ejemplo, agregar roles, bloquear ciertos usuarios, etc.).
- **UI:** Auth0 ofrece **Universal Login**, que es una página alojada en Auth0 con el formulario de acceso. Esa es la vía recomendada: redirigir al usuario a esa página (que se puede personalizar con el logo/colores) y luego volver a la app. Alternativamente, uno puede usar SDKs para crear una UI nativa personalizada, pero en RN Expo sería manual. Universal Login facilita mucho la implementación (Auth0 maneja las credenciales en su dominio, lo cual mejora seguridad).
- **Sesión offline:** Similar a Clerk y otros, Auth0 mantendrá un token de sesión en el dispositivo (generalmente un refresh token si se habilitó). Auth0 en aplicaciones SPAs suele no dar refresh token largo por defecto (por seguridad), pero en apps nativas se puede solicitar *Refresh Token Rotation*. Con ello, la app puede seguir usándose offline mientras el JWT no expire; si expira y no hay conexión, se requeriría volver a login. No hay un “modo offline” particular aparte de esto.
- **Multiplataforma:** Auth0 puede ser usado en cualquier plataforma, pero se siente más natural en web y aplicaciones con backend. En RN, funciona vía WebAuth (similar a expo-auth-session) o con el SDK RN (que invoca Safari tabs). En Windows, una app podría abrir la web de Auth0 en el navegador predeterminado para login. En general es agnóstico porque es OAuth2/OIDC estándar.

**Limitaciones de Auth0:**
- **Complejidad y costo:** Auth0 es muy completo, pero esa potencia trae complejidad. La configuración de aplicaciones, callbacks, permisos de API puede ser confusa al inicio. Para un caso de uso simple, Auth0 puede sentirse “demasiado” (Clerk simplifica cosas que Auth0 deja configurables). Además, el costo: Auth0 tiene un plan gratuito para ~7k usuarios activos, pero sus planes de pago empresarial escalan rápidamente en precio, a menudo más caros que Clerk. Para startups, Auth0 a veces es un overkill a menos que se necesite SAML/enterprise logins.
- **Expo compatibility:** Usar Auth0 en Expo *managed* puede requerir trabajo extra comparado con Clerk. No hay un *SDK Expo* oficial, hay que armar el flujo de OAuth manualmente. 
- **Vendor lock-in similar:** Exportar usuarios de Auth0 es posible, pero implica manejar contraseñas hasheadas, etc. Es un proveedor más, con las mismas consideraciones de depender de servicio externo.

Auth0 es apropiado si se requieren características de nivel empresarial o máxima flexibilidad en tipos de login. En nuestro caso (usuarios estándares, social login, etc.), quizá sea más de lo necesario. 

### Otras soluciones de autenticación

Existen otras alternativas que vale mencionar brevemente:

- **OAuth nativo/manual:** En lugar de usar un servicio, se podría implementar registro/login propio (por ejemplo, con una base de datos de usuarios en el backend de la app). Dada la complejidad de hacerlo bien (almacenamiento seguro de contraseñas, manejo de sesiones, reset password, OAuth sociales con múltiples proveedores), normalmente no vale la pena reinventarlo. Servicios como Firebase, Supabase, Clerk o Auth0 resuelven esto de forma segura y testada.
- **Ory / Kratos:** Ory Kratos es una solución open-source de gestión de identidades que se puede auto hospedar. Podría ser una opción si se busca no depender de terceros pero tener un sistema robusto. Sin embargo, integrar Kratos con React Native aún requeriría implementar flujos (Kratos provee APIs, no tanto UI).
- **Supertokens:** Es otra opción open-source que provee componentes de login y manejo de sesiones tanto en frontend como backend. Podría integrarse en RN via WebViews o endpoints.
- **AWS Cognito:** Servicio de Amazon similar a Firebase Auth. Ofrece OAuth sociales, etc., pero su uso suele ser más engorroso a nivel de SDKs y requiere AWS know-how. Probablemente menos conveniente que Firebase/Supabase para este contexto.
- **Magic.link:** Servicio especializado en *passwordless* (enviar links o emails mágicos). Puede ser interesante si se desea eliminar contraseñas, pero se limitaría a ese método (puede coexistir con otros, pero Clerk por ejemplo ya ofrece OTP/email magic link también).

**Comparativa de soluciones de autenticación:**

| Solución              | Facilidad de integración en Expo                   | Autenticación social y métodos       | Multiplataforma y offline            | Limitaciones / Notas                   |
|-----------------------|----------------------------------------------------|--------------------------------------|--------------------------------------|----------------------------------------|
| **Clerk** (clerk-expo)| **Muy alta.** SDK dedicado para Expo con componentes de UI listos. Configuración rápida en pocas líneas. Maneja internamente redirecciones OAuth. | **Amplia.** Email/pass, Magic link, SMS OTP, OAuth con proveedores populares (Google, Apple, etc.) ([Sign-up & Sign-in: Social connections (OAuth) - Clerk](https://clerk.com/docs/authentication/social-connections/overview#:~:text=Learn%20how%20to%20effortlessly%20add,Google%2C%20Facebook%2C%20Github%20and%20more)). MFA opcional. | **Android/iOS/Web** con librerías oficiales. Windows vía web. **Offline:** soporta iniciar la app offline con sesión cacheada (API experimental) ([Expo: Enable offline support in your Expo app](https://clerk.com/docs/references/expo/offline-support#:~:text=,disruptions%20caused%20by%20network%20failures)). | Servicio comercial (coste por MAU, gratuito limitado) ([Comparing Auth from Supabase, Firebase, Auth.js, Ory, Clerk and others](https://blog.hyperknot.com/p/comparing-auth-providers#:~:text=)). Ecosistema relativamente nuevo. Sin soporte nativo Windows/UWP (usa web). |
| **Firebase Auth**     | **Alta.** SDK JS funciona en Expo sin nativos. Flujos sociales requieren usar WebAuth (AuthSession) manualmente. UI debe implementarse (no incluye componentes RN). | **Amplia.** Email/contraseña, teléfono (SMS), OAuth (Google, FB, Twitter, Apple, GitHub, Microsoft...). | **Android/iOS/Web** (SDKs oficiales). En Expo se usa SDK web. **Offline:** persiste sesión local, permitiendo uso offline si ya logueado. Sin modo offline-first para login nuevo. | UI no preconstruida en RN. Requiere configurar cada OAuth (ID de cliente, etc.). Sin metadatos de usuario personalizables (necesario DB adicional). Pertenece al stack Google (puede ser ventaja si se usa Firestore). |
| **Supabase Auth**     | **Alta.** SDK JS (supabase-js) en Expo. Similar a Firebase en uso. Sin UI lista en RN. OAuth vía navegador. | **Amplia.** Email/pass, Magic links, OAuth (Google, Apple, etc.), soporta también SSO SAML/OIDC en planes empresariales. | **Android/iOS/Web** (SDK JS universal). **Offline:** sesión persistente local (JWT/refresh). No hay sync offline extra (debe haber conexión para validar nuevas credenciales). | Proyecto open-source/self-host posible. Menos maduro que Firebase pero rápido en evolución. Depende de tener Supabase backend. |
| **Auth0**             | **Media.** Necesita implementar flujo OAuth manual o usar SDK RN (requiere ejectar). Puede usar *Universal Login* alojado para simplificar. | **Muy amplia.** Gran cantidad de proveedores sociales, enterprise SSO, passwordless, MFA, etc., personalizables. | **Android/iOS/Web** (OAuth estándar). **Offline:** tokens persistidos, similar a otros (no offline login). | Servicio robusto pero complejo. Coste elevado en niveles altos. Puede ser excesivo si solo se necesita social login básico. Requiere cuidado en configuración. |
| **Otras (Ory, etc.)** | **Baja.** Soluciones self-host requieren mucho desarrollo de integración (no plug-and-play en Expo). | Varía según implementación (ej. Ory soporta email/pass, social con config, etc.). | Varía (self-host te da control pero no hay SDK Expo específico; habría que usar WebViews o API HTTP). | Demandan más esfuerzo técnico, recomendables solo si evitar terceros es prioritario y se cuenta con backend propio. |

**Recomendación autenticación:** Para la mayoría de aplicaciones Expo con necesidad de rapidez, **Clerk** destaca por ofrecer la ruta más sencilla y con mejor experiencia de usuario, especialmente si el presupuesto lo permite o la escala de usuarios inicial está cubierta en el plan gratuito. Ofrece social login sin dolores de cabeza y se integra perfectamente con Expo (incluso con expo-router, hay tutoriales mostrando su uso conjunto ([Master React Native Authentication with Expo Router & Clerk](https://www.youtube.com/watch?v=zh6Sc1flK2g#:~:text=Master%20React%20Native%20Authentication%20with,notch%20security%20for%20your))). 

**Firebase Auth** es una alternativa sólida si se prefiere una solución gratuita y ya familiar, asumiendo que el desarrollador implementará las pantallas de login. Combina bien si también se usan otros servicios de Firebase (Firestore para datos, Storage para archivos, etc.), pero no trae componentes de UI listos.

**Supabase Auth** será ideal si el backend de datos va a ser Supabase (PostgreSQL) – así todo queda unificado. Requiere un poco más de configuración manual para OAuth similar a Firebase, pero nada prohibitivo. Tiene la ventaja de ser open source y desplegable por uno mismo, útil si se necesita auto-hospedar en un futuro.

**Auth0** podría considerarse si se anticipa necesidad de autenticación más allá de redes sociales (por ejemplo, integración con sistemas de empresa, AD, etc.) o reglas muy personalizadas en el flujo de login. De lo contrario, su complejidad y costo pueden no justificarlo frente a Clerk o Firebase.

---

## 3. Backend *local-first* y sincronización: Cloudflare Durable Objects vs Convex vs otras soluciones

Para una aplicación *local-first* es crucial la elección de la arquitectura de datos: cómo almacenar los datos localmente en el dispositivo, y cómo sincronizarlos eficientemente con un backend cuando haya conexión. El escenario incluye **datos complejos y voluminosos**: tablas con muchas filas y relaciones, archivos multimedia grandes (videos, audios, imágenes), datos de gráficos, textos extensos, e incluso escritura a mano alzada o vectorial. Se requiere una sincronización rápida y posiblemente en tiempo real cuando se está en línea, pero la aplicación debe ser totalmente funcional offline (consultando y modificando datos locales).

Existen diversos enfoques para esto, que podemos agrupar a grandes rasgos en dos partes: **1) Soluciones de backend/servidor con sincronización en tiempo real**, y **2) Soluciones de base de datos local con replicación.** Algunas combinan ambos conceptos. A continuación se analizan las opciones mencionadas: **Cloudflare Durable Objects**, **Convex**, y alternativas como **SQLite local con bibliotecas offline (RxDB, WatermelonDB)**, servicios en la nube tipo **Firebase/Firestore, Supabase, Appwrite**, y proyectos de backend ligero como **PocketBase**, entre otros.

### Cloudflare Durable Objects (DO)

Los **Durable Objects** de Cloudflare Workers son una tecnología de backend relativamente nueva (introducida en 2021, expandida en 2023-2024) que proporciona **objetos con estado consistente en la nube distribuida de Cloudflare**. Conceptualmente, un Durable Object es como una instancia singleton para una clave dada, que corre código JavaScript (Workers) en la ubicación perimetral (edge) más cercana a los usuarios, manteniendo un estado en memoria y almacenamiento persistente. 

¿Cómo encaja esto en un esquema local-first? Posibles beneficios:
- **Coordinación y consistencia:** Un DO puede actuar como **autoridad central** para cierta porción de datos, recibiendo actualizaciones de múltiples clientes y resolviendo conflictos. Por ejemplo, se podría tener un Durable Object por cada documento/proyecto de usuario. Dado que Cloudflare garantiza que todas las peticiones a un mismo DO van al mismo hilo único ([Zero-latency SQLite storage in every Durable Object](https://blog.cloudflare.com/sqlite-in-durable-objects/#:~:text=Durable%20Objects%20,to%20the%20same%20DO%20instance)), esto evita condiciones de carrera; el DO puede serializar las escrituras y asegurar la consistencia. Para una app donde múltiples dispositivos modifican datos offline y luego sincronizan, un DO podría implementar la lógica de fusión (merge) de cambios en un solo lugar.
- **Baja latencia global:** Cloudflare ejecuta Workers en data centers alrededor del mundo. El DO se inicia en la ubicación del primer request y luego puede migrar según la mayoría de tráfico. Esto significa que usuarios regionales obtienen buena latencia. En sincronización en tiempo real, esto ayuda a rapidez.
- **Almacenamiento integrado:** Originalmente los DO ofrecían un almacenamiento tipo KV (clave-valor) simple. **Desde finales de 2024**, Cloudflare habilitó **SQLite dentro de los Durable Objects** ([Zero-latency SQLite storage in every Durable Object](https://blog.cloudflare.com/sqlite-in-durable-objects/#:~:text=Durable%20Objects%20,nevertheless%20being%20durable%20and%20consistent)). Esto es muy relevante: ahora cada DO puede tener una **base de datos SQL completa (SQLite)** embebida, consultable con queries. Esto combina lo mejor de dos mundos: la conveniencia de SQLite (consultas relacionales, índices) con la naturaleza distribuida de DO. Para nuestro caso, se podría hacer que cada DO tenga tablas espejo de las del cliente, y sincronizar mediante queries diffs. Cloudflare indica que el acceso a SQLite dentro del DO es de **latencia prácticamente cero** porque ocurre en el mismo proceso/hilo que el código, sin overhead de red ([Zero-latency SQLite storage in every Durable Object](https://blog.cloudflare.com/sqlite-in-durable-objects/#:~:text=Durable%20Objects%20,nevertheless%20being%20durable%20and%20consistent)). El tamaño de los datos en un DO es limitado (antes ~10 MB, con SQLite posiblemente decenas de MB o más, pero no gigabytes a menos que se fragmenten en varios DO).
- **Escalabilidad y concurrentes:** Los DO están pensados para manejar muchos usuarios escalando en cantidad de instancias (cada DO independiente). No están hechos para alta *throughput* en una única instancia (cada DO corre en un solo core normalmente). Pero para coordinar sync de una doc o de un usuario van bien. También pueden iniciar websockets, lo que permitiría a clientes suscribirse a eventos en tiempo real.

**Ventajas para nuestra app:** Cloudflare DO + SQLite permitiría implementar un backend custom donde la lógica de sincronización es sumamente flexible. Se podría almacenar datos estructurados (tablas) y también referencias a archivos (p. ej. un DO podría orchestrar subida de archivos a Cloudflare R2 or similar). Cada vez que un cliente conecta, envía sus cambios locales (quizá como diffs o usando un log estilo CRDT), el DO los aplica a su DB, y envía de vuelta los cambios de otros clientes que no tuviera. Esto podría lograr una sync **rápida y optimizada**, dado que uno tiene control total del protocolo.

**Desventajas / complejidad:**
- **No es una solución plug-and-play:** Requiere desarrollar bastante lógica. A diferencia de Firebase o Supabase donde uno aprovecha un servicio existente de sync, con DO se estaría esencialmente construyendo un mini-backend a medida. Hay que codificar en JavaScript (o TypeScript) la lógica de qué hacer en cada sincronización, cómo almacenar las diffs, resolver conflictos, etc.
- **Límite de datos por DO:** Si se espera que un usuario tenga gigas de datos, un solo Durable Object quizás no sea suficiente. Habría que particionar datos en varios DO (por ejemplo, un DO por cada colección de datos o por cada grupo de documentos). Esto añade complejidad de particionado.
- **Archivos grandes:** DO no está pensado para grandes binarios directamente (hay límite de 30s por request y 128MB de memoria por Worker). Lo usual sería combinar con **Cloudflare R2 (S3 compatible)** para almacenar los archivos multimedia grandes, y usar el DO solo para almacenar metadatos y coordinar la subida. Ejemplo: el video se sube directamente del app a R2 (o a DO streaming service) pero el DO recibe la referencia y la sincroniza en la DB.
- **Costo:** Cloudflare Workers/DO tienen un modelo de facturación por millones de invocaciones y CPU time, etc. En el plan gratuito se puede experimentar, pero en producción hay que estimar costos (que suelen ser competitivos, pero no tan straightforward como supabase self-host por ejemplo).
- **Conectividad requerida para sync:** Obvio, pero si un cliente está offline, los DO no entran en juego hasta reconexión. No hay un mecanismo de *P2P sync* entre dispositivos offline directos (no scope de DO realmente).

En resumen, Cloudflare Durable Objects + SQLite es una **opción poderosa para quien desee un backend personalizado** con performance muy alta en la nube y consistencia. Para una startup pequeña, puede ser complejo de implementar pero ofrecería **control total** sobre cómo se manejan los datos complejos y las relaciones. Podría ser particularmente bueno si la app necesita **colaboración en tiempo real** (varios usuarios editando el mismo contenido simultáneamente), ya que un DO puede gestionar ese merging con la lógica que se programe.

### Convex

**Convex** (convex.dev) es un servicio backend que se autodenomina una *“plataforma de sincronización con estado”*. Su propuesta es abstraer la sincronización de datos en tiempo real entre cliente y servidor de forma que el desarrollador no tenga que manejar manualmente websockets, invalidaciones, etc. Algunas características destacadas de Convex:

- **Reactividad en tiempo real:** Convex ofrece una base de datos (tipo documento) donde las consultas que defines son **reactivas**: el servidor **empuja actualizaciones** a los clientes cuando cambia algún dato que afecta a su consulta ([Stateful Sync Platform](https://www.convex.dev/sync#:~:text=Everything%2C%20always%20in%20sync)) ([Stateful Sync Platform](https://www.convex.dev/sync#:~:text=Realtime%2C%20all%20the%20time)). Esto significa que en el front no necesitas suscribirte manualmente a cambios; simplemente lees datos con su hook y Convex mantiene esos datos actualizados automáticamente. Esta capacidad de *live queries* con consistencia es similar a Meteor or SignalR, pero Convex lo hace de forma integral en su DB.
- **Mutaciones con cola offline:** El cliente de Convex proporciona *mutations* que puedes invocar incluso sin conexión; las mutaciones se **encolan en el cliente** y se envían al servidor cuando regresa la conexión ([Stateful Sync Platform](https://www.convex.dev/sync#:~:text=Convex%20is%20a%20stateful%20sync,network%20blips%20are%20handled%20gracefully)). Esto quiere decir que la app puede permitir al usuario hacer acciones offline (crear/editar registros) usando la misma API de Convex, y la lib se encargará de sincronizarlas después. Durante el lapso offline, lógicamente, no podrá obtener confirmación del servidor, pero al menos no pierde las acciones – esto es un tipo de soporte offline fundamental.
- **Modelo de datos:** Internamente Convex usa un **almacenamiento de documentos transaccional** (no SQL, no Postgres; es su propia DB sobre un log en RDS) ([Convex vs. Supabase](https://www.convex.dev/compare/supabase#:~:text=Convex%20uses%20a%20custom%2C%20transactional,automatically%20subscribed%20to%20database%20changes)). Se maneja mediante *functions* escritas en JavaScript/TypeScript (en el backend Convex) para queries y mutaciones, en lugar de exponer consultas directas tipo SQL. Esto les permite asegurar consistencia y que todas las operaciones pasen por sus sistemas (similar a Supabase Edge Functions, pero más integrado).
- **Consistencia e integridad:** Convex garantiza transacciones ACID en sus mutaciones y una vista consistente de los datos para todos los clientes ([Stateful Sync Platform](https://www.convex.dev/sync#:~:text=Consistency%20on%20the%20server%20and,client)). Esto es importante: no es meramente eventual, buscan que lo que veas en cada cliente sea una versión consistente global.
- **Multiplataforma:** Convex tiene actualmente SDKs para web/Node. Para React Native/Expo, al ser Javascript (y usar websockets), debería funcionar; no hay dependencia nativa así que es compatible con Expo. Algunos usuarios han integrado Convex en RN apps con éxito. Convex también lanzó integraciones con Next.js RSC, etc., pero para RN es básico WS.

**Ventajas para nuestra app:**
- **Fácil desarrollo de sync:** Usar Convex implica no tener que implementar manualmente la capa de sincronización en tiempo real: la obtenemos por defecto. Se escribirían funciones Convex para, por ejemplo, obtener la lista de elementos de X usuario con sus relaciones, y esa consulta va a mantenerse actualizada en todos los dispositivos. 
- **Offline que simplemente funciona:** La cola offline de mutaciones de Convex cubre el caso en que el usuario crea/edita algo sin conexión – la lib lo guardará y lo aplicará después. Esto es más transparente que soluciones como Firestore, donde sí hay offline, pero la lógica de merges es last-write-wins (lo cual hay que manejar). Convex al tener el control en su backend podría detectar conflictos en la secuencia de mutaciones.
- **Archivos y otros datos:** Convex menciona tener *file storage* integrado y base de datos vectorial integrada ([Convex vs. Supabase](https://www.convex.dev/compare/supabase#:~:text=,and%20a%20native%20vector%20database)). Es decir, puede almacenar blobs (posiblemente en S3) y también admite almacenar vectores para hacer búsqueda por similitud (lo cual pudiera ser útil si en un futuro se indexaran embeddings de textos largos o imágenes). Esto es un valor añadido interesante en 2025: ya hay vector DB incorporada, por lo que la aplicación podría, por ejemplo, hacer búsquedas de texto semánticas o de imágenes similares usando embeddings sin desplegar infra extra.
- **Escalabilidad:** Convex se ocupa de la escalada de su backend. El desarrollador no toca servidores ni preocuparse de replicación; se paga como servicio (tiene plan gratuito para inicio, luego pago por uso). A diferencia de Cloudflare DO que requeriría uno mismo diseñar la escalabilidad, Convex intenta dártelo listo.

**Limitaciones de Convex:**
- **Base de datos no relacional tradicional:** Si bien es transaccional, Convex no expone SQL ni es un Postgres. Es más similar a Firebase Firestore o a un **store de documentos**. Si los datos son altamente relacionales, puede costar modelarlos y consultarlos sin JOINS. Convex sugiere que sus funciones pueden manejar eso (e.g., hacer varias queries y componer), pero no es un RDBMS completo.
- **Lock-in a su plataforma cerrada:** Convex es propietario. El código de funciones se puede exportar, pero no es trivial migrarlo a otro sistema. Es relativamente nuevo en el mercado, menos probado que Firebase. Confiar en él implica cierta fe en que la empresa perdure o provea continuidad.
- **Costo:** Actualmente Convex tiene un modelo de pago basado en operaciones y tiempo. Puede ser competitivo, pero habría que vigilar en caso de escalas grandes de datos (especialmente si muchos documentos).
- **Tamaño de datos locales:** Convex no almacena un caché local persistente de la base de datos completa en el dispositivo. Mantiene en memoria o en su cliente los datos necesarios para las queries activas. Si la app necesita acceder a *todos* los datos offline (no solo los consultados antes), Convex solo con su cliente no es suficiente – se tendría que implementar una capa de almacenamiento local complementaria para el modo offline completo. En contraste, si se usara una base local tipo SQLite, se podría tener toda la BD en el dispositivo accesible offline. Convex está más pensado para que offline breves (perdida de conexión momentánea) no interrumpa, pero **no reemplaza una base de datos local completa** en el dispositivo.

En síntesis, Convex facilita enormemente construir una app *online-first con buen soporte offline*, pero quizás no cubre el caso de querer tener una copia completa de todos los datos en local. Para una app local-first verdadera, probablemente se usaría Convex como sync mientras los datos primarios residen en SQLite local en cada cliente. De hecho, Convex ha publicado guías de usarlo junto con CRDTs tipo Automerge localmente ([Going local-first with Automerge and Convex - Stack](https://stack.convex.dev/automerge-and-convex#:~:text=I%27ll%20walk%20you%20through%20how,working%20with%20Automerge%20and%20Convex)). Es decir, Convex puede actuar similar a Cloudflare DO + custom logic, pero ya implementado y con menos esfuerzo por parte del dev.

### SQLite local + RxDB / WatermelonDB (y similares)

Otro camino es apostar a una base de datos local robusta en cada dispositivo, que permita trabajar offline sin restricciones, y luego sincronizar con algún servicio o entre pares. Dos bibliotecas mencionadas son **WatermelonDB** y **RxDB**, ambas enfocadas en *offline-first*:

- **SQLite local:** Tanto WatermelonDB como RxDB pueden usar SQLite como almacenamiento en React Native. SQLite es prácticamente sinónimo de **base de datos relacional local** y viene en todos los móviles. Su rendimiento es excelente manejando miles o millones de registros localmente. Permite consultas complejas (JOINs, índices) y almacenar datos estructurados.
- **WatermelonDB:** Es una librería diseñada para RN (y web) que provee un *ORM reactivo* sobre SQLite. Sus fortalezas:
  - **Rendimiento y escala en RN:** WatermelonDB está optimizada en C++/JNI para realizar las consultas pesadas en hilos nativos, evitando bloquear el hilo de JS. Puede manejar decenas de miles de registros localmente sin degradar la experiencia ([Create an Offline-first React Native App Using WatermelonDB — SitePoint](https://www.sitepoint.com/create-an-offline-first-react-native-app-using-watermelondb/#:~:text=WatermelonDB%20is%20a%20high,data%20needs%20to%20be%20stored)) ([Create an Offline-first React Native App Using WatermelonDB — SitePoint](https://www.sitepoint.com/create-an-offline-first-react-native-app-using-watermelondb/#:~:text=match%20at%20L1647%20several%20advantages,first%20applications%20and%20data)). De hecho, está pensada para **apps complejas con mucha data** sin ralentizar.
  - **Reactividad:** Permite suscribirse a los datos; por ejemplo, si una consulta cambia, las UI componentes se actualizan automáticamente (similar a Convex pero local). Usa `withObservables` para vincular componentes a queries ([Create an Offline-first React Native App Using WatermelonDB — SitePoint](https://www.sitepoint.com/create-an-offline-first-react-native-app-using-watermelondb/#:~:text=import%20styles%20from%20)) ([Create an Offline-first React Native App Using WatermelonDB — SitePoint](https://www.sitepoint.com/create-an-offline-first-react-native-app-using-watermelondb/#:~:text=%2F%2F%20We%20observe%20and%20render,%7B%20review.deleteReview%28%29%3B)).
  - **Sincronización integrada (parcialmente):** WatermelonDB ofrece una estrategia de sync *pull/push* mediante funciones `synchronize()` donde uno provee cómo obtener del servidor los cambios desde la última vez y cómo enviarle los nuevos cambios locales ([Create an Offline-first React Native App Using WatermelonDB — SitePoint](https://www.sitepoint.com/create-an-offline-first-react-native-app-using-watermelondb/#:~:text=How%20does%20WatermelonDB%20handle%20data,synchronization)). No trae servidor, pero **facilita** la implementación: define un protocolo (e.g., proveer una API REST o GraphQL en backend que dado un timestamp devuelva registros nuevos/actualizados, y otro endpoint para recibir lotes de cambios desde el cliente). El dev tiene que implementar el lado servidor, pero Watermelon ayuda con la gestión local de marcas de tiempo, etc. Indican que maneja conflictos e interrupciones de forma elegante durante la sync (probablemente última escritura gana o similar, a configurar) ([Create an Offline-first React Native App Using WatermelonDB — SitePoint](https://www.sitepoint.com/create-an-offline-first-react-native-app-using-watermelondb/#:~:text=How%20does%20WatermelonDB%20handle%20data,synchronization)).
  - **Soporte de datos relacionados:** Al ser SQL debajo, admite relaciones definidas (foreign keys lógicas en el esquema JS). Watermelon no soporta aún *joins* arbitrarios vía SQL directo, pero puedes definir colecciones relacionadas y cargar asociadas (p. ej. `post.comments` te trae comentarios relacionados).
  - **Uso con Expo:** WatermelonDB puede usarse en Expo, pero **requiere configuración nativa** (instalar el módulo `react-native-sqlite-storage` o `watermelondb/adapters/sqlite`). En un proyecto Expo managed, esto implica usar **config plugins** o prebuild, lo cual es posible. Alternativamente, Watermelon tiene un adaptador LokiJS (en memoria) para desarrollo web, pero en móviles es menos eficiente. Probablemente habría que incluir la dependencia nativa SQLite para producción. Es factible pero aumenta complejidad de build.
  - **Limitaciones:** Watermelon no soporta consultas SQL arbitrarias directas (tiene su API de query estilo ORM). Tampoco tiene, por sí sola, un sistema de autorización multiusuario (es local, cualquier logic multiuser es externa). Y migrar esquemas requiere algunas atenciones (tiene sistema de versiones pero limitado, agregar columnas es soportado pero no eliminar). Según documentación, **transacciones complejas** no están expuestas directamente, aunque internamente agrupa operaciones.

- **RxDB:** Es otra librería JS para base de datos reactiva. Sus características:
  - **Multiplataforma real:** RxDB funciona en navegador, Node, Electron, React Native, etc. Usa distintos **adapters** de almacenamiento: puede ser IndexedDB, LocalStorage, SQLite, etc. En RN suele utilizar SQLite (vía pouchdb-adapter-rn or Watermelon’s adapter) o puede usar su propio storage.
  - **Modelo orientado a documentos**: A diferencia de Watermelon (más SQL/ORM), RxDB se originó como un *superset* de PouchDB, trabajando con colecciones de documentos JSON y permitiendo consultas tipo Mango (similar a queries de Mongo). Pero también soporta esquemas tipados y RxJS para reactividad.
  - **Sync potente con CouchDB/GraphQL:** RxDB destaca por ofrecer **replicación en tiempo real** con CouchDB u otros endpoints. Es decir, si se utiliza un backend CouchDB (o compatible, ej. Cloudant), la sincronización bidireccional es *casi automática* – RxDB/PouchDB se encargan de replicar los documentos, manejar revisionado y conflictos (usando algoritmo *last write wins* con detección de conflictos vía _rev). Alternativamente, RxDB tiene plugins para replicar con GraphQL queries, lo que permite conectarlo a un backend custom GraphQL con resoluciones de conflictos definibles. Esto es más flexible que la aproximación de Watermelon de *pull/push manual*, aunque conceptualmente similar.
  - **Uso en Expo:** RxDB en Expo es posible. Sin embargo, PouchDB (en que se basa) no fue pensado para RN y puede tener issues de rendimiento con muchos datos (de hecho PouchDB guarda históricamente todas revisiones, lo cual inflaba almacenamiento ([React Native Database - Sync & Store Like a Pro | RxDB - JavaScript Database](https://rxdb.info/react-native-database.html#:~:text=PouchDB%20is%20a%20JavaScript%20NoSQL,only%20real%20reason%20to%20use))). RxDB ha tratado de solventar algunos problemas de Pouch, pero hay que configurarlo bien (por ejemplo, usando **react-native-quick-sqlite** como storage para que sea rápido). Es más complejo de afinar que Watermelon, quizás.
  - **Reactividad RxJS:** Los datos se manejan con observables RxJS, permitiendo componer stream de cambios. Esto es poderoso pero agrega otra abstracción (no todo dev RN conoce RxJS).
  - **Limitaciones:** Si se usa sin CouchDB, tocaría implementar backend GraphQL o similar. Y si se usa CouchDB/Pouch, hay que aceptar su modelo eventual con *conflictos por _rev*. Esto funciona bien pero no es relacional (los datos se representan como documentos JSON).
  - **Community:** Watermelon es específico RN (creado por Nozbe) con comunidad RN. RxDB es más amplia (JS en general). Ambos tienen buen mantenimiento, aunque Watermelon es más opinado para RN.

**Otras similares:** 
- **Realm** (de MongoDB): Base de datos local orientada a objetos, con sincronización opcional a la nube Mongo Realm. Es muy eficiente local (C++ engine), soporta datos relacionados y consultas. La sincronización de Realm es automática a su backend (resuelve conflictos mediante último escritor u otras estrategias configurables). Sin embargo, usar Realm Sync requiere cuenta MongoDB Realm (hay costo según uso, gratuito limitado). En Expo, Realm puede usarse con config plugin (es nativo). Es excelente técnicamente, pero la versión Sync es privativa.
- **PouchDB + CouchDB:** Ya mencionado implícitamente vía RxDB. PouchDB en RN no va tan fino a gran escala (problemas de performance conocidos), pero es una solución probada en web offline (e.g. aplicaciones Apache CouchDB used en field).
- **WatermelonDB + cualquier backend:** Podríamos implementar, por ejemplo, un backend con SQLite + HTTP (similar a lo que Watermelon sugiere en su guía con AdonisJS ([Using WatermelonDB for offline data sync - LogRocket Blog](https://blog.logrocket.com/watermelondb-offline-data-sync/#:~:text=Using%20WatermelonDB%20for%20offline%20data,side%20API%20application)) o Supabase). Incluso se puede sincronizar Watermelon directamente con Supabase Postgres a través de una función Cloud (ver tutorial en Supabase blog ([Offline-first React Native Apps with Expo, WatermelonDB, and ...](https://supabase.com/blog/react-native-offline-first-watermelon-db#:~:text=Offline,syncs%20to%20a%20Supabase%20backend))).
- **AWS Amplify DataStore:** Amplify de AWS ofrece DataStore, que debajo usa SQLite (o AsyncStorage) para almacenar datos localmente definidos por un schema GraphQL, y los sincroniza automáticamente con una API AppSync GraphQL en la nube. Soporta conflicto resolvers (por defecto último write win con timestamp, o personalizado en AppSync). Es conceptualmente similar a Realm or Firebase but with GraphQL. Ventaja: integración con AWS (Cognito, S3, etc.). Inconveniente: SDK relativamente pesado y lock-in AWS. En Expo también requeriría configuración.
- **PocketBase:** Es un backend open source escrito en Go que integra **una base de datos SQLite, autenticación y almacenamiento de archivos** en un solo paquete ejecutable. Uno puede desplegarlo en un servidor o local. PocketBase ofrece una API REST y Realtime (suscripción a cambios) incorporada. ¿Cómo encaja en local-first? Dos posibles formas:
  - Ejecutar PocketBase en un servidor y usar su offline client caching: Actualmente PocketBase no tiene SDK offline para RN, pero se podría cachear manualmente. 
  - Ejecutar PocketBase *localmente en el dispositivo*: dado que es un binario Go/wasm, en móvil no es trivial correrlo de forma continua (no hay Go runtime en iOS). Pero en una app Windows o desktop, se podría empotrar PocketBase local. 
  - Lo que se suele hacer es usar PocketBase online pero dado que su DB es SQLite, es fácil de replicar o hacer backups del archivo. 
  - De todos modos, PocketBase brilla por su simplicidad de instalación y funcionalidad out-of-the-box (auth + DB + files). Podría ser una alternativa a Supabase self-host sin la complejidad de Postgres.
  - Limitación: no tiene “auto-merge” de datos offline; uno tendría que conciliar conflictos manualmente si dos dispositivos editan offline los mismos registros.

- **Appwrite:** Backend open source estilo Firebase (con DB, auth, storage). Actualmente su DB es MariaDB + Lucene (para buscar). No tiene soporte offline en sus SDKs; como vimos en búsquedas, implementar offline con Appwrite es manual ([Offline Support · appwrite appwrite · Discussion #5326 - GitHub](https://github.com/appwrite/appwrite/discussions/5326#:~:text=Building%20offline%20first%20capabilities%20with,Yes%20it%20requires%20more)). Aún así, se puede usar Appwrite como server y un SQLite local en cliente, sincronizando a mano.
- **Firebase/Firestore:** Ya hablamos de Auth, pero en datos: **Cloud Firestore** de Firebase merece mención. Firestore **sí soporta offline** en sus SDK nativos: almacena una caché local de los datos consultados y de las escrituras realizadas. De hecho, puedes escribir en Firestore offline y la escritura se enviará al servidor cuando vuelva la conexión, y mientras tanto la lectura local la vería aplicada. Esto hace a Firestore una solución *offline-capable*. Sin embargo, algunas salvedades:
  - Firestore en web (JS SDK) también tiene persistencia offline (usa IndexedDB).
  - En React Native (via JS SDK) debería usar IndexedDB vía expo-sqlite perhaps, pero históricamente el soporte offline en RN con Firebase JS era problemático. Hoy en día es posible que funcione, habría que probar.
  - Firestore está limitado en consultas (no soporta JOINS, consultas solo sobre un índice compuesto, etc.), y es de tipo NoSQL documento. Para datos muy tabulares con relaciones, puede requerir duplicar datos (denormalización) o usar subcolecciones.
  - A su favor, maneja muy bien la sincronización multiusuario en tiempo real (sus *snapshots* en cliente se actualizan al instante).
  - En contra, no tiene un mecanismo robusto de merges de conflictos más allá de *last write wins* en nivel de documento. En apps multi offline editors, los cambios simultáneos en el mismo doc se sobreescriben por el último en sincronizar, a menos que uno use campos de tipo *merge* (como Merge de Map) o semejantes.
  - Para archivos, Firebase Storage complementa (también con reintento de subidas).
  - Firestore escalabilidad: muy buena en servidor (Google infra), pero localmente si la colección es enorme podría ser lento cargar todo (aunque solo se carga lo consultado).

- **Supabase (Postgres) offline:** Supabase como tal no tiene caching offline en sus libs. Pero se puede usar un enfoque: usar **replicación lógica** de Postgres hacia clientes. De hecho, hay herramientas emergentes como **ElectricSQL** (antes *Electric*), que replican una base de datos SQLite en cliente con Postgres en servidor usando WAL logs. No estaba mencionado, pero es interesante: Electric SQL proporciona un conjunto para RN/web que sincroniza un SQLite local con la base de datos Postgres remota usando CRDTs y conflict-free replication. Esto es exactamente para offline-first sin desarrollar todo uno mismo. Aún es relativamente nuevo.
  - Sin ir a Electric, Supabase sí expone un feed de cambios (via *realtime* over websockets, que escucha las WAL de Postgres). Uno podría conectar y aplicar esos cambios localmente. Pero no es trivial, y para bidireccional habría que tener algo en server aplicando cambios de cliente. 
  - Es “posible” pero no soportado oficialmente. 

Dados los muchos caminos, enfoquémonos en los mencionados concretamente y evaluémoslos:

**Comparativa soluciones de backend/sync:**

| Solución / Enfoque                      | Facilidad de desarrollo                   | Rendimiento y escalabilidad                   | Multiplataforma & Offline             | Limitaciones importantes                    |
|-----------------------------------------|-------------------------------------------|-----------------------------------------------|---------------------------------------|----------------------------------------------|
| **Cloudflare Durable Objects** + custom | **Baja.** Requiere programar el backend de sincronización desde cero (JS en Workers). Gran libertad pero demanda esfuerzo experto. | **Alta performance** en coordinación (estado en memoria, latencia muy baja en edge) ([Zero-latency SQLite storage in every Durable Object](https://blog.cloudflare.com/sqlite-in-durable-objects/#:~:text=Durable%20Objects%20,nevertheless%20being%20durable%20and%20consistent)). Escala creando muchos DO (shards). Bien para <= miles de objetos simultáneos cada uno con tráfico moderado; no tanto para big data centralizado. | Back-end desplegado global, clientes pueden ser cualquiera con HTTP/WS. **Offline:** no provee SDK cliente offline; se maneja enviando diffs al reconectar. | Implementación compleja de lógica de merge/conflictos. Almacenamiento por DO limitado (típicamente <100MB por DO). No hay app server tradicional (difícil integraciones SQL externas, aunque con SQLite en DO mejora). |
| **Convex** (BaaS de sync en tiempo real) | **Alta.** Proporciona SDK sencillo, definiciones de funciones en TS, y se encarga de la sync y reactividad ([Stateful Sync Platform](https://www.convex.dev/sync#:~:text=Everything%2C%20always%20in%20sync)) ([Stateful Sync Platform](https://www.convex.dev/sync#:~:text=Realtime%2C%20all%20the%20time)). Mucho menos código de sincronización manual. | **Muy buena para tiempo real.** Base de datos optimizada para notificar cambios a clientes. Transaccional y consistente. Escala verticalmente (en su cloud) según uso. Para muchos documentos funciona, pero consultas muy pesadas quizá no tan rápidas como SQL especializado. | SDK JS funciona en web, RN Expo (vía WS). **Offline:** admite encolar operaciones sin conexión y sincronizarlas luego ([Stateful Sync Platform](https://www.convex.dev/sync#:~:text=Convex%20is%20a%20stateful%20sync,network%20blips%20are%20handled%20gracefully)). Sin embargo, no almacena automáticamente *todos* los datos localmente, solo los consultados (cache en memoria). | *Lock-in* en plataforma cerrada. No es SQL; modelar datos relacionales complejos puede ser menos directo. Tamaño de datos por app limitado por sus planes (no diseñado para TB de datos por cliente). Dependencia de conexión para datos no cacheados. |
| **SQLite local + WatermelonDB**         | **Media.** Lado cliente: requiere integrar lib nativa en Expo (config plugin) y definir esquemas/modelos y quizá UI reactivas. Lado servidor: implementar endpoints de sync (pull/push) según guía Watermelon ([Create an Offline-first React Native App Using WatermelonDB — SitePoint](https://www.sitepoint.com/create-an-offline-first-react-native-app-using-watermelondb/#:~:text=How%20does%20WatermelonDB%20handle%20data,synchronization)). | **Excelente local:** SQLite maneja miles de registros sin problema en móvil, consultas rápidas con índices ([Create an Offline-first React Native App Using WatermelonDB — SitePoint](https://www.sitepoint.com/create-an-offline-first-react-native-app-using-watermelondb/#:~:text=WatermelonDB%20is%20designed%20specifically%20for,synchronization%20out%20of%20the%20box)). **Escala server:** depende de cómo implementes backend; puede ser un servidor SQL central que agregue cambios. Soporta grandes datasets locales si el dispositivo tiene espacio. | **Android/iOS/Web**: Web puede usar IndexedDB/Loki fallback. En Windows, SQLite debería funcionar (RNW tiene módulos SQLite). **Offline:** Totalmente funcional; todos los datos están locales. Sync incremental manual al reconectar. | Debes resolver conflictos de merge (Watermelon espera que servidor devuelva datos canonicos; último gana por defecto). Sin backend predefinido: más trabajo coordinar multiusuario. Consultas SQL complejas no expuestas directamente (ORM limitado). Carece de push notifs nativas server→cliente (habría que pedir sync periódicamente o con websockets externos). |
| **SQLite local + RxDB**                 | **Media.** Cliente: integrar RxDB y adaptador (posible config) + definir esquemas JSON. Facilita mucho si se usa con CouchDB (poco código sync). | **Muy buena local:** similar a Watermelon, desempeño depende de SQLite adapter (quick-sqlite). **Escala server:** usando CouchDB, este escala decentemente en concurrentes pero no para datos fuertemente relacionales. Con GraphQL custom, escalabilidad depende de tu endpoint. | **Android/iOS/Web/Node:** Altamente portable. **Offline:** completo, toda data local y replicación bidireccional cuando hay conexión (si con Couch/Pouch). Maneja históricos de cambios con revs (puede ocupar espacio extra). | Modelo NoSQL documento: datos muy relacionales pueden ser incómodos. PouchDB (núcleo) tiene issues de rendimiento a gran escala (limpiar históricos complicado ([React Native Database - Sync & Store Like a Pro | RxDB - JavaScript Database](https://rxdb.info/react-native-database.html#:~:text=CouchDB%20couchdb,only%20real%20reason%20to%20use))). Requiere resolución de conflictos a nivel documento (CouchDB marca conflictos pero no los fusiona automáticamente). Integrar con Postgres requiere GraphQL u otro; más complejo que usar su flujo con CouchDB. |
| **Firebase Firestore**                 | **Alta (cliente).** Muy fácil de usar en cliente (SDK); offline caching automático en nativo, en Expo funcional con limitaciones. Servidor ya gestionado por Google (sin code). | **Buena escalabilidad en server:** Firestore maneja grandes cargas. **Performance local:** consultas indexadas rápidas para rangos; pero no es SQL, consultas limitadas. Realtime updates instantáneos. | **Android/iOS/Web:** SDKs nativos con offline. En RN/Expo usando SDK web: offline persistencia puede requerir hacks. **Offline:** permite leer/escribir cache local offline y sincroniza en red ([Offline-First Durable Objects / KV - Workers - Cloudflare Community](https://community.cloudflare.com/t/offline-first-durable-objects-kv/230015#:~:text=Community%20community,and%20syncing%20them%20upon%20reconnections)). | No soporta joins ni lógica de servidor custom (solo Cloud Functions separadas). Conflictos: último writer gana; no hay merges a nivel de campo salvo usando tipos especiales. Coste escalable según uso (pero generoso inicio). |
| **Supabase (Postgres) + custom sync**   | **Baja-Media.** Cliente fácil (Supabase JS SDK) pero no tiene offline; habría que implementar cache local (por ej. usar SQLite y replicar). Servidor: es Postgres, poderoso pero sin mecanismo offline nativo (usar WAL, triggers, etc.). | **Excelente servidor:** Postgres robusto para datos relacionales masivos. **Performance local:** usando un local DB como SQLite para offline podría ser bueno. Realtime via Supabase (WS) para notificar cambios. | **Android/iOS/Web:** SDK online funciona multiplataforma. **Offline:** no nativo. Posible lograrlo con herramientas adicionales (replicación lógica Postgres→SQLite usando algo como ElectricSQL, etc.). | Sin soporte offline nativo, es la mayor pega. Construir replicación robusta requiere mucho trabajo o herramientas de terceros emergentes. |
| **PocketBase** (backend SQLite + API)   | **Alta (server).** Desplegar PocketBase es trivial (un binario). Cliente: consumido via REST/Realtime API; SDK JS disponible. Necesita implementar caching si offline. | **Server single-instance:** usa SQLite, soporta buen volumen pero escalar más allá de un servidor requiere sharding manual. Realtime via WebSocket para notificar cambios a clientes. | **Android/iOS/Web:** via REST calls (can use anywhere). **Offline:** no incorporado; se puede cachear manual en SQLite local y comparar timestamps. | Al ser single-file DB, concurrentes altos limitados (aunque buena para apps medianas). Sin merge offline automático – la lógica recae en dev si dos ediciones confligen. |

*(Otras soluciones open-source como **Appwrite** o **Realm** no incluidas por brevedad, pero se ubicarían en estrategia similar: Appwrite similar a Supabase (requiere custom offline), Realm similar a Watermelon/RxDB con Sync integrado propio pero de pago).*

**Análisis de idoneidad para el caso de uso:** Dada la naturaleza de la aplicación (muchos datos tabulares relacionados, necesidad de offline completo, y sincronización rápida incluyendo archivos multimedia):

- Una **base de datos local robusta es casi obligatoria** para rendimiento offline. SQLite es la opción lógica porque manejará datos relacionales con índices eficientemente en el dispositivo. Usarla vía WatermelonDB proporciona un marco sólido para trabajar con grandes colecciones en RN ([Create an Offline-first React Native App Using WatermelonDB — SitePoint](https://www.sitepoint.com/create-an-offline-first-react-native-app-using-watermelondb/#:~:text=WatermelonDB%20is%20designed%20specifically%20for,synchronization%20out%20of%20the%20box)). Así, creemos que la app debería tener un **almacenamiento local central (SQLite)** donde residen todos los datos editables.

- Sobre la **sincronización**, si se busca minimizar esfuerzo de implementación, una solución como **Convex** puede encargarse de la mayor parte del problema de enviar/recibir cambios en tiempo real. Sin embargo, Convex no almacena todos los datos localmente por sí solo, así que podría usarse en combinación: por ejemplo, usar SQLite local y cuando la app esté online, aplicar las mutaciones a Convex (que las replicará a otros clientes) – funcionaría, pero no es un patrón típico que ellos vendan (Convex espera controlar su propia DB, no sincronizar con una local externa).

- Alternativamente, un **patrón WatermelonDB + servidor Postgres** podría ser apropiado: El dispositivo guarda en SQLite y manda cambios al servidor (que puede ser Postgres supabase o incluso Cloudflare DO con SQLite) y jala actualizaciones. Esto cumple local-first total pero exige implementar la API. Aquí es donde herramientas como **Cloudflare DO** brillan si se tiene capacidad de implementarlas – usando DO + SQLite en el backend para recibir esos cambios, podríamos hacer replicación a nivel SQL (incluso aprovechar que SQLite a SQLite sería más sencillo en formato). Con la reciente introducción de SQLite en DO, se podría imaginar hasta sincronizar ficheros WAL entre cliente y DO aunque eso no esté dado, habría que customizar.

- **Firebase Firestore** por sí solo podría quedarse corto debido a las relaciones complejas: modelar datos muy relacionales en Firestore (NoSQL) complica consultas y duplicaría datos. Además, los archivos multimedia grandes tendrían que subirse a Firebase Storage, lo cual es viable pero hay que gestionar las URLs, etc. Firestore es genial para datos más sencillos y realtime, pero para datos tabulares (ej. varias tablas con foreign keys) un SQL local/central es mejor. Sin embargo, Firestore podría complementar si no se quisiera montar un servidor personalizado: se podría usar Firestore como canal de sync con su offline caching, pero se correría en los problemas de modelo.

- **Supabase/Postgres** es tentador por el poder de SQL para las relaciones. Sin offline nativo, requiere un esfuerzo en replicación, pero existen abordajes: uno, más manual, es escribir endpoints tipo "damelos cambios desde X logseq" (similar a Watermelon approach). Otra más novedosa es utilizar la replicación lógica de Postgres: Supabase en sus internos ya la usa para el feed realtime. Herramientas como ElectricSQL están tratando de simplificar eso para devs RN, sincronizando Postgres con SQLite local usando CRDT. Si esta app tiene recursos, apostar por un stack Postgres + Electric (o replichaje similar) podría dar lo mejor: SQL fuerte en ambos lados y offline transparente. Es tecnología de punta y no trivial, pero en 2025 está avanzando.

- **PocketBase** y similares podrían ser una solución pragmática para prototipo: desplegar un PocketBase para tener rápidamente auth+db+files, y luego usar su API; offline tocaria cache manual en SQLite, pero ya se tiene un backend unificado sencillo. A escalas muy grandes quizás no sea suficiente, pero para una app mediana podría funcionar.

**Recomendación backend/sync:**  Para asegurar un funcionamiento *local-first* robusto con datos complejos, sugerimos:
  - Usar **SQLite en el cliente** (posiblemente a través de WatermelonDB, Realm u otro ORM eficiente) como base local primaria. Esto garantiza rendimiento local óptimo y soporte de datos relacionales. 
  - Implementar un mecanismo de **sincronización incremental**. Si el equipo tiene experiencia en backend, una combinación de **Cloudflare DO + SQLite** en el servidor sería potente: se puede implementar una API de sync optimizada, con DO consolidando cambios de múltiples clientes de manera consistente y rápida en la nube (y aprovechar Worker KV o R2 para los archivos). Esto requerirá mayor desarrollo inicial pero daría control total sobre cómo se manejan conflictos (por ejemplo, podríamos implementar lógica de merge específica para datos vectoriales – quizás un CRDT para dibujos – en el DO).
  - Si se desea acelerar el desarrollo reduciendo la construcción de backend custom, entonces optar por **Convex** es razonable para la capa de sincronización de datos tradicionales (tablas, textos, etc.), complementado con un almacenamiento local persistente. Convex podría notificar cambios en tiempo real y encolar acciones offline, simplificando la lógica cliente. Luego, para archivos multimedia, usar un almacenamiento como S3 o Supabase Storage y guardar referencias. Convex recientemente anunció integración con vectores y files, así que quizás podría manejarlo internamente también ([Convex vs. Supabase](https://www.convex.dev/compare/supabase#:~:text=,and%20a%20native%20vector%20database)).
  - Otras combinaciones posibles son **WatermelonDB + Supabase** (usando un pequeño servidor Node/Edge Function para diffs) o **RxDB + CouchDB** si se prefiere aprovechar la replicación ya existente (en ese caso, diseñar los datos como documentos JSON en lugar de tablas normales).
  - Para las **escrituras vectoriales** (trazos de lápiz): suelen representarse como series de puntos o comandos (ej. formato JSON de puntos, o incluso como un pequeño archivo SVG/Ink). Este tipo de dato podría guardarse en una tabla local (por ejemplo, cada trazo como un registro con lista de puntos) o quizá como blob. Manejar diffs de dibujos es complicado, posiblemente se podría simplificar guardando cada versión nueva como un objeto separado (no CRDT sino versionado linear). Si fuera crítico colaborar en tiempo real en el mismo dibujo, entonces técnicas CRDT (ej. Automerge, Y.js) podrían entrar en juego. Un DO con CRDT o Convex con CRDT podrían manejarlo. Estas son consideraciones avanzadas.

En conclusión, **no existe una solución única que, sin desarrollo, cumpla perfectamente todo** (local-first, relaciones, multimedia, etc.), pero sí hay caminos. Un stack viable podría ser: **WatermelonDB (SQLite) en Expo + un backend ligero (PocketBase o Supabase) + quizá WebSockets** para notificar cambios. Esto daría local-first y sincronización razonable. Para máxima consistencia, ir a **Cloudflare DO/Workers** con lógica a medida ofrece una solución elegante, especialmente ahora con SQLite en edge (evitando tener que mantener un servidor central tradicional) ([Zero-latency SQLite storage in every Durable Object](https://blog.cloudflare.com/sqlite-in-durable-objects/#:~:text=Durable%20Objects%20,nevertheless%20being%20durable%20and%20consistent)). 

---

## 4. Tipos de bases de datos recomendados (relacional, documental, vectorial, híbrida)

Dada la naturaleza de los datos de la aplicación, conviene analizar qué **tipo de base de datos** es más apropiado, ya sea para el almacenamiento local, en la nube, o ambos. Podríamos considerar cuatro categorías: **relacional (SQL)**, **documental (NoSQL orientado a documentos JSON)**, **vectorial** y **enfoques híbridos o multi-modelo**. A continuación, se describen cada tipo con sus pros, contras y aplicabilidad al caso:

- **Base de datos relacional (SQL):** Organiza los datos en tablas con filas y columnas, permitiendo definir relaciones (FKs) y realizar consultas SQL complejas (JOINs, agregaciones).
  - *Ventajas:* Excelentes para **datos altamente estructurados y relacionados** – por ejemplo, si tenemos entidades como Usuarios, Proyectos, Tareas, cada una en tablas vinculadas, un SQL puede fácilmente traer, digamos, “todas las Tareas de los Proyectos del Usuario X que estén incompletas” en una sola consulta. Garantizan **consistencia ACID**; las transacciones aseguran integridad referencial (importante al manejar muchas relaciones). SQL es un lenguaje universalmente conocido y optimizado por décadas, con capacidad de **agregar índices** para acelerar búsquedas en grandes volúmenes. Para datos tabulares masivos, un buen motor SQL (SQLite local, Postgres en servidor) manejará cientos de miles de registros con eficiencia. 
  - *Desventajas:* Las bases SQL tradicionales no estaban diseñadas para sincronización multi-maestro offline; manejan concurrencia en un servidor central, pero sincronizar dos bases SQL (ej. SQLite cliente y Postgres servidor) es complejo sin herramientas especiales. También, requieren **esquemas predefinidos**; si los datos son muy heterogéneos o cambian de estructura con frecuencia, puede ser restrictivo (aunque se pueden hacer migraciones). Otra contra es la **curva de complejidad**: hay que diseñar bien el modelo normalizado y escribir consultas, lo que es más laborioso que guardar JSON directamente. En dispositivos móviles, SQLite es muy capaz pero hay ciertas limitaciones (tamaño de DB manejable en móviles – aunque se habla de decenas de GB en teoría, no es ideal tener tantísimo en un teléfono).
  - *En este caso:* Probablemente **necesario para la parte estructurada** (tablas, relaciones). La app tiene “grandes cantidades de datos tabulares y relaciones”, lo que encaja perfectamente con relacional. También los textos largos se pueden almacenar como TEXT en SQL, con opción de hacer búsquedas full-text (SQLite tiene FTS5 por ejemplo). Para sincronizar offline, se puede utilizar la base relacional local y luego emplear estrategias de replicación (CRDTs o logs) o servicios como los mencionados (Electric, etc.) para resolver el multi-maestro. Pero como almacenamiento central de verdad, un Postgres (relacional) podría ser la fuente principal de verdad en el servidor.

- **Base de datos orientada a documentos (NoSQL documental):** Almacenan datos semiestructurados normalmente en formato JSON, agrupados en colecciones. No imponen un esquema rígido por adelantado.
  - *Ventajas:* **Flexibilidad de esquema** – se pueden tener objetos con distintos campos sin migraciones formales, útil si los datos varían. Son naturales para almacenar datos anidados: por ejemplo, un objeto Usuario que contenga un array de direcciones y otro de teléfonos en un solo documento JSON. Esto evita la necesidad de múltiples tablas y JOINS para datos que conceptualmente son un único objeto. Tienden a escalar fácilmente de forma distribuida (ej: CouchDB, MongoDB) y algunas están pensadas para replicación offline (CouchDB fue pionera en replicación P2P y offline, PouchDB en cliente). Para **datos de tipo libre** (como quizás las notas de texto largas, o configuraciones) es cómodo.
  - *Desventajas:* Consultas complejas o **unir datos de distintas colecciones es engorroso**, ya que no hay JOINS nativos (se harían en la lógica de la app). Se suele duplicar datos (denormalización) para optimizar lecturas, lo que puede llevar a inconsistencias si no se maneja bien. Las transacciones si existen son limitadas (Mongo por ejemplo tiene transacciones multi-documento solo en clusters replicados, CouchDB no tiene transacciones multi-documento), esto puede dificultar mantener integridad entre piezas de datos relacionadas. En nuestro caso, con datos muy relacionales, un NoSQL puro sería más complicado para asegurar consistencia.
  - *Caso actual:* Podría ser útil para **almacenar los objetos más libres**, por ejemplo, un documento JSON para cada *dibujo vectorial* que contenga todos los trazos y propiedades. O para almacenar configuraciones del usuario, historial, etc., donde la rigidez SQL no aporta mucho. También, si se quisiera implementar un sistema de sync vía CouchDB/PouchDB, se tendría que modelar todo como documentos JSON con un campo _rev. Pero dado que hay muchas relaciones tabulares, un modelo puramente documental no parece ideal como fuente principal. Podría complementarse: por ejemplo, usar una base documental local para ciertos datos offline (como RxDB replicando con CouchDB) mientras otros datos más estructurados usan SQLite. Esto es complejo, por eso existen bases híbridas.

- **Base de datos vectorial:** Es un tipo de base de datos especializado emergente, optimizado para almacenar **vectores de alta dimensión** y realizar búsquedas por similitud (distancia vectorial). No se refiere a vectores gráficos, sino a vectores matemáticos (como embeddings de IA, características de imagen).
  - *Ventajas:* Permite **búsquedas rápidas de similitud** – por ejemplo, buscar documentos cuyo embedding de texto sea más cercano a cierto vector (usado en búsqueda semántica), o imágenes similares a una dada (embedding visual). Si la app tuviera características de inteligencia artificial, como buscar entre los textos largos contenido relevante mediante embeddings, una vector DB (tipo Pinecone, Weaviate, etc., o la integrada en Convex ([Convex vs. Supabase](https://www.convex.dev/compare/supabase#:~:text=,and%20a%20native%20vector%20database))) sería útil. 
  - *Desventajas:* Es un nicho muy específico. No reemplaza a una DB relacional o documental en general, pues solo almacena los vectores y normalmente un identificador. Usualmente se complementa a otra DB (por ej., almacenamos vectores de cada documento en Milvus, pero los documentos en sí en Postgres). Además, no es necesario a menos que implementemos funciones de búsqueda semántica o de contenido similar. 
  - *En nuestra app:* A menos que planeemos funciones como “buscar notas similares” o “buscar imágenes por parecido” utilizando AI, probablemente **no necesitemos una base vectorial dedicada**. El término "escritura vectorial" en la pregunta parece referirse a trazos de lápiz (vector graphics), lo cual no tiene que ver con vector DB. Para almacenar los trazos, se podría usar una base documental (un JSON con los puntos) o guardarlos en una tabla relacionada (una tabla points con FK al dibujo). No se requiere un motor de búsqueda vectorial para eso. Si en el futuro se quisiera incorporar, por ejemplo, búsqueda inteligente en los textos largos, se podría considerar añadir un vector store para embeddings de texto, pero inicialmente no es fundamental. En caso de usar Convex, notamos que ellos incluyen “native vector database” en su stack ([Convex vs. Supabase](https://www.convex.dev/compare/supabase#:~:text=,and%20a%20native%20vector%20database)), así que podría ser un plus gratis si se usara esa plataforma.

- **Bases de datos híbridas o multi-modelo:** Son aquellas que combinan varios paradigmas en uno. Por ejemplo:
  - **ArangoDB** combina modelo documental + grafos + key-value en una sola base.
  - **FaunaDB** (y *SurrealDB* emergente) son bases modernas que permiten consultas tipo SQL sobre datos semi-estructurados, un poco mezclando lo relacional y documental.
  - **OrientDB** era otra que combinaba grafos con documentos.
  - **Azure CosmosDB** puede actuar como documental, como clave-valor, etc., según la API.
  - Estas BD buscan dar lo mejor de cada mundo, pero a veces con costo de complejidad y madurez.
  - *Ventajas:* Un sistema multi-modelo podría almacenar, por ejemplo, las relaciones en formato SQL/tabla, y a la vez permitir guardar subdocumentos JSON o hacer consultas de grafos sobre ciertas entidades (por ejemplo, si los “gráficos” se refirieran a grafos tipo redes, un motor de grafos sería indicado).
  - *Desventajas:* No siempre alcanzan la especialización de cada modelo puro. Además, puede ser excesivo para una sola aplicación que quizá no necesita un grafo dedicado.
  - *Caso actual:* Podría no hacer falta algo multi-modelo exótico. Sin embargo, podemos pensar en **enfoque híbrido ad-hoc**: es decir, usar **más de una base** para distintas necesidades. Por ejemplo, usar SQLite para lo relacional principal, y quizás una solución de búsqueda como **ElasticSearch** para texto libre o **Weaviate** para vectores, si se necesitase. Esto es más bien arquitectura *polyglot persistence*. Si los textos largos van a requerir búsqueda full-text avanzada (no solo coincidencia de palabras, sino ranking, stemming, etc.), un motor tipo Elastic o Algolia podría complementarse. O usar SQLite FTS para un término medio.

**Resumen y recomendaciones de tipo de BD:**

En la aplicación propuesta, **la base de datos relacional** parece la piedra angular ideal para la mayoría de la información estructurada. Usar un **motor SQL (SQLite en cliente, Postgres en servidor)** facilitará manejar las relaciones entre datos y consultas complejas sin duplicación. Además, SQLite en el cliente tiene la ventaja de ser ligero y funcionar offline embebido.

Las **bases documentales** pueden ser útiles para contenidos no estructurados (por ejemplo, almacenar en un solo documento JSON todos los datos de configuración de usuario, o los resultados de un gráfico complejo). No obstante, no se ve un requerimiento fuerte de esquema flexible en la descripción, salvo quizás los datos de dibujo vectorial que podrían modelarse como documento. Aun así, se puede manejar eso dentro de una base relacional (guardando JSON en un campo, ya que tanto SQLite como Postgres permiten campos JSON; Postgres incluso permite indexar JSON). Por tanto, podríamos usar un enfoque híbrido **relacional con campos JSON** donde convenga, en vez de una base NoSQL separada.

Las **bases de datos vectoriales** especializadas no son una prioridad inicial a menos que se identifique una funcionalidad de búsqueda por similitud. Si en el futuro se incorpora IA para, digamos, etiquetar fotos o buscar por contenido de audio/video, se consideraría añadir un vector store. Por ahora, el término "vectorial" lo manejaremos en su sentido de *gráficos vectoriales* más que DB vectorial.

Una **aproximación híbrida práctica** sería:
- En el dispositivo: **SQLite** (via Watermelon/Realm) para datos estructurados y algunas columnas JSON para datos semiestructurados. 
- En el servidor: **PostgreSQL** (via Supabase u otro) para persistir permanentemente con estructura relacional, y quizás tablas de apoyo para full-text search (Postgres tiene Full Text nativo que podría usarse para buscar en textos largos).
- Si se requiere colaboración en grafos (no está claro, “gráficos” suena a charts o drawings, no necesariamente grafos tipo redes sociales), pero si hubiera datos tipo grafo (nodos-aristas), una opción sería usar una BD de grafos (Neo4j, etc.) o modelarlo en SQL con tablas de adyacencia. No parece central por ahora.

**Tabla comparativa de tipos de BD:**

| Tipo de base de datos    | Ventajas en este proyecto                                         | Desventajas / Riesgos                                   | Aplicabilidad al caso                       |
|--------------------------|------------------------------------------------------------------|---------------------------------------------------------|---------------------------------------------|
| **Relacional (SQL)**     | - Ideal para datos tabulares con muchas relaciones (integridad referencial).<br>- Consultas complejas (JOIN, agregaciones) resueltas eficientemente ([Create an Offline-first React Native App Using WatermelonDB — SitePoint](https://www.sitepoint.com/create-an-offline-first-react-native-app-using-watermelondb/#:~:text=WatermelonDB%20is%20a%20high,date%20across%20multiple%20devices)).<br>- ACID: seguridad en transacciones (importante para mantener consistencia en tantas entidades).<br>- SQLite local muy rápido para lecturas/escrituras locales; Postgres robusto en server. | - Sin herramientas nativas de sincronización multi-maestro (requiere implementar replicación/conflictos).<br>- Esquema rígido: cambios requieren migraciones (aunque esto se puede manejar con buenas prácticas).<br>- Puede ser exceso de formalidad para datos muy flexibles (p.ej. si algunas entidades varían mucho en estructura). | **Muy alta.** Gran parte de los datos (tablas, relaciones, campos numéricos y de texto) encajan en modelo relacional. La app manejará “grandes cantidades de datos tabulares y relaciones”, justamente fortaleza SQL. Usaremos SQLite en cliente por ser prácticamente la única opción robusta offline de este estilo ([Zero-latency SQLite storage in every Durable Object](https://blog.cloudflare.com/sqlite-in-durable-objects/#:~:text=SQLite%20is%20the%20most,of%20SQLite%20in%20the%20cloud)). |
| **Documental (NoSQL)**   | - Flexibilidad para almacenar datos heterogéneos o anidados sin predefinir esquema (útil para, por ej., guardar un campo "config" JSON para cada gráfico que tenga sub-elementos).<br>- Replicación offline sencilla en algunas implementaciones (CouchDB) – apropiado si se optara por RxDB/Pouch para sync sin diseñar esquema SQL. | - Consultar por relaciones o múltiples criterios es más complejo (sin JOIN, a veces hay que duplicar datos).<br>- Puede dificultar mantener consistencia entre partes relacionadas (p.ej. usuario y sus tareas separados por colecciones, hay que actualizar contadores manualmente, etc.).<br>- En RN, soluciones como PouchDB sufren rendimiento con datos masivos ([React Native Database - Sync & Store Like a Pro | RxDB - JavaScript Database](https://rxdb.info/react-native-database.html#:~:text=CouchDB%20couchdb,only%20real%20reason%20to%20use)). | **Media.** Puede usarse para partes específicas: ej. representar un **dibujo vectorial completo como documento JSON** en lugar de normalizar en múltiples tablas (puntos, líneas). También podría servir para *logs de cambios* o historial, donde cada entrada es un doc. Sin embargo, no la usaríamos para el grueso de datos tabulares (allí preferimos SQL). Podría implementarse almacenando JSON dentro de columnas en SQLite/Postgres cuando convenga, en vez de tener otra DB separada. |
| **Vectorial (similaridad)** | - Permite búsquedas avanzadas (ej. encontrar documentos o multimedia “parecidos” a cierto criterio) en tiempo subsegundo incluso con miles de vectores, gracias a índices especiales (Annoy, HNSW).<br>- Útil para funciones de IA: recomendación de contenido, agrupación semántica automática, etc. | - No es un almacén general de datos, solo de embeddings; requiere flujos de ML para generar esos embeddings.<br>- Añade complejidad y recursos (normalmente es un servicio separado).<br>- No tiene un rol directo en CRUD de datos normales. | **Baja (inicialmente).** No parece haber un requerimiento de “búsqueda por similitud” explícito. Los “gráficos” mencionados son probablemente charts o doodles, no redes vectoriales de datos numéricos. Por tanto, no justificaría introducir una vector DB pura en MVP. A futuro, si se quisiera implementar, por ejemplo, *búsqueda en notas largas por significado*, se podría evaluar añadir vectores (Convex ya lo incorpora en su DB por si se usa ([Convex vs. Supabase](https://www.convex.dev/compare/supabase#:~:text=,and%20a%20native%20vector%20database)), o integrar una librería como FAISS localmente). De momento, **no es prioritario**. |
| **Híbrido / Multi-modelo** | - Un único sistema podría atender múltiples patrones de datos (estructurados, documentos, grafos).<br>- Evita tener que orquestar varias bases distintas, reduciendo complejidad de integración.<br>- Ejemplo: FaunaDB permitiría guardar datos como documentos pero consultarlos con algo parecido a SQL, combinando ventajas. | - Menos maduro/probado en algunos casos. Poca experiencia en la comunidad móvil con estos.<br>- Optimización comprometida: no siempre tan eficiente como una DB especializada en cada área.<br>- Conocimiento menos difundido; más difícil encontrar ayuda. | **Baja.** Probablemente no sea necesario introducir una solución multi-modelo especial. El problema puede resolverse con una combinación de tecnologías conocidas (SQL + quizás almacenamiento de archivos + alguna búsqueda). Meter un ArangoDB o Fauna podría generar complejidad sin un beneficio claro, pues nuestro caso de uso no menciona necesidad de grafos complejos ni similar. Un enfoque **híbrido a nivel arquitectura** (usar varias tecnologías en conjunto) es más tangible: ej. Postgres + ElasticSearch para buscar en texto, o SQLite + Convex combinados, etc. Eso sería preferible a confiar en un solo sistema mágico. |

En conclusión, se recomienda un **modelo principalmente relacional** para estructurar los datos de la aplicación, complementado con elementos NoSQL o de búsqueda cuando resulte conveniente. Esto podría implicar usar **SQLite/SQL** tanto en el cliente (para operar offline sobre datos relacionales) como en el servidor (para almacenamiento persistente), y adicionalmente:
- Usar **archivos en sistema de ficheros** o almacenamiento objeto para los **videos/audios/imágenes**, en lugar de guardar blobs enormes directamente en la base de datos (evitando sobrecargarla). Se guarda solo la ruta o URL en la base.
- Para **textos largos**, aprovechar funcionalidades de búsqueda de texto (SQLite FTS5 en local para encontrar palabras clave rápidamente; en servidor, quizás ElasticSearch o Postgres full-text for search).
- Para **trazos vectoriales** de stylus, escoger una representación: o bien guardarlos en una tabla relacional (ej. cada trazo con campos de coordenadas, ligado a un dibujo), o serializar el dibujo completo en JSON y almacenarlo en un campo (o incluso como fichero SVG). Si la edición colaborativa de dibujos no es tan concurrente, guardar como blob JSON puede ser más sencillo y se sincroniza ese blob cuando cambia.
- Mantener un **balance entre consistencia y rendimiento**: relacional para la consistencia en datos vinculados (asegurando, por ejemplo, que si se borra un Proyecto, también se marcan para borrar sus Tareas), pero quizás no normalizar *demasiado* al punto de dificultar la sync. A veces en offline-first se prefiere incluso duplicar ciertos datos para simplificar merges (ej: instead of a strict normalized schema, include some denormalized info to avoid multi-entity transactions offline). Esto es un detalle de diseño: se podría normalizar en el server pero tener un esquema más redundante localmente para facilitar la resolucion de conflictos. 

En resumen, **SQL + sincronización bien pensada** aparece como la base tecnológica más adecuada para nuestra aplicación, complementada según necesidad con otras herramientas. Las tecnologías evaluadas (Expo Router, Clerk vs Firebase, Durable Objects vs Convex vs DB locales, etc.) se integran en este panorama aportando cada una en su capa: la navegación y auth para la UX multiplataforma, y la estrategia de datos para cumplir la promesa de *local-first* con sync rápida de grandes datos.

**Referencias**:

- Expo Router vs React Navigation ([Expo Router vs React Navigation: A Comprehensive Comparison | Attract Group](https://attractgroup.com/blog/expo-router-vs-react-navigation-a-comprehensive-comparison/#:~:text=,and%20mobile%20without%20extra%20configuration)) ([Introduction to Expo Router - Expo Documentation](https://docs.expo.dev/router/introduction/#:~:text=Expo%20Router%20is%20a%20file,Android%2C%20iOS%2C%20and%20web)) ([Migrate from React Navigation - Expo Documentation](https://docs.expo.dev/router/migrate/from-react-navigation/#:~:text=Pitch))  
- Clerk offline support y características ([Expo: Enable offline support in your Expo app](https://clerk.com/docs/references/expo/offline-support#:~:text=,disruptions%20caused%20by%20network%20failures)) ([Comparing Auth from Supabase, Firebase, Auth.js, Ory, Clerk and others](https://blog.hyperknot.com/p/comparing-auth-providers#:~:text=))  
- WatermelonDB en offline-first (rendimiento, sincronización) ([Create an Offline-first React Native App Using WatermelonDB — SitePoint](https://www.sitepoint.com/create-an-offline-first-react-native-app-using-watermelondb/#:~:text=WatermelonDB%20is%20a%20high,date%20across%20multiple%20devices)) ([Create an Offline-first React Native App Using WatermelonDB — SitePoint](https://www.sitepoint.com/create-an-offline-first-react-native-app-using-watermelondb/#:~:text=How%20does%20WatermelonDB%20handle%20data,synchronization))  
- Cloudflare Durable Objects y SQLite en edge ([Zero-latency SQLite storage in every Durable Object](https://blog.cloudflare.com/sqlite-in-durable-objects/#:~:text=Durable%20Objects%20,nevertheless%20being%20durable%20and%20consistent))  
- Convex: estado sincronizado en tiempo real ([Stateful Sync Platform](https://www.convex.dev/sync#:~:text=Everything%2C%20always%20in%20sync)) ([Stateful Sync Platform](https://www.convex.dev/sync#:~:text=Convex%20is%20a%20stateful%20sync,network%20blips%20are%20handled%20gracefully)).

# Pregunta

La base de datos tanto local como en la nube quiero que guarde archivos de texto como obsidian para que el usuario siempre tenga el control de sus datos. Por lo que podria acceder a los datos y modificarlos por texto plano y a continuacion volver a iniciar su aplicacion y que esos cambios se actualicen a la aplicacion y la base de datos de la nube, cual seria la mejor opcion de base local y en nube para poder hacer esto a mallores de trabajar con imagenes, videos y graficos vectoriales?