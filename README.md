# Reto-3-Flow-en-mis-diagramas

Repositorio en donde se publica la evidencia de que mi persona, Lucas García, cumplió con el reto asignado.

- Y a diferencia del anterior, esta vez no tuve mayores dificultades :) .

## Logo de mi equipo(infaltable):
***

## Algoritmo para obtener números primos hasta N
***
### Diagrama de Flow(Flujo):
```mermaid
 graph TD;
 A(Inicio);
    A -->B[número n entero positivo];
    B -->C{n menor a 3?};
    C -->|No| G[Lista de 3 hasta n];
    C -->|Sí|D{n igual a 0 o a 1 ?};
    D -->|Sí| E[no hay ningún número primo hasta n];
    D -->|No| F[solo hay un número primo hasta n];
    G-->H[l=3];
    H-->I[i=2];
    I-->J{residuo de l/i es cero?};

    J-->|No|K{i>l^0.5?};
    K-->|No|L[i=i+1];
    K-->|Sí|M[l es primo];
    M-->Y;
    L-->J;

    J-->|Sí|Z[l no es primo];
    Z-->Y[l=l+1];

    Y-->X{l>n?};
    X-->|No|I;
    X-->|Sí|W[Cantidad de primos hasta n = número de l primos + 1];
    W-->V(Fin);
```

### En Pseudocódigo

```pseudocode
[variables]
n : entero
i : entero
l : entero

inicio
  l := 3
  i := 2

  Si n <= 1 entonces
    escribir("no hay números primos hasta n")

  Sino si n == 2 entonces
    escribir("solo hay 1 número primo hasta n")

  sino
    Mientras (l <= n) hacer
      Mientras (i <= l^0.5) hacer
        Si modulo(l,i) == 0 entonces
          escribir("l no es primo")
        sino
          i := i + 1
      Fin mientras
      Si i > l^0.5 entonces 
        escribir("l es primo")
      l := l + 1
    Fin mientras
    Cantidad_de_números_primos_hasta_n := l primos + 1
fin
```
