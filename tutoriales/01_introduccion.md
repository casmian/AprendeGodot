# 🎮 Tutorial 01 – Cómo Instalar Godot y Configurar tu Primer Proyecto

## 🕒 Duración estimada: 20 minutos  
## 📌 Objetivo: Descargar e instalar Godot Engine, y configurar tu primer proyecto vacío  
## 🧰 Herramientas: Godot 4.4.1 (versión recomendada), sistema operativo Windows/Linux/macOS  
## 🧑‍💻 Contenido:

1. Descargar Godot desde la página oficial  
2. Instalarlo en tu computadora  
3. Abrir el editor  
4. Crear un nuevo proyecto  
5. Guardarlo en una carpeta  
6. Conocer la interfaz básica  

---

## 1. Descargar Godot desde la página oficial

Ve a este link:  
👉 https://godotengine.org/download/ 

Allí encontrarás las versiones disponibles para tu sistema operativo.

- Si usas **Windows**: Descarga la versión `.zip` (no necesitas instalar nada).
- Si usas **Linux**: Puedes usar AppImage o instalar desde terminal.
- Si usas **macOS**: Descarga el `.zip` y arrastra Godot a la carpeta Aplicaciones.

📌 **Recomendación:** Usa la versión **4.4.1 Stable** (la más reciente estable).

---

## 2. Instalarlo en tu computadora

**Windows:**
- Descomprime el `.zip`.
- Haz doble clic en el ejecutable `godot.windows.opt.tools.64.exe`.
- ¡Listo! No necesita instalación adicional.

**Linux:**
- Da permisos de ejecución al archivo AppImage.
- Ejecútalo haciendo doble clic o desde terminal.

**macOS:**
- Descomprime el `.zip`.
- Arrastra Godot a la carpeta Aplicaciones.
- Abre la aplicación.

---

## 3. Abrir el editor

Al abrir Godot por primera vez, verás el **"Project Manager"**.

Desde aquí puedes:
- Crear un nuevo proyecto
- Abrir uno existente
- Borrar proyectos antiguos

---

## 4. Crear un nuevo proyecto

Haz clic en **"New Project"**.

- Elige una ubicación donde guardar tu proyecto (por ejemplo: `C:\MisJuegos\PrimerProyecto`)
- Dale un nombre: **"MiPrimerJuego"**

---

## 🔧 5. Elegir el Modo del Proyecto

Aquí viene la parte importante: **elegir el modo del proyecto según tus necesidades**.

Godot te ofrece tres opciones:

### ✅ Forward+

- **¿Qué es?** El modo predeterminado y más moderno.
- **¿Para qué sirve?** Ideal para juegos con gráficos avanzados, luces dinámicas y efectos visuales.
- **¿Cuándo usarlo?** Si planeas hacer un juego con muchos efectos visuales o luces realistas.
- **¿Requisitos?** Necesitas una GPU decente y no es ideal si tu PC es débil.

---

### ✅ Móvil

- **¿Qué es?** Optimizado para dispositivos móviles y hardware limitado.
- **¿Para qué sirve?** Perfecto si quieres exportar tu juego a Android o iOS.
- **¿Cuándo usarlo?** Si tu objetivo final es un juego móvil o si tienes pocos recursos en tu PC.
- **¿Ventaja?** Más rápido y liviano que Forward+.

---

### ✅ Compatibilidad

- **¿Qué es?** Usa OpenGL 3.3 / ES 3.0 / WebGL 2.
- **¿Para qué sirve?** Es compatible con más dispositivos y navegadores web.
- **¿Cuándo usarlo?** Si quieres exportar a HTML5/WebGL o si tu PC tiene muy pocos recursos (como es mi caso).
- **¿Ventaja?** Funciona mejor en PCs básicas como la mía (y probablemente la tuya también).

---

📌 **Josué dice:**  
Yo uso el modo **Compatibilidad**, porque tengo una laptop básica con solo 4GB de RAM y sin una tarjeta gráfica potente. Y funciona bien.  
Así que si tú también empiezas con poco, **elige "Compatibilidad"**. Podrás seguir aprendiendo sin problemas.

---

## 6. Guardarlo en una carpeta

Godot creará automáticamente las carpetas necesarias dentro de tu proyecto:
- `res://` es la carpeta raíz de tu juego.
- Aquí irán tus scripts, imágenes, sonidos, escenas...

---

## 7. Conocer la interfaz básica

Una vez dentro del editor, verás varias secciones:

| Sección | ¿Qué hace? |
|--------|-------------|
| **Escena** | Aquí construyes tu juego con nodos |
| **Nodo** | Muestra las propiedades del nodo seleccionado |
| **FileSystem** | Muestra los archivos de tu proyecto |
| **Viewport** | Aquí ves cómo se ve tu juego mientras lo editas |
| **Barra inferior** | Muestra mensajes, consola, errores... |

No te sientas abrumado/a. En próximos tutoriales aprenderemos qué hace cada parte.

---

## 📝 Notas Finales

- Si Godot se ejecuta lento, cierra otras aplicaciones.
- Asegúrate de tener espacio libre en disco.
- Si algo falla, abre un issue en GitHub o busca ayuda en Discord de Godot.

---

## 🚀 Próximo Tutorial

👉 [Tutorial 02 – Introducción a los Nodos y Escenas en Godot](../tutoriales/02_nodos_y_escenas.md)


