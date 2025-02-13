# DiscreteMathCodes
Python Scripts for  implementing Discrete Math examples
Aquí tienes la documentación en formato Markdown para incluir en tu repositorio de GitHub:  

---

# Matriz de Adyacencia en Python

Este repositorio contiene una implementación en Python para generar y visualizar una matriz de adyacencia a partir de un conjunto de nodos y sus relaciones.

# Descripción

El código permite representar grafos dirigidos mediante una matriz de adyacencia, útil para modelar conexiones entre elementos. Este repositorio contiene un script en Python para generar y visualizar una matriz de adyacencia a partir de un conjunto de elementos y sus relaciones. La matriz de adyacencia es una representación matricial de un grafo dirigido, donde los nodos son los elementos del conjunto y las aristas representan las relaciones entre ellos.

## Estructura del Código

El código se compone de las siguientes funciones:

### 1. `crear_matriz_adyacencia(conjunto, relaciones)`

#### Descripción
Esta función genera una matriz de adyacencia a partir de un conjunto de nodos y una lista de relaciones.

#### Parámetros
- `conjunto` (list): Lista de nodos del grafo.
- `relaciones` (list): Lista de pares ordenados que representan las aristas entre los nodos.

#### Retorno
- `matriz` (list de listas): Matriz de adyacencia representando las conexiones entre los nodos.

#### Implementación
La función:
1. Crea un diccionario que asigna un índice a cada nodo del conjunto.
2. Inicializa una matriz cuadrada con ceros.
3. Recorre la lista de relaciones y asigna un valor de `1` en la matriz para indicar la conexión entre nodos.

### 2. `mostrar_matriz(matriz)`

#### Descripción
Esta función imprime en la consola la matriz de adyacencia de manera legible.

#### Parámetros
- `matriz` (list de listas): Matriz de adyacencia a imprimir.

#### Implementación
La función recorre la matriz e imprime cada fila separando los valores con espacios.

## Ejemplo de Uso

```python
# Definición del conjunto de nodos y relaciones\conjunto = ['BJX', 'MEX', 'LAX']
relaciones = [('BJX', 'MEX'), ('MEX', 'LAX'), ('BJX', 'LAX')]

# Crear la matriz de adyacencia
matriz_adyacencia = crear_matriz_adyacencia(conjunto, relaciones)

# Mostrar la matriz
print("Matriz de Adyacencia:")
mostrar_matriz(matriz_adyacencia)
```

### Salida esperada
```
Matriz de Adyacencia:
0 1 1
0 0 1
0 0 0
```

## Aplicaciones
- Representación de grafos dirigidos en teoría de grafos.
- Modelado de redes y conexiones entre nodos.
- Análisis de rutas en sistemas de transporte.





# Uso

1. **Definir los nodos** en la lista `conjunto`.
2. **Especificar las relaciones** en la lista de tuplas `relaciones`.
3. **Ejecutar el código** para obtener y mostrar la matriz de adyacencia.

## Código

```python
# Función para crear la matriz de adyacencia
def crear_matriz_adyacencia(conjunto, relaciones):
    """
    Crea una matriz de adyacencia para un conjunto de elementos y sus relaciones.

    :param conjunto: lista de elementos del conjunto (nodos)
    :param relaciones: lista de pares ordenados (aristas)
    :return: matriz de adyacencia
    """
    indices = {elemento: i for i, elemento in enumerate(conjunto)}
    matriz = [[0] * len(conjunto) for _ in range(len(conjunto))]

    for (origen, destino) in relaciones:
        matriz[indices[origen]][indices[destino]] = 1

    return matriz

# Función para mostrar la matriz de adyacencia
def mostrar_matriz(matriz):
    """
    Muestra una matriz de adyacencia de forma legible.

    :param matriz: matriz de adyacencia
    """
    for fila in matriz:
        print(" ".join(map(str, fila)))

# Ejemplo de uso
conjunto = ['BJX', 'MEX', 'LAX']
relaciones = [('BJX', 'MEX'), ('MEX', 'LAX'), ('BJX', 'LAX')]

matriz_adyacencia = crear_matriz_adyacencia(conjunto, relaciones)

print("Matriz de Adyacencia:")
mostrar_matriz(matriz_adyacencia)
```

## Salida esperada

```
Matriz de Adyacencia:
0 1 1
0 0 1
0 0 0
```

## Licencia

Este código está disponible bajo la licencia MIT.
