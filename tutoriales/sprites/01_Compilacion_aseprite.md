# 🖼️ Guía de Instalación de Aseprite 1.3.13 en Windows

> Una guía paso a paso para instalar y compilar **Aseprite v1.3.13** en Windows, incluso si no tienes experiencia previa.

Esta guía está pensada para desarrolladores que quieren usar **herramientas libres, gratuitas y accesibles**, ideal para personas como tú que empiezan desde cero y tienen pocos recursos técnicos.

---

## ⚠️ Notas Importantes Antes de Empezar

- ❌ No uses MinGW – Aseprite **no lo soporta oficialmente**
- ⚙️ Desactiva temporalmente **Windows Defender** si bloquea los archivos por falso positivo
- 🔧 Todas las herramientas necesarias son para un sistema Windows de 64 bits
- 🔄 Si algo falla, limpia `%WORKING%` y `%TEMP%` antes de volver a intentar

---

## 🔧 Herramientas Necesarias

Antes de empezar, asegúrate de tener estas herramientas instaladas:


| Herramienta | Versión Mínima | Descarga |
|-------------|----------------|----------|
| **Visual Studio Community 2022** | Community Edition | [Descargar Visual Studio](https://visualstudio.microsoft.com/es/vs/community/) |
| **CMake** | 3.16+ | [Descargar CMake (v3.31.7)](https://github.com/Kitware/CMake/releases/download/v3.31.7/cmake-3.31.7-windows-x86_64.msi) |
| **Ninja Build** | v1.12.1 | [Descargar ninja x64 ](https://github.com/ninja-build/ninja/releases/download/v1.12.1/ninja-win.zip) |
| **Git for Windows** | Última versión | [Descargar Git](https://github.com/git-for-windows/git/releases/download/v2.49.0.windows.1/Git-2.49.0-64-bit.exe)|
| **WinRAR (opcional)** | — | [Descargar WinRAR](https://www.win-rar.com/index.html) |

📌 Estas herramientas te permitirán compilar Aseprite desde el código fuente.

📦 Una vez descargadas, sigue esta guía para instalarlas correctamente.

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

2. Una vez descargado, haz doble clic en el instalador.  
   Deberías ver una ventana como esta:  
   <img width="357" alt="Ventana inicial del instalador de Visual Studio" src="https://github.com/user-attachments/assets/928a5a1c-e4cc-469d-a87e-2f5afb3705f4" />  
   Haz clic en **"Continuar"**.

3. Se abrirá el instalador. Busca la sección de **Trabajo para móviles y escritorio** y selecciona:  
   ✅ **Desarrollo para el escritorio con C++**  
   <img width="926" alt="Opciones de carga de trabajo" src="https://github.com/user-attachments/assets/c4c559df-055c-4530-92f7-25f408eb8813" />

4. Ahora ve a **Detalles de la instalación** y desmarca todas las opciones actuales.

5. Marca solo estos componentes:
   - ✅ **Herramientas de compilación de MSVC v143-VS 2022 para x64/x86**
   - ✅ **ATL de C++ para herramientas de compilación v143 (x86/x64)**
   - ✅ **Herramientas de CMake en C++ para Windows**
   - ✅ **Administrador de paquetes vcpkg**
   - ✅ **AddressSanitizer para C++**
   - ✅ **Windows SDK 10.0.20348.0**

6. Haz clic en **"Instalar"** y espera a que termine.

📌 Una vez terminado, cierra todas las ventanas del instalador.

---

## 🧰 Paso 3: Compilación Automática de Aseprite

Usaremos un **script automatizado** para compilar Aseprite sin tener que hacerlo manualmente.

### 1. **Crea esta carpeta:**

```bash
C:\asebuild\deps\
```

### 2. **Guarda el script como `build.bat` en:**

```bash
C:\herramientas\aseprite\build.bat
```

El script descargará automáticamente:
- 📁 Código fuente de Aseprite 1.3.13
- 🧱 Skia precompilado (necesario para gráficos avanzados)
- 🔧 Configurará todo para compilar con Visual Studio

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

1. Abre **PowerShell como Administrador**
2. Navega a la carpeta del script:

   ```powershell
   cd C:\herramientas\aseprite\
   ```

3. Ejecuta el script:

   ```powershell
   .\build.bat
   ```

⚠️ Este proceso puede tardar entre 15 minutos y media hora, según tu conexión.

---

## 🗂️ Paso 6: Encuentra el Ejecutable Final

Una vez terminada la compilación, encontrarás Aseprite aquí:

```
C:\asebuild\deps\aseprite\build\bin\aseprite.exe
```

Puedes mover este archivo a donde prefieras:  
Ejemplo: `D:\apps\aseprite\`, `E:\juegos\tools\aseprite\`


---

## 📌 Próximo Tutorial

👉 [Tutorial 02 – Cómo Hacer Tu Primer Sprite Básico con Aseprite](../sprites/02_hacer_primer_sprite.md)

---
