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

---

## 🧰 Paso 2: Instalar cmake 

Una ves descargado cmake  **CMake** | 3.16+ | [Descargar CMake (v3.31.7)](https://github.com/Kitware/CMake/releases/download/v3.31.7/cmake-3.31.7-windows-x86_64.msi) 
da doble click y te saldra lo siguiente <img width="353" alt="image" src="https://github.com/user-attachments/assets/dd9a8a8e-411f-48d0-bc49-3eb0c3c7fb6e" /> damos click en next o siguiente <img width="352" alt="image" src="https://github.com/user-attachments/assets/be9247b8-06e7-423d-a3df-3e63b8845720" /> aceptamos los termnnos e servicio y damos next o siguiente luego marcamos las dos opciones que nos aparcen y damos en next <img width="356" alt="image" src="https://github.com/user-attachments/assets/41970b72-00f4-42da-b0a0-6762075b996e" /> dejaremos la ruta por defecto <img width="353" alt="image" src="https://github.com/user-attachments/assets/2c5b12d1-9580-4f31-a819-3b374a5b92a4" /> no te preocupes si tu ruta no es la misma puede aparcer en español algo como C:\Archivos de Programa\CMake\ algo asi solo dale next no modifiques nada de ahi finalemente damos en install <img width="352" alt="image" src="https://github.com/user-attachments/assets/2f78f856-8c4d-4ad0-bb71-ce56ac6af5b9" /> y esperamos a que termine de instalar 

paso 3 instalacionde git 

una ves descargaod desde  **Git for Windows** | Última versión | [Descargar Git](https://github.com/git-for-windows/git/releases/download/v2.49.0.windows.1/Git-2.49.0-64-bit.exe)  

damos doble click en el archivo y nos saldra la siguiente ventana <img width="364" alt="image" src="https://github.com/user-attachments/assets/6719260f-5af1-4316-bf97-ee3367233847" /> damos en next nos saldra la siguiente ventana dejamos la ruta por defecto <img width="368" alt="image" src="https://github.com/user-attachments/assets/71a30fbd-439d-4268-bee5-c23e95398b9b" /> y damos a next nos saldra una lista de dependencias  <img width="352" alt="image" src="https://github.com/user-attachments/assets/c90752d6-f683-4bd7-bbb5-e5dbb4562afc" /> dejamos marcadas las que vienen por defecto y elejimos olo una mas marcaremos una mas la que dice New add a git bash profile to windows terminal damos a next luego otra ves en next <img width="352" alt="image" src="https://github.com/user-attachments/assets/2b861cc2-8f26-464c-b417-e19b6c2264d6" /> en esta parte nos dice elijamos un editor para git dejamos el que esta por defecto a menos que tengas un editor de codigo que perefires instalado si no solo dale a next <img width="373" alt="image" src="https://github.com/user-attachments/assets/de7aaafd-06da-4d64-aff6-47db742febcd" /> aqui damos a next nuevamente sin modificar nada luego en este ventana <img width="366" alt="image" src="https://github.com/user-attachments/assets/51f2d8d2-63e0-445d-a1dd-57a9dfa5d553" /> tampoco modificamos nada y le damos next en la siguiente ventana <img width="375" alt="image" src="https://github.com/user-attachments/assets/e0b61f81-40c8-42e4-8ef2-fed7314b213d" /> tampoco modificamos nda y damos next en la siguiente ventana <img width="375" alt="image" src="https://github.com/user-attachments/assets/f4b1b601-e8ab-47e9-9e0e-e7b862806138" /> tampoco modificamos nada y damos next tampoco modificaremos ndad en esta ventana <img width="375" alt="image" src="https://github.com/user-attachments/assets/02cadcd6-82a5-4314-9803-f282a3cf44af" /> nota en esta ventana donde nos dice de elejir el terminal del bash <img width="375" alt="image" src="https://github.com/user-attachments/assets/0a1886a2-3d69-4b87-8ffb-90536a76349a" /> marcamos la opcion de windows defautl console y damos en next en la siguinet ventana <img width="375" alt="image" src="https://github.com/user-attachments/assets/d788dcb1-824c-47fb-94ad-e43956dbc3ee" /> no modificaremos nada tampoco en esta  <img width="375" alt="image" src="https://github.com/user-attachments/assets/54a88f18-ce4a-4898-83bb-f5e681333df2" /> ni esta <img width="375" alt="image" src="https://github.com/user-attachments/assets/04b6dfba-9420-482a-a47f-fb43c3a19fc0" /> finalmenta damos en install y esperamos a que termine 



paso 4 Instalar Ninja:

Descargar Ninja:**Ninja Build** | v1.12.1 | [Descargar ninja x64 ](https://github.com/ninja-build/ninja/releases/download/v1.12.1/ninja-win.zip) 

descropime el zip con winrar o 7zip y veras un achivo llamado ninja .exe <img width="605" alt="image" src="https://github.com/user-attachments/assets/c9b21532-1088-4a84-905d-b1fd4b473f2f" />   nos vamos al disco local c y creamos una carpeta llamada ninja <img width="600" alt="image" src="https://github.com/user-attachments/assets/f084b5b8-b76c-4272-b254-82e52a05f88e" /> y dentro de ella copiamos el archivo ninja.exe  <img width="959" alt="image" src="https://github.com/user-attachments/assets/e8e40782-aece-4b38-b336-b5da1c8c4d37" /> tendran esta ruta C:\Ninja una ves hecho esto nos vamos a la barra de busqueda de windows y escrbimos editar varianbles de entorno y dame click en la que nos aparece nos saldra una ventana como esta  <img width="299" alt="image" src="https://github.com/user-attachments/assets/8aa00e2d-e007-4f9f-abe3-920553d5ba57" />  damos click donde dice variables de entorno <img width="299" alt="image" src="https://github.com/user-attachments/assets/fab4eff2-b331-4279-abe0-8e2239342a65" /> seleccionamos donde dice path y le damos en el boton de editar <img width="440" alt="image" src="https://github.com/user-attachments/assets/793bd41f-f163-4568-b762-7a2b02a0b987" /> damos click en nuevo y escribimos la ruta <img width="384" alt="image" src="https://github.com/user-attachments/assets/b7155cc3-397e-4a07-a958-4ab370cb9f8a" /> C:\Ninja  luego damos click en aceptar luego en aceptar nuevamente y otra vez en aceptar y se cerrara esa ventana de windows con esto terminamos con ninja

Paso 5 Skia Version m-102

una vez descragado el archivo | **Skia** | Skia-m102 | [Descargar Skia](https://github.com/aseprite/skia/releases/download/m102-861e4743af/Skia-Windows-Release-x64.zip) | antes de descomprimirlo vamos al discoc local c y creamos una carpta llamda deps <img width="509" alt="image" src="https://github.com/user-attachments/assets/215cc506-e702-4399-adc0-f7eba877eb7b" /> y dentro de esa carptea otra llamada "skia" <img width="595" alt="image" src="https://github.com/user-attachments/assets/73669df3-4490-4166-a206-d7c309e4a17c" /> les quedara esta ruta C:\deps\skia vamos a descargar o donde descrgamos el archivo de skia dscompriminos y copiamos todo su contenido a la carpeta que creamos en C:\deps\skia  <img width="839" alt="image" src="https://github.com/user-attachments/assets/0bc334de-18cd-48d6-b158-b2a7527ca30e" />





paso 6 compilar asesprite 

una vez hecho todos los pasos anteiriores toca compilar aseprite una ves descargad asesprite de | **Aseprite** | 1.3.13 | [Descargar Asepritre](https://github.com/aseprite/aseprite/releases/download/v1.3.13/Aseprite-v1.3.13-Source.zip)| Una ves descarga lo primero que tenemos que hacer es ir a el disco local c y crear una carpeta llamada "Aseprite" <img width="530" alt="image" src="https://github.com/user-attachments/assets/e079b7d8-ae16-4474-a2cf-e039da490438" /> 
dentro de ella tenemos que copiar todos los archivos descomprimidos del rar que acabamos de descargar  <img width="845" alt="image" src="https://github.com/user-attachments/assets/a5524d5a-5ec6-4cd4-b08c-a6a5645fb079" /> C:\Aseprite  

una ves hecho esto apretamos la tecla windows y la teclar r escribimos cmd  
una ves abieto escribimos los siguiente comando uno por uno no copien y peguen todos de golpe 

 C:\Aseprite
mkdir build
cd build  
<img width="671" alt="image" src="https://github.com/user-attachments/assets/2f48f963-9ab8-4e66-8357-b0be6a2f11c6" /> 
una ves esten en 
copian y pegan el siguiente comando 
call "C:\Program Files\Microsoft Visual Studio\2022\Community\Common7\Tools\VsDevCmd.bat" -arch=x64 si hiciero bien todo lo anterior el formato del cmd debra cambiar a este no se asuten tarda al menos un minuto en mostrar esto <img width="654" alt="image" src="https://github.com/user-attachments/assets/684d6d47-1eab-4a1a-8ce3-8f0a5bd9c622" /> si les salio eso esta todo correcto de momento vamos con el siguiente comando 


cmake -DCMAKE_BUILD_TYPE=RelWithDebInfo -DLAF_BACKEND=skia -DSKIA_DIR=C:\deps\skia -DSKIA_LIBRARY_DIR=C:\deps\skia\out\Release-x64 -DSKIA_LIBRARY=C:\deps\skia\out\Release-x64\skia.lib -G Ninja ..

como pueden ver el comando tiene todas las rutas que creamos para skia que recordemos esta en C:\deps\skia 

tardara bastante no se preocupen por todos los mensajes que suelta lo importante es que alfunal muestre el siguiente mensaje 


Esta es la parte que indica que todo salio bien 

-- Configuring done (648.3s)
-- Generating done (3.6s)
-- Build files have been written to: C:/Aseprite/build

De ultimo ejecutamos el ultimo comando 
ninja aseprite 

esto activara el compilador una vez que finalize podran econtran su tan esperado aseprite en esta ruta  
C:\Aseprite\build\bin 
No desesperen tarda bastante en compilar pondra algo como C:\Aseprite\build>ninja aseprite
[107/1549] Building  .....

al finalizar pondra lo siguiente

C:\Aseprite\build>ninja aseprite
[1549/1549] Linking CXX executable bin\aseprite.exe


ahora si vamos a esta ruta C:\Aseprite\build\bin
encontraremos el punto exe de aseprite 
<img width="701" alt="image" src="https://github.com/user-attachments/assets/e040db93-2e38-4ff3-a9ba-8aef6cf50f74" /> 
si asi lo desean pueden copiar estos archivos a otra carpeta para que sea mas comodo por ejemplo de documentos 
y listo para ejecutarlo solo dan doble click en el y listo pueden empezar con el mundo de los pixeles 
<img width="958" alt="image" src="https://github.com/user-attachments/assets/b2916595-b8af-4df4-9924-7d27a2132b05" />


---

## 📌 Próximo Tutorial

👉 [Tutorial 02 – Cómo Hacer Tu Primer Sprite Básico con Aseprite](../sprites/02_hacer_primer_sprite.md)

---
