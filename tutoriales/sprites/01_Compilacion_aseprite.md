# 🖼️ Guía de Instalación de Aseprite 1.3.13 en Windows

> Una guía paso a paso para instalar y compilar **Aseprite v1.3.13** en Windows, incluso si no tienes experiencia previa.

Esta guía está pensada para desarrolladores que quieren usar **herramientas libres, gratuitas y accesibles**, ideal para personas como tú que empiezan desde cero y tienen pocos recursos técnicos.

---

## 🔧 Requisitos Previos

Antes de comenzar, asegúrate de tener descargado lo siguiente:

| Herramienta | Versión Mínima | Descarga |
|-------------|----------------|----------|
| **Visual Studio Community 2022** | Community Edition | [Descargar Visual Studio](https://visualstudio.microsoft.com/es/vs/community/) |
| **CMake** | 3.16+ | [Descargar CMake (v3.31.7)](https://github.com/Kitware/CMake/releases/download/v3.31.7/cmake-3.31.7-windows-x86_64.msi) |
| **Ninja Build** | v1.12.1 | [x64](https://github.com/ninja-build/ninja/releases/download/v1.12.1/ninja-win.zip) / [ARM64](https://github.com/ninja-build/ninja/releases/download/v1.12.1/ninja-winarm64.zip) |
| **Windows SDK** | 10.0.20348.0 | Dependencia que se instala al configurar VS Community |
| **Git for Windows** | Última versión | [Descargar Git](https://git-scm.com/downloads) |
| **WinRAR (si no lo tienes)** | — | [Descargar WinRAR](https://www.win-rar.com/index.html) |

📌 Estas herramientas te permitirán compilar Aseprite desde el código fuente.
📦 Una ves descargados tendras que instalarlos segun la guia..

---

## ⚠️ Notas Importantes

- No uses MinGW – Aseprite **no lo soporta oficialmente**.
- Desactiva temporalmente **Windows Defender** si bloquea los archivos por falso positivo.
- El script crea y borra carpetas automáticamente → no muevas nada mientras se ejecuta.
- Si algo falla, limpia `%WORKING%` y `%TEMP%` antes de volver a intentar.

---

## 📦 Paso 1: Instalación de Scoop (Recomendado)

Scoop es un gestor de paquetes para Windows que facilita la instalación de dependencias como Ninja y CMake.

### Pasos:

1. **Abre PowerShell como administrador**
2. **Habilita la ejecución de scripts:**

   ```powershell
   Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
   ```

3. **Instala Scoop:**

   ```powershell
   Invoke-RestMethod -Uri https://get.scoop.sh | Invoke-Expression
   ```

4. **Usa Scoop para instalar dependencias necesarias:**

   ```powershell
   scoop install ninja cmake
   ```

---

## 💻 Paso 2: Instalación de Visual Studio Community 2022

1. Ve a:  
   👉 [Descargar Visual Studio 2022 Community](https://visualstudio.microsoft.com/es/thank-you-downloading-visual-studio/?sku=Community&channel=Release&version=VS2022&source=VSLandingPage&passive=false&cid=2030)

2. Durante la instalación, selecciona solo esta carga de trabajo:
   - ✅ **Desarrollo para el escritorio con C++**

3. Usa este archivo `.vsconfig` para automatizar la instalación solo con lo necesario:

### 📁 Archivo: `.vsconfig`
```json
{
  "version": "1.0",
  "components": [
    "Microsoft.VisualStudio.Component.CoreEditor",
    "Microsoft.VisualStudio.Workload.CoreEditor",
    "Microsoft.VisualStudio.Component.Roslyn.Compiler",
    "Microsoft.Component.MSBuild",
    "Microsoft.VisualStudio.Component.TextTemplating",
    "Microsoft.VisualStudio.Component.VC.CoreIde",
    "Microsoft.VisualStudio.Component.VC.Tools.x86.x64",
    "Microsoft.VisualStudio.Component.VC.ATL",
    "Microsoft.VisualStudio.Component.VC.Redist.14.Latest",
    "Microsoft.VisualStudio.ComponentGroup.NativeDesktop.Core",
    "Microsoft.VisualStudio.ComponentGroup.WebToolsExtensions.CMake",
    "Microsoft.VisualStudio.Component.VC.CMake.Project",
    "Microsoft.VisualStudio.Component.VC.ASAN",
    "Microsoft.VisualStudio.Component.Vcpkg",
    "Microsoft.VisualStudio.Component.Windows10SDK.18362",
    "Microsoft.VisualStudio.Workload.NativeDesktop"
  ],
  "extensions": []
}
```

Guarda ese archivo como `.vsconfig` y úsalo durante la instalación de VS.

---

## 🧰 Paso 3: Compilación Automática de Aseprite

Para facilitar el proceso, usaremos un script automatizado para descargar e instalar Aseprite.

### 1. **Crea esta carpeta:**

```
C:\asebuild\deps\
```

### 2. **Guarda el script como `build.bat` en:**

```
C:\herramientas\aseprite\build.bat
```

El script descargará automáticamente:
- El código fuente de Aseprite 1.3.13
- Skia precompilado (necesario para gráficos avanzados)
- Y configurará todo para compilar con Visual Studio

🔗 [Descargar Skia para Windows x64](https://github.com/aseprite/skia/releases/download/m102-861e4743af/Skia-Windows-Release-x64.zip)  
🔗 [Descargar Skia para ARM64 (Mac M1/M2)](https://github.com/aseprite/skia/releases/download/m102-861e4743af/Skia-Windows-Release-arm64.zip)

---

## ⚙️ Paso 4: Configura las Rutas del Script

Revisa estas variables dentro del `.bat` y cámbialas si es necesario:

```bat
set WORKING=C:\asebuild
set DEPS=%WORKING%\deps
set ASEPRITE=%DEPS%\aseprite
set SKIA=%DEPS%\skia
set ASEZIP=https://github.com/aseprite/aseprite/releases/download/v1.3.13/Aseprite-v1.3.13-Source.zip
set SKIAZIP=https://github.com/aseprite/skia/releases/download/m102-861e4743af/Skia-Windows-Release-x64.zip
set VISUALSTUDIO="C:\Program Files\Microsoft Visual Studio\2022\Community"
set WINSDK="C:\Program Files (x86)\Microsoft SDKs\Windows Kits\10\ExtensionSDKs\Microsoft.UniversalCRT.Debug\10.0.20348.0"
set TEMP=%WORKING%\temp
```

📌 Si instalaste Visual Studio en otra unidad o tienes Windows en otro idioma, ajusta las rutas manualmente.

---

## 🧱 Paso 5: Ejecuta el Script

1. Abre PowerShell como Administrador.
2. Ve a tu carpeta de herramientas:

   ```powershell
   cd C:\herramientas\aseprite\
   ```

3. Ejecuta el script:

   ```powershell
   .\build.bat
   ```

⚠️ El proceso puede tardar entre 15 minutos y media hora, dependiendo de tu conexión e Internet.

---

## 🗂️ Paso 6: Encuentra el Ejecutable Final

Al terminar, encontrarás Aseprite aquí:

```
C:\asebuild\deps\aseprite\build\bin\aseprite.exe
```

Puedes copiar esa carpeta a donde prefieras (`D:\apps\aseprite`, etc.)

---


---

## 📌 Próximo Tutorial

👉 [Tutorial 02 – Cómo Hacer Tu Primer Sprite Básico con Aseprite](../sprites/02_hacer_primer_sprite.md)

---
