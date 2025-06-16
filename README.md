# PROYECTO PYXEL (Laberinto) 🧩
### Introducción

Para nuestro proyecto escogimos la alternativa cuatro, que es de libre eleccion. Nuestra propuesta es realizar un laberinto que se basa en el movimiento de las teclas W,A,S,D por medio de la libreria **msvcrt** junto a un sistema de vidas, trampas y opcion para escoger distintos tipos de laberinto y sus dificultades.

### Objetivo del Juego

El jugador debe guiar un personaje desde la entrada del laberinto hasta la salida, evitando muros y trampas, y superando varios niveles. Tiene vidas limitadas, que se reducen al caer en trampas. El juego se controla con el teclado (W, A, S, D).


## Estructura general del juego 🧱
Menú principal (en consola):

Iniciar partida.

Elegir laberinto manualmente desde un banco.

Salir.

Inicio del nivel:

Se carga el laberinto desde un archivo o estructura (texto plano con símbolos).

Se muestra en pantalla (consola) con el jugador en la posición inicial.

Movimiento del jugador:

Con teclas W (arriba), A (izquierda), S (abajo), D (derecha).

Se verifica si el movimiento es válido:

✅ Espacio libre → se mueve.

❌ Muro → no se mueve.

☠️ Trampa → pierde una vida.

🚪 Salida → avanza al siguiente nivel.

Sistema de vidas:

El jugador inicia con X vidas.

Si pisa una trampa, pierde una vida.

Si llega a 0 vidas, fin del juego.

Cambio de nivel:

Al llegar a la salida, se carga el siguiente laberinto automáticamente.

Puede haber 2 o más niveles predefinidos.

Fin del juego:

Al completar todos los laberintos → mensaje de victoria.

Al perder todas las vidas → mensaje de derrota.
## DIAGRAMA DE FLUJO

``` mermaid
---
config:
  theme: redux
---

flowchart TD
    A(["Inicio"]) --> B[Pantalla principal]
    B --> C{"¿Desea ver las instrucciones del juego?"}
    C -- Sí --> D[/Mostrar instrucciones/]
    C -- No --> F
    D --> F{"Escoga una dificultad"}
    F -- Principiante --> G[/Mostrar tablero 8 x 8 con 10 minas/]
    F -- Intermedio --> H[/Mostrar tablero 16 x 16 con 40 minas/]
    F -- Experto --> I[/Mostrar tablero 16 x 36 con 99 minas/]
    G --> J[seleccione una casilla]
    H --> J
    I --> J
    J --> K{"¿La casilla tiene mina?"}
    K -- Sí --> L[/Mostrar mensaje de juego perdido/]
    L --> Q
    K -- No --> M[/Mostrar número de minas cercanas/]
    M --> N{"¿Ha descubierto todas las casillas?"}
    N -- No -->J
    N -- Sí --> O[/Mostrar mensaje de juego ganado/]
    O --> Q{"¿Desea volver a jugar?"}
    Q -- Sí -->F
    Q -- No --> P(["Fin"])
```
# cronograma

| **Semana** | **Fecha**               | **Tema**                                                                                                  |
| ---------- | ----------------------- | --------------------------------------------------------------------------------------------------------- |
| Semana 10  | 09/06/2025 - 15/06/2025 | **Diseño del preproyecto**<br>definición del problema, algoritmo incial, diagrama de flujo, funcionamiento o reglas. |
| Semana 11  | 16/06/2025 - 22/06/2025 | **Preparación del entorno y estructura base.**<br> - Crear estructura de carpetas y archivos del proyecto.<br>- funciones base: renderizado del laberinto, entrada de teclado.<br> - bucle principal|
| Semana 12  | 23/06/2025 - 29/06/2025 | **Movimiento del jugador y detección de colisiones**<br>- Implementar controles de movimiento (WASD) y límites del mapa<br>- manejar colisiones con muros y obstáculos<br>- detección de llegada a la meta (salida).                         |
| Semana 13  | 30/06/2025 - 06/07/2025 | **Sistema de vidas, trampas y niveles**       |
| Semana 14  | 07/07/2025 - 13/07/2025 | **Interfaz de menú en consola y banco de laberintos**<br>- Crear menú inicial: iniciar juego, elegir laberinto, salir<br>- Hacer sistema de elección de laberintos desde un banco predefinido.                     |
| Semana 15  | 14/07/2025 - 20/07/2025 | Pulido, pruebas y documentación                 |
| Semana 16  | 21/07/2025 - 27/07/2025 | **Entrega final**<br>- Verificación final: Probar en distintas versiones y revision final. |

## INTEGRANTES
- [Juan Carlos Polania Bolivar](https://github.com/Ciyuang)
- [Erick Llanos Espinel](https://github.com/erickllanos120)
- [fabian Camilo Linares Villalba](https://github.com/campersi93)
