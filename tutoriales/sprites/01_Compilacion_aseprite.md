# 🖼️ Guía de Instalación de Aseprite 1.3.13 en Windows

> Una guía paso a paso para instalar y compilar **Aseprite v1.3.13** en Windows, incluso si no tienes experiencia previa.

Esta guía está pensada para desarrolladores que quieren usar **herramientas libres, gratuitas y accesibles**, ideal para personas como tú que empiezan desde cero y tienen pocos recursos técnicos.

---

## ⚠️ Notas Importantes Antes de Empezar

- ❌ No uses MinGW – Aseprite **no lo soporta oficialmente**
- ⚙️ Desactiva temporalmente **Windows Defender** si bloquea los archivos por falso positivo
- 🔧 Todas las herramientas necesarias son para un sistema Windows de 64 bits

---

## 🔧 Herramientas Necesarias

Antes de empezar, asegúrate de tener estas herramientas Descargadas:


| Herramienta | Versión Mínima | Descarga |
|-------------|----------------|----------|
| **Visual Studio Community 2022** | Community Edition | [Descargar Visual Studio](https://visualstudio.microsoft.com/es/vs/community/) |
| **CMake** | 3.16+ | [Descargar CMake (v3.31.7)](https://github.com/Kitware/CMake/releases/download/v3.31.7/cmake-3.31.7-windows-x86_64.msi) |
| **Ninja Build** | v1.12.1 | [Descargar ninja x64 ](https://github.com/ninja-build/ninja/releases/download/v1.12.1/ninja-win.zip) |
| **Git for Windows** | Última versión | [Descargar Git](https://github.com/git-for-windows/git/releases/download/v2.49.0.windows.1/Git-2.49.0-64-bit.exe)|
| **WinRAR (opcional)** | — | [Descargar WinRAR](https://www.win-rar.com/index.html) | 
| **Skia** | Skia-m102 | [Descargar Skia](https://github.com/aseprite/skia/releases/download/m102-861e4743af/Skia-Windows-Release-x64.zip) | 
| **Aseprite** | 1.3.13 | [Descargar Asepritre](https://github.com/aseprite/aseprite/releases/download/v1.3.13/Aseprite-v1.3.13-Source.zip)| 

📌 Estas herramientas te permitirán compilar Aseprite desde el código fuente.

📦 Una vez descargadas, sigue esta guía para instalarlas correctamente.

---

## 💻 Paso 1: Instalación de Visual Studio Community 2022

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


Perfecto, aquí tienes tu versión con las **imágenes ubicadas debajo de cada texto** correspondiente, ideal para una presentación clara y secuencial:

---

## 🧰 Paso 2: Instalar CMake

Una vez descargado **CMake**, haz doble clic en el instalador. Aparecerá la siguiente pantalla:

* **Herramienta:** `CMake v3.31.7`
* **Enlace de descarga:**
  👉 [Descargar CMake (v3.31.7)](https://github.com/Kitware/CMake/releases/download/v3.31.7/cmake-3.31.7-windows-x86_64.msi)

---

### 🔹 Pantallas del Instalador

1. **Pantalla inicial:**
   Haz clic en **Next** o **Siguiente**.

   <img width="353" alt="Pantalla inicial del instalador de CMake" src="https://github.com/user-attachments/assets/dd9a8a8e-411f-48d0-bc49-3eb0c3c7fb6e" />

2. **Términos de uso:**
   Acepta los **términos del servicio** y vuelve a hacer clic en **Next**.

   <img width="352" alt="Aceptamos los términos de servicio" src="https://github.com/user-attachments/assets/be9247b8-06e7-423d-a3df-3e63b8845720" />

3. **Componentes adicionales:**
   Marca ambas opciones:

   * ✅ *Add CMake to the system PATH for all users*
   * ✅ *Create shortcuts in Start Menu*

   Luego, haz clic en **Next**.

   <img width="356" alt="Seleccionar componentes adicionales" src="https://github.com/user-attachments/assets/41970b72-00f4-42da-b0a0-6762075b996e" />


### 📁 Elegir carpeta de instalación

Se abrirá esta ventana:

<img width="353" alt="Ruta de instalación por defecto" src="https://github.com/user-attachments/assets/2c5b12d1-9580-4f31-a819-3b374a5b92a4" />

Deja la **ruta por defecto**, a menos que tengas una razón específica para cambiarla.
En sistemas en español, podría mostrarse como:

```
C:\Archivos de Programa\CMake\
```

> ⚠️ Si no estás seguro de lo que haces, no cambies nada. Usa la configuración predeterminada.

Haz clic en **Next** y luego en **Install**.


### 🛠️ Finalizar instalación

Espera a que finalice la instalación.
Una vez terminado, haz clic en **Finish**.

<img width="352" alt="Pantalla final de instalación de CMake" src="https://github.com/user-attachments/assets/2f78f856-8c4d-4ad0-bb71-ce56ac6af5b9" />

---

📌 **¡Listo!**
CMake está correctamente instalado y listo para usarse.


---

## 🧰 Paso 3: Instalación de Git

Una vez descargado desde:
👉 **Git for Windows** | Última versión
[Descargar Git](https://github.com/git-for-windows/git/releases/download/v2.49.0.windows.1/Git-2.49.0-64-bit.exe)

Haz doble clic en el archivo. Verás la siguiente ventana:

<img width="364" alt="Pantalla de inicio del instalador de Git" src="https://github.com/user-attachments/assets/6719260f-5af1-4316-bf97-ee3367233847" />

Haz clic en **Next**.

---

### 📁 Carpeta de instalación

Se mostrará la ruta de instalación:

<img width="368" alt="Ruta de instalación" src="https://github.com/user-attachments/assets/71a30fbd-439d-4268-bee5-c23e95398b9b" />

Deja la ruta por defecto y haz clic en **Next**.

---

### ⚙️ Selección de componentes

Aparecerá una lista de componentes:

<img width="352" alt="Lista de componentes" src="https://github.com/user-attachments/assets/c90752d6-f683-4bd7-bbb5-e5dbb4562afc" />

Deja marcadas las opciones por defecto.
Marca **una adicional**:
✅ *New: Add a Git Bash profile to Windows Terminal*
Luego haz clic en **Next**.

---

### 📝 Selección del editor por defecto

Aparecerá una pantalla para elegir el editor de Git:

<img width="352" alt="Editor por defecto" src="https://github.com/user-attachments/assets/2b861cc2-8f26-464c-b417-e19b6c2264d6" />

Deja el que está por defecto (usualmente Vim o Notepad++)
Haz clic en **Next**.

---

<img width="373" alt="Pantalla siguiente sin cambios" src="https://github.com/user-attachments/assets/de7aaafd-06da-4d64-aff6-47db742febcd" />

Haz clic en **Next** sin modificar nada.

---

<img width="366" alt="Configuraciones adicionales" src="https://github.com/user-attachments/assets/51f2d8d2-63e0-445d-a1dd-57a9dfa5d553" />

Haz clic en **Next** sin cambiar nada.

---

<img width="375" alt="Configuraciones sin cambio 2" src="https://github.com/user-attachments/assets/e0b61f81-40c8-42e4-8ef2-fed7314b213d" />

Nuevamente, **no modifiques nada**. Haz clic en **Next**.

---

<img width="375" alt="Configuraciones sin cambio 3" src="https://github.com/user-attachments/assets/f4b1b601-e8ab-47e9-9e0e-e7b862806138" />

Sin cambios, clic en **Next**.

---

<img width="375" alt="Configuraciones sin cambio 4" src="https://github.com/user-attachments/assets/02cadcd6-82a5-4314-9803-f282a3cf44af" />

Tampoco modifiques nada. Haz clic en **Next**.

---

### 💻 Selección del terminal Bash

<img width="375" alt="Seleccionar consola por defecto" src="https://github.com/user-attachments/assets/0a1886a2-3d69-4b87-8ffb-90536a76349a" />

Selecciona **"Use Windows default console window"**.
Haz clic en **Next**.

---

<img width="375" alt="Sin cambios terminal extra" src="https://github.com/user-attachments/assets/d788dcb1-824c-47fb-94ad-e43956dbc3ee" />

Haz clic en **Next** sin cambiar nada.

---

<img width="375" alt="Configuraciones extra 1" src="https://github.com/user-attachments/assets/54a88f18-ce4a-4898-83bb-f5e681333df2" />

Haz clic en **Next** sin modificar opciones.

---

<img width="375" alt="Configuraciones extra 2" src="https://github.com/user-attachments/assets/04b6dfba-9420-482a-a47f-fb43c3a19fc0" />

Nuevamente, clic en **Next** sin cambios.

Finalmente, haz clic en **Install** y espera a que termine el proceso.

---

📌 **¡Listo!**
Git estará instalado y listo para su uso en tu sistema.

---
Perfecto, Eduardo. Entiendo completamente: quieres que cada imagen vaya **debajo del texto que explica el paso**, no a la par, para mantener una presentación limpia y ordenada. Aquí te dejo el **Paso 4: Instalación de Ninja** corregido con ese formato:

---

### Paso 4: Instalación de Ninja

**Descargar Ninja:**
**Ninja Build** | v1.12.1 | [Descargar ninja x64](https://github.com/ninja-build/ninja/releases/download/v1.12.1/ninja-win.zip)

Descargamos el archivo `.zip` y lo descomprimimos con WinRAR o 7-Zip. Veremos un único archivo llamado `ninja.exe`.

<img width="400" alt="ninja.exe" src="https://github.com/user-attachments/assets/c9b21532-1088-4a84-905d-b1fd4b473f2f" />

Vamos al disco local **C:** y creamos una carpeta llamada `Ninja`.

<img width="400" alt="crear carpeta ninja" src="https://github.com/user-attachments/assets/f084b5b8-b76c-4272-b254-82e52a05f88e" />

Luego copiamos dentro el archivo `ninja.exe`. Debe quedar con esta ruta: `C:\Ninja`.

<img width="400" alt="ninja en C" src="https://github.com/user-attachments/assets/e8e40782-aece-4b38-b336-b5da1c8c4d37" />

---

### Agregar Ninja a las variables de entorno

Vamos a la barra de búsqueda de Windows y escribimos **"editar variables de entorno"**, luego damos clic en la opción que aparece.

<img width="250" alt="buscar variables" src="https://github.com/user-attachments/assets/8aa00e2d-e007-4f9f-abe3-920553d5ba57" />

En la ventana que se abre, hacemos clic en el botón **“Variables de entorno…”**.

<img width="250" alt="botón variables de entorno" src="https://github.com/user-attachments/assets/fab4eff2-b331-4279-abe0-8e2239342a65" />

Seleccionamos la variable llamada **Path** y damos clic en **Editar**.

<img width="350" alt="editar path" src="https://github.com/user-attachments/assets/793bd41f-f163-4568-b762-7a2b02a0b987" />

En la nueva ventana, damos clic en **Nuevo** y escribimos la ruta:
`C:\Ninja`

<img width="300" alt="agregar ruta" src="https://github.com/user-attachments/assets/b7155cc3-397e-4a07-a958-4ab370cb9f8a" />

Finalmente, damos clic en **Aceptar**, luego en **Aceptar** nuevamente y otra vez más para cerrar todas las ventanas.

---


---

### Paso 5: Skia versión m-102

Descargamos la versión m-102 de Skia desde el siguiente enlace:
**Skia** | m102 | [Descargar Skia](https://github.com/aseprite/skia/releases/download/m102-861e4743af/Skia-Windows-Release-x64.zip)

Antes de descomprimir el archivo, vamos al disco local **C:** y creamos una carpeta llamada `deps`.

<img width="509" alt="image" src="https://github.com/user-attachments/assets/215cc506-e702-4399-adc0-f7eba877eb7b" />

Dentro de `deps`, creamos otra carpeta llamada `skia`.

<img width="595" alt="image" src="https://github.com/user-attachments/assets/73669df3-4490-4166-a206-d7c309e4a17c" />

Nos debe quedar la siguiente ruta: `C:\deps\skia`.

Ahora descomprimimos el archivo `.zip` que descargamos y **copiamos todo su contenido** dentro de la carpeta `C:\deps\skia`.

<img width="839" alt="image" src="https://github.com/user-attachments/assets/0bc334de-18cd-48d6-b158-b2a7527ca30e" />

---

### Paso 6: Compilar Aseprite

Descargamos el código fuente de Aseprite desde:
**Aseprite** | v1.3.13 | [Descargar Aseprite](https://github.com/aseprite/aseprite/releases/download/v1.3.13/Aseprite-v1.3.13-Source.zip)

Creamos una carpeta en `C:\` llamada `Aseprite`.

<img width="530" alt="image" src="https://github.com/user-attachments/assets/e079b7d8-ae16-4474-a2cf-e039da490438" />

Descomprimimos el archivo descargado y **copiamos todos los archivos extraídos dentro de esa carpeta**.
Debe quedarte así: `C:\Aseprite`.

<img width="845" alt="image" src="https://github.com/user-attachments/assets/a5524d5a-5ec6-4cd4-b08c-a6a5645fb079" />

Ahora abrimos la terminal: presionamos **Windows + R**, escribimos `cmd` y presionamos Enter.

En la terminal, escribimos uno por uno los siguientes comandos:

```
cd C:\Aseprite
mkdir build
cd build
```

<img width="671" alt="image" src="https://github.com/user-attachments/assets/2f48f963-9ab8-4e66-8357-b0be6a2f11c6" />

Luego, ejecutamos el siguiente comando para configurar el entorno de Visual Studio (tardará un poco):

```
call "C:\Program Files\Microsoft Visual Studio\2022\Community\Common7\Tools\VsDevCmd.bat" -arch=x64
```

<img width="654" alt="image" src="https://github.com/user-attachments/assets/684d6d47-1eab-4a1a-8ce3-8f0a5bd9c622" />

Si todo está bien, el prompt del CMD cambiará al estilo de entorno de desarrollo.

A continuación, ejecutamos el siguiente comando para configurar la compilación con Skia:

```
cmake -DCMAKE_BUILD_TYPE=RelWithDebInfo -DLAF_BACKEND=skia -DSKIA_DIR=C:\deps\skia -DSKIA_LIBRARY_DIR=C:\deps\skia\out\Release-x64 -DSKIA_LIBRARY=C:\deps\skia\out\Release-x64\skia.lib -G Ninja ..
```

Este paso tardará bastante. Ignora los muchos mensajes del proceso. Lo importante es que al final veas algo como esto:

```
-- Configuring done (648.3s)
-- Generating done (3.6s)
-- Build files have been written to: C:/Aseprite/build
```

Finalmente, compilamos con el siguiente comando:

```
ninja aseprite
```

Esto iniciará la compilación final. Aparecerán muchos mensajes como este:

```
[107/1549] Building ...
```

Cuando todo termine correctamente, deberías ver:

```
[1549/1549] Linking CXX executable bin\aseprite.exe
```

Ahora navega a `C:\Aseprite\build\bin` y encontrarás el ejecutable de Aseprite.

<img width="701" alt="image" src="https://github.com/user-attachments/assets/e040db93-2e38-4ff3-a9ba-8aef6cf50f74" />

Puedes copiar estos archivos a otra carpeta (por ejemplo, en Documentos) para tener más comodidad.
¡Listo! Solo haz doble clic en el archivo `.exe` y comienza tu aventura en el mundo del pixel art.

<img width="958" alt="image" src="https://github.com/user-attachments/assets/b2916595-b8af-4df4-9924-7d27a2132b05" />

---

## 📌 Próximo Tutorial

👉 [Tutorial 02 – Cómo Hacer Tu Primer Sprite Básico con Aseprite](../sprites/02_hacer_primer_sprite.md)

---
