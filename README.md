# Tic-Tac-Toe AI (Juego del Gato) 🎮🤖

Un clon moderno y altamente pulido del clásico juego *Tic-Tac-Toe* (Gato) desarrollado en **C++** utilizando la biblioteca **SFML** (Simple and Fast Multimedia Library). El proyecto cuenta con una interfaz gráfica dinámica, un gestor de audio robusto y un sistema de juego contra Inteligencia Artificial con múltiples niveles de dificultad.

---

## ✨ Características Principales

* **Máquina de Estados Sólida:** Transiciones fluidas entre pantallas mediante control de estados (`Menu`, `Game`, `GameOver`, `Settings`, `ModeSelect`, `DifficultySelect`).
* **Modos de Juego:**
    * **1 vs 1:** Modo local clásico para dos jugadores.
    * **vs IA:** Desafía a la computadora con lógica de toma de decisiones modularizada.
* **Dificultad Ajustable:** Tres niveles de juego para la IA (`Fácil`, `Medio` y `Difícil`) que modifican su comportamiento y precisión.
* **UI/UX Pulida:**
    * Fondos con degradados dinámicos calculados en tiempo real.
    * Efectos visuales avanzados (sombras proyectadas en las piezas `X` y `O`).
    * Línea de victoria animada y estilizada con bordes dorados mediante funciones matemáticas (`std::hypot`, `std::atan2`).
    * Botones interactivos con efectos *hover* visuales y sonoros.
* **Gestor de Audio Integrado (`AudioManager`):** * Música de fondo en bucle (`.ogg`).
    * Efectos de sonido independientes (`.wav`) para clics, movimientos, victorias, empates y eventos *hover*.
    * Panel de configuración de audio dedicado para mutear o regular el volumen de la música y los efectos (SFX) por separado.

---

## 🛠️ Stack Tecnológico

* **Lenguaje:** C++17 (o superior)
* **Biblioteca Gráfica y Multimedia:** [SFML 2.6+](https://www.sfml-dev.org/) (Modules: Graphics, Audio, Window, System)
* **Lógica de IA:** Algoritmos de optimización/búsqueda integrados en `IA.hpp`.

---

## 🎮 Controles del Juego

* **Clic Izquierdo:** Interactuar con los menús, seleccionar opciones y colocar tu pieza (`X` o `O`) en el tablero.
* **Clic Derecho:** Regresar instantáneamente al menú principal desde cualquier pantalla secundaria (Ajustes, Selección de Modo, Dificultad).

---

## 💻 Compilación e Instalación

### Prerrequisitos
Asegúrate de tener instalado un compilador de C++ compatible con C++17 (como `GCC`/`MinGW` o `MSVC`) y la biblioteca **SFML** configurada en las variables de entorno de tu sistema o en tu IDE.

### Clonar el Repositorio
`git clone [https://github.com/TU_USUARIO/Tic-Tac-Toe-AI.git](https://github.com/TU_USUARIO/Tic-Tac-Toe-AI.git)
cd Tic-Tac-Toe-AI`

### Compilación desde la Terminal (usando MinGW/GCC)
Asegúrate de enlazar correctamente las dependencias de SFML (graphics, window, audio, system):
  * `g++ -c main.cpp -I"C:\Ruta\A\SFML\include"`
  * `g++ main.o -o juego_gato -L"C:\Ruta\A\SFML\lib" -lsfml-graphics -lsfml-window -lsfml-audio -lsfml-system`


## 📋 Nota sobre Recursos (Assets)
El juego busca los archivos de audio en las siguientes rutas relativas por defecto:
  * `sounds/background.ogg`
  * `sounds/click.wav, sounds/move.wav, sounds/win.wav, sounds/draw.wav, sounds/hover.wav`
    
Asegúrate de que la carpeta `sounds/` esté en el mismo directorio que tu ejecutable final para evitar advertencias en la consola.

## 📐 Detalles de Arquitectura Técnica
El código base demuestra buenas prácticas en desarrollo de videojuegos nativos:

  * Desacoplamiento de Audio: El uso de `sf::SoundBuffer` y `sf::Sound` por separado evita la sobrecarga de memoria al reutilizar buffers de audio para sonidos repetitivos (como el hover o el move).
  * Lógica Vectorial: El cálculo de la rotación y longitud de la línea de victoria se realiza dinámicamente usando trigonometría pura basándose en la resolución fija de la ventana ($700 \times 700$ píxeles).
