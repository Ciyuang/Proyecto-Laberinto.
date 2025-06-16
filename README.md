# PROYECTO PYXEL (Laberinto) 🧩
### Introducción

Para nuestro proyecto escogimos la alternativa cuatro, que es de libre eleccion. Nuestra propuesta es realizar un laberinto que se basa en el movimiento de las teclas W,A,S,D por medio de la libreria **msvcrt** junto a un sistema de vidas, trampas y opcion para escoger distintos tipos de laberinto y sus dificultades.

### Objetivo 

El jugador debe guiar un personaje desde la entrada del laberinto hasta la salida, evitando muros y trampas, y superando varios niveles. Tiene vidas limitadas, que se reducen al caer en trampas. El juego se controla con el teclado (W, A, S, D).


## Estructura general

1. Menú principal (en consola):
   - Iniciar partida.
   - Elegir laberinto manualmente desde el banco de laberintos.
   - Salir.

2. Inicio del nivel:
   - Se carga el laberinto (texto plano con símbolos).
   - Se muestra en pantalla (consola) con el jugador en la posición inicial.

3. Movimiento del jugador:
   - Con teclas W (arriba), A (izquierda), S (abajo), D (derecha).
   - Se verifica si el movimiento es válido:
     - ✅Espacio libre → se mueve.
     - ❌Muro → no se mueve.
     - ☠️Trampa → pierde una vida.
     - 🚪Salida → avanza al siguiente nivel o escoge otro (regrersa al "menú" para elegir un laberinto).

4. Sistema de vidas:
   - El jugador inicia con X vidas.
   - Si pisa una trampa, pierde una vida.
   - Si llega a 0 vidas, fin del juego.

5. Cambio de nivel:
   - Al llegar a la salida, se carga el siguiente laberinto automáticamente.
   - Puede haber 2 o más niveles predefinidos.

6. Fin del juego:
   - Al completar todos los laberintos → mensaje de victoria.
   - Al perder todas las vidas → mensaje de derrota.
## DIAGRAMA DE FLUJO

``` mermaid
---
config:
  theme: redux
---

flowchart TD
    Start([Inicio del programa])
    ShowMenu[Mostrar menu de niveles (1 al 10)]
    ChooseLevel[Jugador elige nivel]
    Init[Inicializar juego con 3 vidas]
    LoadMaze[Cargar laberinto del nivel elegido]
    ShowMaze[Mostrar laberinto en consola]
    PlayerMove[Esperar movimiento del jugador]
    CheckMove[Verificar casilla destino]
    WallCheck{¿La casilla tiene muro?}
    BlockMove[Movimiento bloqueado, volver a mover]
    BombCheck{¿La casilla  tiene una bomba?}
    LoseLife[Restar 1 vida]
    CheckLives{Vidas > 0}
    GameOver[[Fin del juego - Derrota]]
    WinCheck{ Felicidades, Llegó a la meta}
    EndLevel[[Nivel superado]]
    LoopBack[Actualizar laberinto y repetir]

    Start --> ShowMenu --> ChooseLevel --> Init --> LoadMaze --> ShowMaze --> PlayerMove --> CheckMove
    CheckMove --> WallCheck
    WallCheck -- Si --> BlockMove --> ShowMaze
    WallCheck -- No --> BombCheck
    BombCheck -- Si --> LoseLife --> CheckLives
    CheckLives -- No --> GameOver
    CheckLives -- Si --> ShowMaze

    BombCheck -- No --> WinCheck
    WinCheck -- No --> ShowMaze
    WinCheck -- Si --> EndLevel --> ShowMenu
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
