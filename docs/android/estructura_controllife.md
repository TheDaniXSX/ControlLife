# Estructura del Proyecto ControlLife

<!-- Este documento explica la estructura específica del proyecto ControlLife que estamos desarrollando -->

## Estructura Actual

Actualmente, el proyecto ControlLife es una aplicación Android básica creada con la plantilla "Basic Activity" de Android Studio. Esta plantilla proporciona una estructura inicial con navegación entre fragmentos.

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