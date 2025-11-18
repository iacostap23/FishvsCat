#  Fish vs Cat

## 🎥 Video Demostración

[![Ver demostración en YouTube](https://img.youtube.com/vi/ImzMFrrn1EQ/0.jpg)](https://www.youtube.com/watch?v=ImzMFrrn1EQ)


## Descripción General

El juego consiste en un enfrentamiento **1 vs 1**, donde un pez
controlado por el jugador debe disparar contra un gato que se mueve
automáticamente. Ambos personajes cuentan con **tres vidas**, y el
objetivo es reducir las vidas del enemigo a cero.

------------------------------------------------------------------------

##  Objetivo del Juego

-   **El pez** (jugador) debe **acertar 3 disparos** al gato para
    ganar.\
-   **El gato** se mueve automáticamente y no dispara, pero si el pez
    falla un disparo (la bala sale de pantalla), **el pez pierde una
    vida**.\
-   Gana quien **deje al enemigo sin vidas**.

------------------------------------------------------------------------

##  Mecánicas Principales

###  El Pez (Jugador)

-   **↑ (131):** subir\
-   **↓ (133):** bajar\
-   **← (130):** moverse a la izquierda (hasta la barrera)\
-   **→ (132):** moverse a la derecha\
-   Dispara con **ESPACIO (32)**\
-   La bala:
    -   Va hacia la **izquierda**
    -   Si golpea al gato → el gato pierde una vida
    -   Si falla → el pez pierde una vida

------------------------------------------------------------------------

###  El Gato (CPU / Automático)

-   Se mueve sin intervención del jugador.\
-   Movimiento vertical:
    -   Sube hasta el extremo superior\
    -   Baja hasta el extremo inferior\
    -   Repite\
-   Pierde una vida si la bala del pez le impacta.

------------------------------------------------------------------------

##  Barrera Central

-   Dibujo vertical en la mitad de la pantalla.\
-   El pez **NO puede cruzarla**, manteniéndose en su zona.\
-   Las balas **SÍ la cruzan**.\
-   Garantiza equilibrio y evita colisiones físicas entre jugadores.

------------------------------------------------------------------------

##  Sistema de Vidas

Ambos personajes comienzan con **3 vidas**.\
Estas se representan con pequeños rectángulos a modo de corazones.

  - Pez impacta al gato:  **Gato -1 vida**
  - Bala del pez sale de pantalla:  **Pez -1 vida**
  - Gato llega a 0 vidas:  **FISH WINS**
  - Pez llega a 0 vidas:  **CAT WINS**

------------------------------------------------------------------------

##  Arquitectura del Juego

### 1. `Fish.jack`

Dibuja el sprite del pez mediante escritura directa en memoria.

### 2. `Cat.jack`

Dibuja el sprite del gato.

### 3. `Draw1.jack`

Controla la bala del pez: - posición\
- movimiento\
- detección de límites\
- getters

### 4. `Main.jack`

Núcleo general: - Movimiento del pez\
- IA del gato\
- Sistema de disparos\
- Sistema de vidas\
- Colisiones\
- Barrera\
- Renderizado total\
- Secuencia de victoria/derrota

------------------------------------------------------------------------

##  ¿Cómo Ejecutarlo?

1. Abrir la carpeta del proyecto en **JackCompiler**. 
2. En la interfaz del JackCompiler, cargar la carpeta `JUEGO_FINAL` .
3. Verificar que se listan los archivos `Main.jack`, `Fish.jack`, `Cat.jack`, `Draw1.jack`.
4. Hacer clic en **Compile** para generar los archivos `.vm`.
5. Luego hacer clic en **Run**: esto abre automáticamente el **VMEmulator** con el programa cargado.
6. En el **VMEmulator**, mover el control deslizante de velocidad hacia **Fast** para que el juego corra fluido.
7. En la parte inferior del VMEmulator, hacer clic en **Enable Keyboard** para activar el teclado.
8. Finalmente, presionar **Run** y listo, ¡a jugar! 



