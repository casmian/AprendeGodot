

> Este documento sirve como guía de seguimiento del desarrollo de **AudioForge**, organizado por fases. Puedes ir marcando las tareas completadas y llevando un registro claro del progreso.

---

## 🔹 Fase 0: Cimientos – Aprendizaje y Configuración

### ✅ Completadas:
- [x] Instalación de Godot Engine (versión 4.x)
- [x] Exploración básica de la interfaz de Godot (Editor, Nodos, Inspector, FileSystem, Scripts)
- [x] Aprendizaje básico de GDScript (variables, tipos, operadores, funciones, señales)
- [x] Estudio teórico de audio digital (onda, frecuencia, muestreo, envolvente ADSR)

### 🟡 En Progreso:
- [ ] Práctica inicial con nodos básicos (Node2D, Control, etc.)
- [ ] Ejercicios de programación en GDScript
- [ ] Resumen escrito o diagrama de conceptos aprendidos

### ⏳ Pendientes:
- [ ] Organización del repositorio inicial
- [ ] Creación del primer commit con estructura base del proyecto

---

## 🔹 Fase 1: Núcleo de Generación de SFX – El Primer Sonido

### ✅ Completadas:

### 🟡 En Progreso:

### ⏳ Pendientes:
- [ ] Implementar `AudioStreamGenerator`
- [ ] Generar onda sinusoidal básica
- [ ] Agregar soporte para otras formas de onda (cuadrada, triangular, ruido blanco)
- [ ] Implementar una envolvente ADSR funcional
- [ ] Permitir ajuste de duración, frecuencia y amplitud desde código

---

## 🔹 Fase 2: Interfaz de Usuario (UI) Inicial y Control

### ✅ Completadas:

### 🟡 En Progreso:

### ⏳ Pendientes:
- [ ] Diseñar UI básica con nodos Control (Buttons, Sliders, Labels)
- [ ] Conectar los controles a la lógica interna de generación de sonido
- [ ] Implementar botones de reproducción y detención
- [ ] Visualización simple de forma de onda/envolvente (opcional)

---

## 🔹 Fase 3: SFX Mejorados, Vocalizaciones y Música Inicial

### ✅ Completadas:

### 🟡 En Progreso:

### ⏳ Pendientes:
- [ ] Implementar efectos simples: filtro paso bajo/alto, delay, reverb básica
- [ ] Añadir modulación con LFO (vibrato/trémolo)
- [ ] Generar ejemplos de SFX predefinidos (pasos, disparos, saltos)
- [ ] Desarrollar vocalizaciones simples (ruido filtrado, formantes simulados)
- [ ] Crear secuenciador musical básico
- [ ] Limitar notas a escalas definidas y generar acordes sencillos

---

## 🔹 Fase 4: Gestión de Sonidos – Presets, Exportación y Mejoras UI

### ✅ Completadas:

### 🟡 En Progreso:

### ⏳ Pendientes:
- [ ] Crear sistema de presets (estructura de datos + guardado/carga en JSON/.tres)
- [ ] Implementar exportación de sonido generado como .wav/.ogg
- [ ] Diseñar e integrar mini-reproductor dentro de la UI
- [ ] Agregar historial de sonidos generados
- [ ] Mejorar organización visual y usabilidad de la interfaz

---

## 🔹 Fase 5: Funcionalidades Avanzadas y Música Multi-Estilo/Multi-Pista

### ✅ Completadas:

### 🟡 En Progreso:

### ⏳ Pendientes:
- [ ] Implementar modo “Randomizer” para presets aleatorios
- [ ] Diseñar panel de selección de emociones/ambientes
- [ ] Definir parámetros para estilos musicales (Chiptune, Lo-Fi, Ambiental, etc.)
- [ ] Soportar múltiples pistas instrumentales (melodía, bajo, percusión, pads)
- [ ] Sincronizar y mezclar pistas musicales
- [ ] Refinar editor de parámetros en tiempo real

---

## 🔹 Fase 6: Empaquetado, Distribución y Usabilidad

### ✅ Completadas:

### 🟡 En Progreso:

### ⏳ Pendientes:
- [ ] Crear plugin funcional (`EditorPlugin`)
- [ ] Diseñar docks personalizados para el editor de Godot
- [ ] Exportar como aplicación standalone (Windows, Linux, macOS)
- [ ] Integrar tutoriales interactivos dentro de la herramienta
- [ ] Escribir documentación básica de usuario final

---

## 🔹 Fase 7: Comunidad y Expansión Futura Avanzada

### ✅ Completadas:

### 🟡 En Progreso:

### ⏳ Pendientes:
- [ ] Publicar en GitHub / Itch.io con licencia abierta
- [ ] Habilitar base de datos de presets compartidos
- [ ] Implementar generación procedural de ambientes compuestos
- [ ] Crear sistema de morphing entre presets
- [ ] Evaluar soporte opcional de IA (interpretación de prompts descriptivos)
- [ ] Añadir galería online, favoritos y temas de interfaz
- [ ] Explorar integración avanzada con juegos (detección de estado)
- [ ] Implementar síntesis granular, FM simple o aditiva básica
- [ ] Agregar visualizadores avanzados (osciloscopio, analizador espectral)
- [ ] Herramientas de humanización de música/SFX
- [ ] Soporte para entrada MIDI
- [ ] Opciones de personalización visual de la interfaz

---

## 🧩 Componentes Adicionales (Opcional pero Recomendados)

| Tarea | Estado |
|------|--------|
| Sistema de traducción (multi-idioma) | ⏳ Pendiente |
| Modo oscuro/claro en la interfaz | ⏳ Pendiente |
| Ayuda contextual sobre parámetros | ⏳ Pendiente |
| Teclas de acceso rápido | ⏳ Pendiente |
| Soporte para dispositivos móviles | ⏳ Pendiente |

---

