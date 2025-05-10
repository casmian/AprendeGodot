# 🧱 Guía: Cómo Compilar Aseprite en Windows con Visual Studio Community

> Esta guía está hecha para personas que empiezan desde cero y no tienen experiencia técnica.

---

## 🎯 ¿Por Qué Esta Guía?

Compilar Aseprite puede parecer algo técnico, pero es posible hacerlo incluso si:
- Tienes pocos recursos
- No sabes programar
- Usas Windows 10 o 11
- Quieres usar herramientas libres y gratuitas

Y lo mejor: **no necesitas instalar todo Visual Studio**, solo las partes esenciales.

---

## 🔧 Herramientas Necesarias

| Herramienta | Descripción | Link |
|-------------|-------------|------|
| **Git for Windows** | Para descargar el código fuente de Aseprite | [Descargar Git](https://git-scm.com/downloads) |
| **Node.js + Yarn** | Para proyectos basados en Electron (opcional) | [Descargar Node.js](https://nodejs.org/) |
| **Visual Studio Community 2022** | El compilador principal | [Descargar VS Community](https://visualstudio.microsoft.com/vs/community/) |
| **CMake** | Para gestionar la compilación | [Descargar CMake](https://cmake.org/download/) |
| **Ninja Build** | Sistema rápido de construcción | [Descargar Ninja](https://github.com/ninja-build/ninja/releases) |
| **WinRAR** | Para descomprimir archivos `.zip` y `.rar` | [Descargar WinRAR](https://www.win-rar.com/index.html) |

📌 **Importante:**  
No uses MinGW ni GCC. El proyecto oficial de Aseprite **no los soporta** y pueden causar errores.

---

## 📁 Archivo de Configuración Personalizada para Visual Studio (`vsconfig.vsconfig`)

Este archivo te permite instalar **solo lo necesario** para compilar Aseprite:

```json
{
  "version": "1.0",
  "components": [
    "Microsoft.VisualStudio.Component.CoreEditor",
    "Microsoft.VisualStudio.Workload.CoreEditor",
    "Microsoft.VisualStudio.Component.VC.Tools.x86.x64",
    "Microsoft.VisualStudio.Component.Windows10SDK.18362"
  ],
  "extensions": []
}
```

### ✅ Cómo Usarlo

1. Guarda este archivo como `vsconfig.vsconfig`
2. Abre PowerShell como administrador
3. Ejecuta:

```powershell
vs_installer.exe --config vsconfig.vsconfig
```

---

## 📦 Paso a Paso: Compilar Aseprite en Windows

### Paso 1: Descargar el Código Fuente

Abre PowerShell y ejecuta:

```powershell
git clone --recursive https://github.com/aseprite/aseprite.git
cd aseprite
```

📌 Si no tienes Git instalado, asegúrate de haber descargado e instalado **Git for Windows** (viene con interfaz BASH y GUI).

---

### Paso 2: Preparar Skia

Aseprite necesita la biblioteca **Skia** para gráficos avanzados.

#### Opción A: Usar una Versión Precompilada (Recomendada)
Ve a esta página y descarga una versión precompilada de Skia:
👉 [https://github.com/aseprite/skia/releases](https://github.com/aseprite/skia/releases)

Descomprime la carpeta en:
```
C:\deps\skia
```

---

### Paso 3: Crear Carpeta de Construcción

Dentro de la carpeta donde clonaste Aseprite, crea una carpeta llamada `build`.

```powershell
mkdir build
cd build
```

---

### Paso 4: Configurar CMake

En PowerShell, escribe este comando (ajustado a tus rutas):

```powershell
cmake -G Ninja ^
  -DLAF_BACKEND=skia ^
  -DSKIA_DIR=C:/deps/skia ^
  -DSKIA_LIBRARY_DIR=C:/deps/skia/out/Release-x64 ^
  -DSKIA_LIBRARY=C:/deps/skia/out/Release-x64/skia.lib
```

📌 Asegúrate de que las rutas sean correctas según dónde guardaste Skia.

---

### Paso 5: Compilar con Ninja

Una vez que CMake haya terminado, ejecuta:

```powershell
ninja aseprite
```

⚠️ Este paso puede tardar entre 10 minutos y más de media hora, dependiendo de tu PC.

---

### Paso 6: Ejecutar Aseprite

Al finalizar, encontrarás el ejecutable aquí:

```
C:\aseprite\build\bin\aseprite.exe
```

Haz doble clic y... ¡listo! Tienes Aseprite funcionando en tu equipo.

---

## ⚠️ Notas Importantes

- **Windows Defender puede bloquear archivos temporales** → Desactiva protección temporalmente.
- **No uses MinGW**: Puede causar errores graves.
- **Si ves errores de compilación**, reinicia y vuelve a probar.
- **Guarda todo en una carpeta simple**, sin espacios ni tildes.

---

## 📂 Recomendación de Estructura del Proyecto

```
AprendeGodot/
│
├── /tutoriales/
│   └── sprites/
│       ├── 01_compilar_aseprite.md
│       └── 02_hacer_primer_sprite.md
│
├── /herramientas/
│   └── vsconfig.vsconfig
│
└── ...
```

---

## 📌 Próximo Tutorial

👉 [Tutorial 02 – Cómo Hacer Tu Primer Sprite Básico con Aseprite](../tutoriales/sprites/02_hacer_primer_sprite.md)

---

