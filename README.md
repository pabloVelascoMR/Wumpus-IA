#  Wumpus con IA (Minimax con poda Alfa-Beta)

Este proyecto ha sido desarrollado en el marco de la asignatura **Sistemas Inteligentes (Curso 2024-2025)** en la **Universidad de Burgos (UBU)**.

El objetivo del trabajo es implementar una **versión automática del clásico “Juego del Wumpus”**, donde un agente inteligente toma decisiones utilizando el algoritmo **Minimax con poda Alfa-Beta**.  
El proyecto está completamente desarrollado en **Python**, en formato **Jupyter Notebook**, e incluye generación del tablero, mecánicas del juego y ejecución de la IA.

---

## Descripción del Juego Wumpus

El Wumpus es un juego clásico en el que un agente debe moverse por un tablero lleno de peligros, evitando trampas y tratando de sobrevivir.

El tablero se genera mediante la clase `Tablerowumpus`, que incluye automáticamente:

- 🕳 Pozos  
- 💨 Brisas (indican pozos cercanos)  
- 👹 Wumpus  
- 🤢 Hedor (indica el Wumpus cercano)  
- 🤠 Jugador / Agente  
- 💎 Recompensas opcionales  

En esta versión del proyecto:
 **La IA controla todos los movimientos**, calculando la mejor decisión con **Minimax + poda Alfa-Beta**.

## Ambientación del Juego

El proyecto está ambientado en el **Oeste americano**, donde el jugador controla a un **forajido** que intenta recuperar un **cofre de oro** mientras evita múltiples peligros del desierto.  

En este mundo:

- 🤠 **El agente** es un sherif
- 💰 **El objetivo** es llegar al oro
- 🕳️ **Las minas** (“hoyos”) son trampas mortales en movimiento
- 👹 **El Wumpus** es el vandido que vigila la zona
- 💨 **Brisas y hedor** sirven como señales de peligro

Todo ocurre en un tablero cuadriculado donde el agente debe planificar cada movimiento.

---

##  Objetivo del Agente

El agente puede ganar de dos maneras:

- **Llegando al oro**, evitando todos los peligros  
- **Eliminando al Wumpus con un disparo**, sin necesidad de alcanzar el oro

---

##  Funcionamiento de las Minas (Hoyos)

Las minas **no son estáticas**: se **mueven automáticamente** cada vez que el agente da un paso.

- Se desplazan únicamente por **sus mismas filas y columnas**  
- Cada turno del agente → una de las minas se recoloca aleatoriamente
- El entorno es dinámico y muy peligroso

### El agente muere si:
- ❌ cae dentro de una mina  
- ❌ las minas lo rodean sin salida  
- ❌ una mina lo encierra junto al Wumpus  

---

## Sistema de Disparo del Forajido

El forajido puede disparar **una vez** cuando ha realizado **3 movimientos**.

### Reglas del disparo:
- El disparo se lanza de forma **aleatoria**
- Puede ir en un eje **vertical** o **horizontal**
- Recorre toda la línea hasta el borde del tablero

### Victoria instantánea:
Si el disparo **impacta al Wumpus**, el agente **gana automáticamente**, sin necesidad de llegar al oro.

---

## El Wumpus

El Wumpus permanece en una casilla fija del tablero.  
Su presencia genera un **hedor** que advierte al agente de su proximidad.

- Entrar en su casilla → **muerte instantánea**
- Solo puede ser derrotado por el **disparo aleatorio**
- Si el agente llega al oro sin enfrentarlo, también gana

---

## Resumen General de Mecánicas

1. El agente-sherif se mueve por el tablero buscando el **cofre de oro**.  
2. Las **minas se mueven en cada turno** en sus filas y columnas.  
3. Tras **3 movimientos**, el agente puede **realizar un disparo aleatorio**.  
4. Si el disparo alcanza al **Wumpus**, el agente gana automáticamente.  
5. El agente muere si:
   - ❌ cae en una mina,  
   - ❌ queda rodeado por ellas,  
   - ❌ o entra en la casilla del Wumpus.  
6. Puede ganar:
   - ✔️ alcanzando el oro  
   - ✔️ eliminando al Wumpus con un disparo  

---

##  Algoritmo Minimax (con poda Alfa-Beta)

El agente analiza todos los movimientos posibles usando una búsqueda adversarial:

-  Generación de estados sucesores  
-  Función `tablerosSiguientesMAX()` (acciones del agente)  
-  Función `tablerosSiguientesMIN()` (acciones del entorno)  
-  Evaluación heurística del tablero  
-  Exploración hasta una profundidad límite  
-  Reducción del árbol de búsqueda mediante alfa-beta  
-  Ejecución del algoritmo con `iniciarMinimax()`  

### Rol de cada jugador en Minimax

- **MAX** → El agente (busca sobrevivir y maximizar su puntuación)  
- **MIN** → El entorno (modela los peores escenarios posibles)  

---

## 📘 Estructura del Notebook

El archivo principal del proyecto Incluye:

1. Encabezado y autor  
2. Importación de librerías  
3. Implementación de la clase `Tablerowumpus`  
4. Métodos de generación de movimientos  
5. Algoritmo Minimax + poda Alfa-Beta  
6. Ejecución automática del agente  
7. Visualización del tablero y resultados


---

## ⚙️ Requisitos

Para ejecutar este proyecto necesitas:

- **Python 3.10 o superior**
- **Jupyter Notebook**
- Las siguientes librerías:
  - `copy`
  - `typing`
  - `numpy`
  - `matplotlib`
  - `os`
  - `time`

Instalar Jupyter si no lo tienes:

pip install notebook


---

## Cómo Ejecutar el Proyecto

**Descarga el repositorio desde GitHub** (botón **Code → Download ZIP**, o usando `git clone`):


git clone https://github.com/tuusuario/turepositorio.git
Asegúrate de que las carpetas imagenes y checkpoints están colocadas junto al notebook.

Abre el notebook:
jupyter notebook JuegoWumpusVAutomaticaI_PABLO_VELASCO.ipynb
Ejecuta las celdas en orden (Shift + Enter).

---

# Licencia

Proyecto licenciado bajo la licencia MIT. Para más información, consulta el archivo: LICENSE


