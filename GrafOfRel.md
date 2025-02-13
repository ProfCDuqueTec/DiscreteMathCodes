# Documentación del Proyecto: Grafo Dirigido con NetworkX

## Descripción
Este proyecto proporciona una implementación en Python para la creación y visualización de un grafo dirigido utilizando la biblioteca **NetworkX** y **Matplotlib**. Se define un conjunto de funciones para construir el grafo a partir de una lista de pares ordenados y representarlo gráficamente.

## Requisitos
Para ejecutar este proyecto, es necesario instalar las siguientes bibliotecas:

```bash
pip install networkx matplotlib
```

## Estructura del Código

El proyecto consta de las siguientes funciones:

### 1. `crear_grafo_dirigido(relacion)`
Crea un grafo dirigido a partir de una lista de pares ordenados.

**Parámetros:**
- `relacion` (list of tuples): Lista de tuplas que representan las conexiones entre nodos.

**Retorno:**
- `G` (DiGraph): Objeto de tipo `DiGraph` de NetworkX.

### 2. `dibujar_grafo(G)`
Dibuja un grafo dirigido utilizando **Matplotlib**.

**Parámetros:**
- `G` (DiGraph): Grafo dirigido de NetworkX.

**Salida:**
- Muestra una visualización del grafo con una distribución circular de nodos.

### 3. `test_grafo()`
Función de prueba que crea y visualiza un grafo con una relación de ejemplo.

**Ejemplo de Relación:**
- `('BJX', 'MEX')`
- `('MEX', 'LAX')`
- `('BJX', 'LAX')`

### 4. Bloque Principal `if __name__ == "__main__"`
Ejecuta la función `test_grafo()` cuando el script se ejecuta directamente.

## Uso
Para ejecutar el programa, simplemente corre el siguiente comando en la terminal:

```bash
python nombre_del_script.py
```

Esto generará una visualización del grafo dirigido basado en la relación definida en `test_grafo()`.

## Ejemplo de Uso
```python
relacion = [('A', 'B'), ('B', 'C'), ('C', 'D'), ('A', 'D')]
G = crear_grafo_dirigido(relacion)
dibujar_grafo(G)
```
## Código completo
```python
import networkx as nx
import matplotlib.pyplot as plt

def crear_grafo_dirigido(relacion):
    """
    Crea un grafo dirigido a partir de una lista de pares ordenados.

    :param relacion: Lista de tuplas representando los pares ordenados de la relación.
    :return: Objeto Graph de NetworkX.
    """
    G = nx.DiGraph()  # Crear un grafo dirigido
    G.add_edges_from(relacion)  # Agregar los pares ordenados como aristas
    return G

def dibujar_grafo(G):
    """
    Dibuja un grafo dirigido con NetworkX y Matplotlib.

    :param G: Grafo dirigido de NetworkX.
    """
    plt.figure(figsize=(5, 5))
    pos = nx.circular_layout(G)  # Distribución de nodos en forma circular
    nx.draw(G, pos, with_labels=True, node_color="lightblue", edge_color="black", arrowsize=20)
    plt.title("Diagrama del Grafo Dirigido")
    plt.show()

def test_grafo():
    """
    Función de prueba que crea y visualiza el grafo para la relación del ejemplo.
    """
    relacion_ejemplo = [('BJX', 'MEX'), ('MEX', 'LAX'), ('BJX', 'LAX')]  # Relación de la diapositiva 4
    G = crear_grafo_dirigido(relacion_ejemplo)
    dibujar_grafo(G)

# Ejecutar la prueba
if __name__ == "__main__":
    test_grafo()

```

## Autores
- **[Tu Nombre]** - Desarrollador

## Licencia
Este proyecto está bajo la licencia MIT - consulta el archivo [LICENSE](LICENSE) para más detalles.

