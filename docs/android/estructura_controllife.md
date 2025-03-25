# Estructura del Proyecto ControlLife

<!-- Este documento explica la estructura específica del proyecto ControlLife que estamos desarrollando -->

## Estructura Actual ControlLife

Actualmente, el proyecto ControlLife es una aplicación Android básica creada con la plantilla "Basic Activity" de Android Studio. Esta plantilla proporciona una estructura inicial con navegación entre fragmentos.

```
controllife
├── .gradle/                                           # Archivos generados por Gradle para caché y compilación
├── .idea/                                             # Configuración específica del IDE Android Studio
├── .kotlin/                                           # Caché y configuración específica para Kotlin
├── app/                                               # Módulo principal de la aplicación
├── ├── build/                                         # Archivos generados durante la compilación
├── ├── src/                                           # Código fuente y recursos
├── │   ├── androidTest/java/com/doolmo/controllife/   # Pruebas de instrumentación (UI Tests)
├── │   │   └── ExampleInstrumentedTest.kt             # Ejemplo de prueba instrumentada
├── │   ├── main/                                      # Código y recursos principales
├── │   │   ├── java/com/doolmo/controllife/           # Código fuente principal en Kotlin
├── │   │   │   ├── FirstFragment.kt                   # Primer Fragmento de ejemplo
├── │   │   │   ├── MainActivity.kt                    # Actividad principal de la aplicación
├── │   │   │   └── SecondFragment.kt                  # Segundo Fragmento de ejemplo
├── │   │   ├── res/                                   # Recursos de la aplicación
├── │   │   │   ├── drawable                           # Imágenes vectoriales y recursos gráficos
├── │   │   │   │   ├── ic_launcher_background.xml     # Fondo del ícono de lanzamiento
├── │   │   │   │   └── ic_launcher_foreground.xml     # Frente del ícono de lanzamiento
├── │   │   │   ├── layout                             # Archivos XML para diseño de UI
├── │   │   │   │   ├── activity_main.xml              # Diseño de la actividad principal
├── │   │   │   │   ├── content_main.xml               # Contenido principal de la actividad
├── │   │   │   │   ├── fragment_first.xml             # Diseño del primer fragmento
├── │   │   │   │   └── fragment_second.xml            # Diseño del segundo fragmento
├── │   │   │   ├── menu                               # Menús de la aplicación
├── │   │   │   │   └── menu_main.xml                  # Menú principal de la aplicación
├── │   │   │   ├── mipmap-anydpi                      # Íconos adaptativos XML para cualquier resolución
├── │   │   │   │   ├── ic_launcher_round.xml          # Ícono redondo adaptativo
├── │   │   │   │   └── ic_launcher.xml                # Ícono adaptativo normal
├── │   │   │   ├── mipmap-hdpi                        # Íconos de alta resolución
├── │   │   │   │   ├── ic_launcher_round.webp
├── │   │   │   │   └── ic_launcher.webp
├── │   │   │   ├── mipmap-mdpi                        # Íconos de resolución media
├── │   │   │   │   ├── ic_launcher_round.webp
├── │   │   │   │   └── ic_launcher.webp
├── │   │   │   ├── mipmap-xhdpi                       # Íconos de resolución extra-alta
├── │   │   │   │   ├── ic_launcher_round.webp
├── │   │   │   │   └── ic_launcher.webp
├── │   │   │   ├── mipmap-xxhdpi                      # Íconos de resolución doble-extra-alta
├── │   │   │   │   ├── ic_launcher_round.webp
├── │   │   │   │   └── ic_launcher.webp
├── │   │   │   ├── mipmap-xxxhdpi                     # Íconos de resolución triple-extra-alta
├── │   │   │   │   ├── ic_launcher_round.webp
├── │   │   │   │   └── ic_launcher.webp
├── │   │   │   ├── navigation                         # Configuración de navegación entre fragmentos
├── │   │   │   │   └── nav_graph.xml                  # Gráfico de navegación
├── │   │   │   ├── values                             # Valores globales como colores, dimensiones y textos
├── │   │   │   │   ├── colors.xml                     # Definición de colores
├── │   │   │   │   ├── dimens.xml                     # Definición de dimensiones estándar
├── │   │   │   │   ├── strings.xml                    # Textos estáticos traducibles
├── │   │   │   │   └── themes.xml                     # Definición del tema principal
├── │   │   │   ├── values-land                        # Valores específicos para orientación horizontal
├── │   │   │   │   └── dimens.xml
├── │   │   │   ├── values-night                       # Valores específicos para modo oscuro
├── │   │   │   │   └── themes.xml
├── │   │   │   ├── values-v23                         # Valores específicos para API nivel 23 y superior
├── │   │   │   │   └── themes.xml
├── │   │   │   ├── values-w600dp                      # Valores específicos para pantallas medianas (tabletas)
├── │   │   │   │   └── themes.xml
├── │   │   │   ├── values-w1240dp                     # Valores específicos para pantallas grandes (tabletas grandes o escritorios)
├── │   │   │   │   └── themes.xml
├── │   │   │   └── xml                                # Configuración adicional en XML
├── │   │   │       ├── backup_rules.xml               # Reglas para copias de seguridad automáticas
├── │   │   │       └── data_extraction_rules.xml      # Reglas para extracción automática de datos
├── │   │   └── AndroidManifest.xml                    # Configuración global de la aplicación Android
├── │   └── test/java/com/doolmo/controllife/          # Pruebas unitarias
├── │       └── ExampleUnitTest.kt                     # Ejemplo de prueba unitaria
├── ├── .gitignore                                     # Reglas para archivos que Git debe ignorar
├── ├── build.gradle                                   # Configuración específica de compilación del módulo "app"
├── └── proguard-rules.pro                             # Reglas de optimización y ofuscación del código
├── docs/                                              # Documentación del proyecto
├── gradle/                                            # Archivos y scripts relacionados con Gradle
├── ├── wrapper/                                       # Scripts y archivos para ejecutar Gradle
├── │   ├── gradle-wrapper.jar                         # Ejecutable para la envoltura de Gradle
├── │   └── gradle-wrapper.properties                  # Configuración para Gradle Wrapper
├── └── libs.versions.toml                             # Versionado de dependencias de librerías
├── .gitignore                                         # Reglas globales para archivos ignorados por Git
├── build.gradle                                       # Configuración general de compilación del proyecto
├── gradle.properties                                  # Propiedades globales de Gradle
├── gradlew                                            # Script ejecutable para Gradle en sistemas Unix
├── gradlew.bat                                        # Script ejecutable para Gradle en sistemas Windows
├── local.properties                                   # Propiedades locales del entorno de desarrollo
└── settings.gradle                                    # Configuración de los módulos incluidos en el proyecto
```

## Componentes Principales

### MainActivity.kt
Archivo: `app/src/main/java/com/doolmo/controllife/MainActivity.kt`

Es la actividad principal y punto de entrada de la aplicación. Contiene:
- Una toolbar (barra de herramientas superior)
- Un FAB (Floating Action Button) que muestra un mensaje de bienvenida
- Configuración para la navegación entre fragmentos
- Menú de opciones con una entrada de configuración

```kotlin
// Extracto relevante
binding.fab.setOnClickListener { view ->
    Snackbar.make(view, "¡Bienvenido a ControlLife!", Snackbar.LENGTH_LONG)
        .setAction("Action", null)
        .setAnchorView(R.id.fab).show()
}
```

### Fragmentos
- **FirstFragment.kt**: Pantalla inicial con un mensaje de bienvenida y un botón para navegar al segundo fragmento
- **SecondFragment.kt**: Pantalla secundaria con un botón para volver al primer fragmento

### Archivos de Layout (XML)
- **activity_main.xml**: Define la estructura principal de la app
  - Contiene la toolbar y el botón flotante (FAB)
  - Incluye el contenedor para los fragmentos

- **content_main.xml**: Contenido principal donde se muestran los fragmentos

- **fragment_first.xml**: Layout del primer fragmento
  - Contiene un botón y un TextView con el mensaje de bienvenida

- **fragment_second.xml**: Layout del segundo fragmento
  - Similar al primero pero con un mensaje diferente

### Recursos (res)
- **strings.xml**: Contiene todos los textos de la aplicación
  - Título de la aplicación: "ControlLife"
  - Etiquetas de navegación: "Inicio", "Detalles"
  - Textos de botones: "Siguiente", "Anterior"
  - Mensaje de bienvenida:
    ```
    ¡Bienvenido a ControlLife!
    Esta es tu primera aplicación Android. Aquí puedes comenzar a diseñar tu aplicación para gestionar y controlar aspectos de tu vida diaria.
    Explora las diferentes funciones y características disponibles haciendo clic en los botones de navegación.
    ```

- **colors.xml**: Define la paleta de colores básica
- **themes.xml**: Define el tema visual de la aplicación
- **dimens.xml**: Define dimensiones estándar como márgenes

### Navigation
- **nav_graph.xml**: Define la navegación entre FirstFragment y SecondFragment

### Archivos de Configuración
- **AndroidManifest.xml**: Configuración de la aplicación, permisos y actividades
- **build.gradle.kts**: Configuración de dependencias y compilación

## Próximos Pasos

Para desarrollar la aplicación ControlLife, podríamos:

1. **Definir funcionalidades específicas**: Decidir qué aspectos de la vida queremos "controlar"
   - Seguimiento de hábitos
   - Gestión de tareas
   - Control de gastos
   - Monitoreo de salud/ejercicio

2. **Crear nuevos fragmentos y actividades** para cada funcionalidad

3. **Implementar persistencia de datos** (base de datos local con Room)

4. **Mejorar la interfaz de usuario** con componentes más específicos

5. **Implementar notificaciones** para recordatorios

## Cómo Modificar la Aplicación

### Cambiar Textos
Editar `strings.xml` para modificar cualquier texto visible.

### Añadir Nueva Pantalla
1. Crear un nuevo archivo de layout XML en `res/layout`
2. Crear una nueva clase Fragment o Activity
3. Actualizar el gráfico de navegación en `nav_graph.xml`

### Cambiar Estilos y Colores
Modificar `colors.xml` y `themes.xml` para personalizar la apariencia.

### Añadir Funcionalidades
Modificar los archivos Kotlin existentes o crear nuevos según la arquitectura que decidamos seguir. 