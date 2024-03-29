# Reto-3-Flow-en-mis-diagramas

Repositorio en donde se publica la evidencia de que mi persona, Lucas García, cumplió con el reto asignado.

- Y a diferencia del anterior, esta vez no tuve mayores dificultades :) .

## Logo de mi equipo(infaltable):
***

 [![Logo-equipo.webp](https://i.postimg.cc/Z5BYw1Tx/Logo-equipo.webp)](https://postimg.cc/9D2jMgwD)


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

### En Pseudocódigo:

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

  Sino si n == 2 entonces;
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
    Cantidad_de_numeros_primos_hasta_n := l primos + 1
fin
```
## Algoritmo para hallar la raíz cuadrada de un número:
***
### Diagrama de Flow(Flujo):
```mermaid
graph TD;
    A(Inicio);
A -->B[número x entero positivo];
B -->C[a = 9];
C -->E[x se divide en conjuntos de 2 <br> cifras de derecha a izquierda];
E -->F[el primer conjunto de cifras de izquierda a derecha = q];
F -->G{a^2 menor que q ?};
G -->|Sí|H[la primera cifra <br> de la raíz es a];
G -->|No|I[a = a - 1];
I -->G;
H -->J[q - a^2 = r];
J -->K{Faltan otras cifras ?};
K -->|No|L["La raíz más <br> cercana es  √(a^2)"];
K -->|Sí|M[a r se le añaden <br> otro conjunto de cifras = u];
M -->N[n = 9];
N -->O{"u menor a <br>(a*2 seguido de n) * n = h ?"};
O -->|Sí|P[n = n - 1];
P -->O;
O -->|No|Q[u - h = r];
Q -->R{Faltan más cifras?};
R -->|Sí|M;
R -->|No|T["La raíz más próxima es <br> √(a seguido de todos los n)"];
T -->S(Fin);
```

### En Pseudocódigo:
```pseudocode
[variables]
n : entero
x : entero
u : entero
r : entero
h : entero
a : entero

inicio
 a := 9
 q := último conjunto de parejas de cifras de x de derecha a izquierda

 Mientras (q <= a^2) hacer
  a := a - 1
 Fin mientras
 r := q - a^2

 Si x > 99 entonces
  Mientras (x tenga más conjuntos de cifras) hacer
   u:= r seguido de 2 cifras faltantes
   n := 9
   h := (a*2 seguido de n) * n
   Mientras (u < h) hacer
    n := n - 1
   Fin mientras
   r := u - h
  Fin mientras 
  escribir("La raíz más próxima es √(a seguido de todos los n)")

 sino
  escribir("La raíz más cercana es √(a^2)")

fin
```
