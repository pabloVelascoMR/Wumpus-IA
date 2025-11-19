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


