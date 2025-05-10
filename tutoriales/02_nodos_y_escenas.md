---

# 🧱 Tutorial 02 – Introducción a los Nodos y Escenas en Godot

## 🕒 Duración estimada: 25 minutos  
## 📌 Objetivo: Entender qué son los nodos y las escenas, y cómo estructurar tu primer juego  
## 🧰 Herramientas: Godot 4.4.1, GDScript  
## 🧑‍💻 Contenido:

1. ¿Qué es un Nodo?  
2. ¿Qué es una Escena?  
3. Jerarquía de nodos – Padre e hijo  
4. Cómo construir tu primera escena (personaje + movimiento)  
5. Dónde guardar tus archivos  
6. Cómo navegar por la jerarquía de nodos  

---

## 1. ¿Qué es un Nodo?

En Godot, todo está hecho de **nodos**.  
Un nodo puede representar casi cualquier cosa:
- Un personaje
- Una cámara
- Una imagen
- Un botón
- Un temporizador
- Efectos de sonido
- Y mucho más...

Los nodos pueden tener hijos.  
Y juntos forman una **escena**.

📌 **Ejemplo:**  
Piensa en un coche:
- El coche es un nodo.
- Sus ruedas, motor y luces también lo son, pero están **dentro del coche** → son sus hijos.

---

## 2. ¿Qué es una Escena?

Una **escena** es una colección de nodos organizados en una jerarquía.  
Puedes pensar en ellas como **objetos reutilizables**.

### Ejemplos:
- Un enemigo (con su propio comportamiento)
- Un botón del menú
- El jugador (con sus habilidades)
- Un nivel completo

Las escenas se guardan con extensión `.tscn` o `.scn`.

---

## 3. Jerarquía de Nodos – Padre e Hijo

Imagina una familia:
- El padre es el nodo raíz.
- Los hijos son los nodos dentro de él.

Si mueves al padre, todos los hijos se mueven contigo.  
Es una forma poderosa de organizar tu juego.

### Ejemplo Práctico:
```text
Node2D (raíz)
├── Sprite2D (imagen del personaje)
├── CollisionShape2D (detecta golpes)
└── Area2D (detecta cuando algo entra/sale)
```

---

## 4. Cómo Construir tu Primera Escena

### Paso 1: Crea una nueva escena
1. Haz clic en “+” arriba a la izquierda
2. Selecciona `Node2D` como nodo raíz
3. Guárdala como `Personaje.tscn`

### Paso 2: Añade un Sprite
1. Haz clic derecho sobre `Node2D`
2. Añade un nuevo nodo → `Sprite2D`
3. En el Inspector, carga una imagen (si no tienes, usa un color temporal)

### Paso 3: Añade movimiento
1. Haz clic derecho sobre `Node2D` → añade `Script` → crea un nuevo script (`Personaje.gd`)
2. Escribe este código básico:

```gdscript
extends Node2D

@export var velocidad = 200

func _process(delta):
    var movimiento = Vector2.ZERO
    
    if Input.is_action_pressed("ui_right"):
        movimiento.x += 1
    if Input.is_action_pressed("ui_left"):
        movimiento.x -= 1
    if Input.is_action_pressed("ui_down"):
        movimiento.y += 1
    if Input.is_action_pressed("ui_up"):
        movimiento.y -= 1

    position += movimiento.normalized() * velocidad * delta
```

3. Asigna el script al nodo raíz

---

## 5. Dónde Guardar Tus Archivos

Organiza tu carpeta así:

```
res://
├── escenas/
│   └── Personaje.tscn
├── scripts/
│   └── Personaje.gd
└── assets/
    └── personaje.png
```

---

## 6. Cómo Navegar por la Jerarquía de Nodos

La ventana de **Escena** (normalmente a la izquierda) muestra toda tu estructura.

Haz doble clic en cualquier nodo para seleccionarlo.  
Usa el botón **“Instance”** (+) para agregar escenas previamente guardadas.

---

## 📝 Notas Finales

- Si ves demasiadas opciones, enfócate solo en lo que necesitas ahora.
- No uses demasiadas funciones avanzadas todavía. Empieza simple.
- Puedes revisar el glosario para entender mejor palabras como "hijo", "padre", "escena".

---

## 🚀 Próximo Tutorial

👉 [Tutorial 03 – Cómo Mover un Personaje en 2D](../tutoriales/03_mover_personaje_2d.md)

---
