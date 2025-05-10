# 📚 Clases Principales de Godot 4.4 – Explicadas Paso a Paso

Godot está construido sobre una jerarquía de clases muy bien definida. Aquí te explico las más importantes, desde las más básicas hasta las más complejas.

---

## 🔷 Nodo (`Node`)

- **¿Qué es?** La clase base de casi todo en Godot.
- **¿Para qué sirve?** Es el bloque fundamental de cualquier escena.
- **Ejemplo:** Un personaje, una cámara, un botón... todo es un nodo.
- **Hereda de:** Object
- **Hijos comunes:** Node2D, Spatial (en 3D), Control

---

## 📦 Escena (`PackedScene`)

- **¿Qué es?** Una plantilla reutilizable de una colección de nodos.
- **¿Para qué sirve?** Para instanciar objetos como enemigos, balas, etc.
- **Ejemplo:** Instanciar una bala cuando el jugador dispara.

---

## 🧮 GDScript

- **¿Qué es?** El lenguaje de programación principal de Godot.
- **¿Para qué sirve?** Para escribir scripts que controlan el comportamiento de los nodos.
- **Similar a:** Python
- **Ejemplo:** Asignar movimiento a un personaje

---

## 🎮 Node2D / Sprite2D

- **¿Qué es?** Clases para trabajar con gráficos 2D.
- **¿Para qué sirve?** Dibujar imágenes, animaciones, personajes...
- **Ejemplo:** Crear un personaje que camina

---

## 🎵 AudioStreamPlayer

- **¿Qué es?** Reproduce archivos de audio.
- **¿Para qué sirve?** Reproducir música y efectos de sonido pregrabados.
- **Ejemplo:** Sonido de salto, música de fondo

---

## 🔊 AudioStreamGenerator

- **¿Qué es?** Genera sonido desde código.
- **¿Para qué sirve?** Crear sonidos procedurales desde cero.
- **Ejemplo:** Generar tonos, ruidos, música procedural

---

## 🎛️ Control / Button / Label

- **¿Qué es?** Herramientas para crear interfaces gráficas.
- **¿Para qué sirve?** Menús, HUDs, opciones, etc.
- **Ejemplo:** Botón de "Play" en el menú principal

---

## 🧱 TileMap

- **¿Qué es?** Herramienta para crear niveles rápidos con mosaicos.
- **¿Para qué sirve?** Diseñar mapas en 2D fácilmente.
- **Ejemplo:** Mapa de un juego tipo Metroidvania

---

## 🕹️ AnimationPlayer

- **¿Qué es?** Sistema de animación del motor.
- **¿Para qué sirve?** Crear animaciones de propiedades, nodos, sprites...
- **Ejemplo:** Animación de caminar de un personaje

---

## 🧭 Input / InputMap

- **¿Qué es?** Sistema de entrada del motor.
- **¿Para qué sirve?** Detectar teclas, clicks, controles...
- **Ejemplo:** Mover personaje con flechas del teclado

---

## 📁 FileSystem / FileAccess

- **¿Qué es?** Herramientas para leer y escribir archivos.
- **¿Para qué sirve?** Guardar partidas, cargar datos externos...
- **Ejemplo:** Guardar puntaje máximo en un archivo `.txt`

---

## 🧠 Más Clases (Próximamente)
- Camera2D
- Area2D / CollisionShape2D
- RigidBody2D
- KinematicBody2D
- ShaderMaterial
- Y muchas más...

---

¿Quieres que continuemos creando este archivo con todas las clases del motor?  
¿O prefieres empezar ya con el primer tutorial: **“Introducción a Godot – Instalación y Configuración”**?

Dime qué prefieres y seguimos construyendo esta gran base de conocimiento para la comunidad. 💪🧡🚀
