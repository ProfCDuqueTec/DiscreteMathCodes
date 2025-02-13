# Generación y Visualización de Matriz de Adyacencia

# Descripción
Este repositorio contiene un script en Python para generar y visualizar una matriz de adyacencia a partir de dos conjuntos de elementos y una relación entre ellos. La matriz de adyacencia es una representación tabular que indica las conexiones entre los elementos de los dos conjuntos dados.

# Contenido del Código
El código incluye dos funciones principales:

## 1. `generar_matriz_adyacencia(U, P, C)`
Esta función genera una matriz de adyacencia a partir de:
- `U`: Un conjunto de elementos (ej. usuarios o nodos de origen).
- `P`: Un conjunto de elementos (ej. productos o nodos de destino).
- `C`: Un conjunto de pares `(u, p)`, donde `u` pertenece a `U` y `p` pertenece a `P`, indicando que hay una conexión entre ellos.

### Algoritmo:
1. Se asignan índices a los elementos de `U` y `P` para facilitar la representación matricial.
2. Se inicializa una matriz de ceros con dimensiones `len(U) x len(P)`.
3. Se recorre el conjunto `C`, y se actualiza la matriz con `1` en las posiciones correspondientes a las conexiones definidas.
4. Se retorna la matriz generada.

### 2. `mostrar_matriz(matriz, U, P)`
Esta función imprime la matriz de adyacencia en formato tabular para facilitar su lectura.

#### Algoritmo:
1. Imprime una cabecera con los elementos de `P`.
2. Itera sobre las filas de la matriz, imprimiendo los elementos de `U` y sus respectivas conexiones.

## Ejemplo de Uso
### Entrada:
```python
U = ["Alicia", "Bruno", "Carla"]
P = ["Libro", "Laptop", "Teléfono"]
C = {("Alicia", "Laptop"), ("Bruno", "Libro"), ("Carla", "Teléfono"), ("Bruno", "Teléfono")}

# Generar la matriz de adyacencia
matriz = generar_matriz_adyacencia(U, P, C)

# Mostrar la matriz de adyacencia
mostrar_matriz(matriz, U, P)
```

### Salida esperada:
```
         Libro       Laptop     Teléfono    
Alicia       0           1           0    
Bruno        1           0           1    
Carla        0           0           1    
```

# Función para generar la matriz de adyacencia
``` Python
def generar_matriz_adyacencia(U, P, C):
    # Crear un diccionario para mapear los elementos de U y P a índices
    index_U = {elemento: i for i, elemento in enumerate(U)}
    index_P = {elemento: i for i, elemento in enumerate(P)}

    # Crear una matriz de ceros con las dimensiones de U x P
    matriz = [[0 for _ in range(len(P))] for _ in range(len(U))]

    # Llenar la matriz con los valores de la relación C
    for (u, p) in C:
        if u in index_U and p in index_P:
            matriz[index_U[u]][index_P[p]] = 1

    return matriz
```

# Función para mostrar la matriz de adyacencia de manera legible
``` Python
def mostrar_matriz(matriz, U, P):
    # Mostrar las cabeceras de las columnas
    print("    ", end="")
    for p in P:
        print(f"{p:12}", end="")
    print()

    # Mostrar las filas con las cabeceras de las filas (elementos de U)
    for i, fila in enumerate(matriz):
        print(f"{U[i]:<12}", end="")
        for valor in fila:
            print(f"{valor:12}", end="")
        print()
```

# Datos de prueba
U = ["Alicia", "Bruno", "Carla"]
P = ["Libro", "Laptop", "Teléfono"]
C = {("Alicia", "Laptop"), ("Bruno", "Libro"), ("Carla", "Teléfono"), ("Bruno", "Teléfono")}

# Generar la matriz de adyacencia
matriz = generar_matriz_adyacencia(U, P, C)

# Mostrar la matriz de adyacencia
mostrar_matriz(matriz, U, P)

## Código

```python
# Función para generar la matriz de adyacencia dados dos conjuntos y su relación
def generar_matriz_adyacencia(U, P, C):
    # Crear un diccionario para mapear los elementos de U y P a índices
    index_U = {elemento: i for i, elemento in enumerate(U)}
    index_P = {elemento: i for i, elemento in enumerate(P)}

    # Crear una matriz de ceros con las dimensiones de U x P
    matriz = [[0 for _ in range(len(P))] for _ in range(len(U))]

    # Llenar la matriz con los valores de la relación C
    for (u, p) in C:
        if u in index_U and p in index_P:
            matriz[index_U[u]][index_P[p]] = 1

    return matriz

# Función para mostrar la matriz de adyacencia de manera legible
def mostrar_matriz(matriz, U, P):
    # Mostrar las cabeceras de las columnas
    print("    ", end="")
    for p in P:
        print(f"{p:12}", end="")
    print()

    # Mostrar las filas con las cabeceras de las filas (elementos de U)
    for i, fila in enumerate(matriz):
        print(f"{U[i]:<12}", end="")
        for valor in fila:
            print(f"{valor:12}", end="")
        print()

# Datos de prueba
U = ["Alicia", "Bruno", "Carla"]
P = ["Libro", "Laptop", "Teléfono"]
C = {("Alicia", "Laptop"), ("Bruno", "Libro"), ("Carla", "Teléfono"), ("Bruno", "Teléfono")}

# Generar la matriz de adyacencia
matriz = generar_matriz_adyacencia(U, P, C)

# Mostrar la matriz de adyacencia
mostrar_matriz(matriz, U, P)


```

## Aplicaciones
- Representación de relaciones entre usuarios y productos.
- Modelado de grafos bipartitos en sistemas de recomendación.
- Análisis de conexiones entre dos conjuntos de datos.

## Requisitos
- Python 3.x

## Autor
Este código fue desarrollado con fines educativos y de investigación.

## Licencia
MIT License.

