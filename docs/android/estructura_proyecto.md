# Estructura de un Proyecto Android

<!-- Este documento explica la estructura básica de un proyecto Android y la función de cada archivo y carpeta principal -->

## Estructura General

```
app/
├── build/                  # Archivos generados durante la compilación
├── src/
│   ├── main/
│   │   ├── java/           # Código fuente en Java/Kotlin
│   │   ├── res/            # Recursos de la aplicación
│   │   └── AndroidManifest.xml  # Configuración principal de la app
│   ├── androidTest/        # Pruebas de instrumentación
│   └── test/               # Pruebas unitarias
├── build.gradle            # Configuración de compilación del módulo
└── proguard-rules.pro      # Reglas de optimización de código
gradle/                     # Scripts de Gradle
build.gradle                # Configuración de compilación del proyecto
settings.gradle             # Configuración de módulos incluidos
```

## Archivos Principales y sus Funciones

### AndroidManifest.xml
Es el archivo de configuración fundamental para tu aplicación. Define:
- El nombre y ID del paquete de la aplicación
- Los componentes de la aplicación (actividades, servicios, etc.)
- Los permisos necesarios
- Las versiones mínimas de Android soportadas
- El icono y tema visual de la aplicación

### /java
Contiene todo el código fuente organizado en paquetes:
- Activities: Pantallas completas de la aplicación
- Fragments: Porciones reutilizables de UI
- Services: Componentes que se ejecutan en segundo plano
- Models: Clases que representan los datos
- Utils: Funciones auxiliares
- ViewModels: Lógica que conecta la UI con los datos (usando MVVM)

### /res (Recursos)
Todos los recursos no programáticos de la aplicación, organizados por tipo:

#### Layout (/res/layout)
Archivos XML que definen la interfaz de usuario:
- `activity_*.xml`: Diseños para actividades completas
- `fragment_*.xml`: Diseños para fragmentos
- `item_*.xml`: Plantillas para elementos individuales en listas
- `dialog_*.xml`: Diseños para diálogos

#### Values (/res/values)
Valores que se usan en la aplicación:
- `strings.xml`: Textos y traducciones (permite internacionalización)
- `colors.xml`: Paleta de colores de la aplicación
- `dimens.xml`: Dimensiones estándar (márgenes, tamaños de texto)
- `styles.xml` y `themes.xml`: Estilos y temas visuales

#### Drawables (/res/drawable)
Imágenes e ilustraciones:
- Imágenes PNG, JPG, WebP
- XML de formas vectoriales
- Selectores de estado (para botones)

#### Mipmap (/res/mipmap)
Iconos de la aplicación en diferentes resoluciones.

#### Navigation (/res/navigation)
Gráficos de navegación que definen cómo se mueve el usuario entre pantallas.

#### Menu (/res/menu)
Definiciones XML para menús y barras de opciones.

### build.gradle
Archivos de configuración para la herramienta de compilación Gradle:
- Dependencias externas (bibliotecas)
- Configuración de la versión de SDK
- Opciones de compilación y empaquetado

## Componentes Principales en el Código

### Activity
Una actividad representa una pantalla única con interfaz de usuario. 
- `MainActivity.kt`: Punto de entrada principal a la aplicación.

### Fragment
Fragmentos de interfaz reutilizables que se pueden combinar en una actividad.
- `FirstFragment.kt`: Secciones específicas de la UI.

### Views y ViewGroups
- TextView, Button, RecyclerView: Elementos básicos de UI.
- ConstraintLayout, LinearLayout: Contenedores para organizar vistas.

### Adapters
Conectan datos con vistas, especialmente en listas y cuadrículas.

### ViewModels y LiveData
Manejan el ciclo de vida y la comunicación de datos en la arquitectura MVVM.

## Flujo de una Aplicación Android

1. **Inicio**: AndroidManifest define la actividad de inicio.
2. **Creación de UI**: Las actividades cargan layouts XML que definen la interfaz.
3. **Interacción**: Listeners responden a acciones del usuario.
4. **Navegación**: Los componentes de navegación gestionan el movimiento entre pantallas.
5. **Datos**: ViewModel/Repository manejan la lógica y el almacenamiento.

## Consejos de Organización

- Mantén un estilo consistente en todo el proyecto
- Usa recursos de texto en `strings.xml` en lugar de hardcoded
- Agrupa por funcionalidad o por tipo de componente
- Implementa una arquitectura clara (MVC, MVP, MVVM)
- Nombra archivos con prefijos por tipo (activity_, fragment_, etc.) 