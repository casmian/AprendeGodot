
## 🛠️ Tutorial 01 – Cómo Compilar Aseprite en Windows (desde cero)

## 🕒 Duración estimada: 45 minutos a 1 hora  
## 📌 Objetivo: Tener Aseprite compilado y funcionando en tu PC  
## 🧰 Herramientas Necesarias:
- Git: [Descargar](https://git-scm.com/downloads)
- Node.js: [Descargar (LTS)](https://nodejs.org/)
- Visual Studio Community: [Descargar](https://visualstudio.microsoft.com/vs/community/)
- WinRAR: [Descargar](https://www.win-rar.com/index.html)

---

## 🎯 ¿Por Qué Este Tutorial?

Aseprite es una herramienta increíble para crear **pixel art profesional**. Pero no siempre hay versiones precompiladas disponibles para todos los países o sistemas.

Este tutorial está hecho **para usuarios con pocos recursos técnicos**, como tú.  
Vamos a hacerlo **paso a paso, sin asumir conocimiento previo**, y asegurándonos de no sobrecargar tu PC.

---

## ⚙️ Paso 1: Descargar e Instalar las Herramientas

### 1. **Git**
Herramienta para descargar código desde GitHub.

🔗 [Descargar Git](https://git-scm.com/downloads)  
📌 Al instalar:
- Selecciona “Use Git from Windows Command Prompt”
- Elige “Checkout Windows-style, commit Unix-style line endings”

---

### 2. **Node.js**
Necesario para ejecutar herramientas basadas en JavaScript (como Yarn).

🔗 [Descargar Node.js (LTS)](https://nodejs.org/)  
📌 Al instalar:
- Solo haz clic en "Next" → "Install"

---

### 3. **Yarn**
Gestor de paquetes que usaremos para compilar Aseprite.

🔹 Abre PowerShell (búscalo en el menú Inicio) y copia este comando:

```powershell
npm install --global yarn
```

Presiona Enter y espera a que termine.

---

### 4. **Visual Studio Community**
Compilador necesario para construir proyectos en C++.

🔗 [Descargar Visual Studio Community](https://visualstudio.microsoft.com/vs/community/)  
📌 Al instalar:
- Marca solo esta opción: **“Desarrollo de escritorio con C++”**
- Desmarca todas las demás opciones innecesarias
- Reinicia tu PC al terminar

---

### 5. **WinRAR**
Herramienta para descomprimir archivos `.zip`, `.rar`, etc.

🔗 [Descargar WinRAR](https://www.win-rar.com/index.html)  
📌 Al instalar:
- Sigue los pasos del asistente
- Asocia WinRAR con tus archivos comprimidos

---

## 🧱 Paso 2: Descargar el Código Fuente de Aseprite

🔹 Abre **PowerShell** y copia estos comandos uno por uno:

```powershell
git clone https://github.com/aseprite/aseprite.git
cd aseprite
```

Esto descargará el código fuente de Aseprite en tu computadora.

---

## ⚙️ Paso 3: Compilar Aseprite

🔹 En la misma ventana de PowerShell, escribe:

```powershell
yarn install
yarn build
```

⚠️ Esto puede tardar entre 10 y 30 minutos dependiendo de tu PC.

---

## ▶️ Paso 4: Ejecutar Aseprite

Cuando termine la compilación, ve a la carpeta donde clonaste Aseprite (por ejemplo `C:\Users\TuNombre\aseprite`) y busca dentro de:

```
dist/Aseprite.exe
```

Haz doble clic en ese archivo y... ¡listo! Tienes Aseprite funcionando.

---

## 🗂️ Paso 5: Guardar Sprites para Godot

Cuando crees tus imágenes en Aseprite:
- Usa el menú `File > Export > Export As` y guarda como `.png`.
- Colócalas en tu proyecto de Godot en `/assets/imagenes/personaje_base/` o donde necesites.

---

## 📝 Notas Importantes

- Si ves errores en la consola, no te asustes. Muchas veces se solucionan reiniciando.
- Puedes usar este proceso para otros proyectos basados en Electron.
- Esta guía está optimizada para PCs con pocos recursos. Todo lo que no es necesario ha sido eliminado.

---

## 🚀 Próximo Tutorial

👉 [Tutorial 02 – Cómo Hacer Tu Primer Sprite Básico con Aseprite](../tutoriales/sprites/02_primer_sprite_basico.md)

---
