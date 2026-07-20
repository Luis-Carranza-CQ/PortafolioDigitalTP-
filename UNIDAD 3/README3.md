<a href="../UNIDAD%202/README2.md"><img src="https://img.shields.io/badge/%E2%86%90%20Unidad%202-darkgreen?style=for-the-badge" alt="Unidad 2"></a>
<a href="../README.md"><img src="https://img.shields.io/badge/%F0%9F%8F%A0%20Men%C3%BA%20Principal-blue?style=for-the-badge" alt="Menú Principal"></a>

---

# 📗 Unidad 3 - Modularidad y Arreglos en C

> Desarrollo de los conceptos fundamentales de la programación modular y del manejo de arreglos en lenguaje C, aplicando funciones, paso de parámetros y estructuras de datos unidimensionales, bidimensionales y tridimensionales para la construcción de programas organizados, reutilizables y eficientes.

---

# 📑 Contenido

- [1. Modularidad y Diseño Top-Down](#1-modularidad-y-diseño-top-down)
- [2. Pase de Parámetros](#2-pase-de-parámetros)
  - [2.1 Pase por Valor](#21-pase-por-valor)
  - [2.2 Pase por Referencia](#22-pase-por-referencia)
- [3. Arreglos en C](#3-arreglos-en-c)
  - [3.1 Arreglos Unidimensionales](#31-arreglos-unidimensionales)
  - [3.2 Arreglos Bidimensionales](#32-arreglos-bidimensionales)
  - [3.3 Arreglos Tridimensionales](#33-arreglos-tridimensionales)
- [4. Principales Dificultades](#4-principales-dificultades)
- [5. Reflexión Crítica](#5-reflexión-crítica)
- [6. Conclusiones Generales](#6-conclusiones-generales)
- [7. Bibliografía](#7-bibliografía)

---

# 1. Modularidad y Diseño Top-Down

## 📌 ¿Qué es la Modularidad?

La modularidad es uno de los principios más importantes en el diseño de software. Se basa en la estrategia de **"Divide y Vencerás"**, que consiste en fragmentar un programa informático grande y complejo en bloques o componentes de código más pequeños, independientes y manejables llamados **módulos**, los cuales en lenguaje C se conocen como **funciones**.

Cada función se diseña para cumplir una única tarea específica (**Alta Cohesión**) y debe depender lo menos posible del resto del programa (**Bajo Acoplamiento**).

## ¿Por qué es vital en computación?

- **Reutilización:** Evita escribir el mismo código varias veces; basta con llamar a la función cuando se la necesite.
- **Mantenibilidad:** Si hay un error en el sistema, es mucho más fácil aislarlo y corregirlo dentro de una función pequeña que buscarlo en un programa completo.
- **Legibilidad:** El código se vuelve más limpio, organizado y fácil de entender.
- **Escalabilidad:** Permite agregar nuevas funcionalidades sin modificar toda la estructura del programa.

## 💻 Diagrama

<p align="center">
  <img width="1536" height="1024" alt="ChatGPT Image 19 jul 2026, 20_44_32" src="https://github.com/user-attachments/assets/f6962252-1831-4bec-b0ca-571e55eea6ba" />
</p>

---

# 2. Pase de Parámetros

## 2.1 Pase por Valor

### 💡 ¿Cómo funciona?

Cuando enviamos una variable a una función **por valor**, el compilador de C hace una **copia exacta** del contenido de esa variable y la almacena en una dirección de memoria temporal reservada para esa función (en la pila o *stack*).

La función trabaja exclusivamente sobre esa copia. Por lo tanto, cualquier modificación, cálculo o cambio que se realice dentro del cuerpo de la función **no afectará de ninguna manera** a la variable original que se encuentra en el programa principal (`main`). Al terminar la función, esa copia se destruye.

Este mecanismo ofrece mayor seguridad cuando no se desea modificar el valor original de una variable.

### 💻 Diagrama

<p align="center">
  <img width="1536" height="1024" alt="ChatGPT Image 19 jul 2026, 20_27_43" src="https://github.com/user-attachments/assets/c2c27d62-cd7d-422e-9135-b82aeb7e5019" />
</p>


### 💻 Codificación

```c
#include <stdio.h>

// Prototipos
void mostrarMenu();
int leerNumero();
int duplicarNumero(int numero);
void mostrarResultado(int original, int duplicado);

int main() {
    int numero, resultado;

    mostrarMenu();
    numero = leerNumero();
    resultado = duplicarNumero(numero);
    mostrarResultado(numero, resultado);

    return 0;
}

// Muestra el encabezado
void mostrarMenu() {
    printf("=====================================\n");
    printf(" PROGRAMA: DUPLICAR UN NUMERO\n");
    printf("=====================================\n");
}

// Lee un número ingresado por el usuario
int leerNumero() {
    int n;
    printf("Ingrese un numero: ");
    scanf("%d", &n);
    return n;
}

// Duplica el número recibido
int duplicarNumero(int numero) {
    return numero * 2;
}

// Muestra los resultados
void mostrarResultado(int original, int duplicado) {
    printf("\nNumero original: %d\n", original);
    printf("Numero duplicado: %d\n", duplicado);
}

```

### ▶️ Ejecución del Código

<p align="center">
  <img src="ImagenesU3/pase_por_valor_ejecucion.png" alt="Ejecución Pase por Valor" width="750">
</p>

### 📝 Explicación del Código

El programa ilustra el aislamiento de variables que ocurre al implementar un pase de parámetros por valor en C.

* **Pase por Valor (`duplicarNumero(numero)`)**: Al invocar la función, el valor contenido en la variable del `main` se duplica en una nueva celda de memoria asignada al argumento formal de la función.
* **Modificación Aislada**: Cualquier operación realizada dentro de `duplicarNumero` ocurre estrictamente sobre la copia local. La variable `numero` del ámbito principal permanece intacta y libre de alteraciones no deseadas.
* **Retorno de Datos**: Para poder usar el resultado del cálculo fuera de la función, esta debe usar obligatoriamente la instrucción `return`, asignando el valor de salida a la variable `resultado` en el `main`.


### 📌 Idea Principal

En el pase por valor:

* Se genera y manipula una **copia independiente** del dato original en un espacio de memoria temporal.
* La función **no puede alterar** el valor de la variable externa que fue enviada como argumento.
* Es el método por defecto y más seguro en C para proteger la integridad de las variables originales cuando solo se necesita leer su información.

---

## 2.2 Pase por Referencia

### 💡 ¿Cómo funciona?

A diferencia de otros lenguajes de programación, el lenguaje C **no tiene un pase por referencia nativo**; en su lugar, lo simula utilizando **punteros**. 

Cuando queremos pasar un parámetro por referencia a una función, no enviamos una copia del valor. En su lugar, enviamos la **dirección de memoria RAM exacta** donde vive la variable original utilizando el operador de dirección (`&`). La función, por su parte, está diseñada para recibir esta dirección mediante un puntero (el cual se denota en la declaración con un asterisco `*`).

Al conocer la ubicación exacta del dato en el hardware, cualquier cambio que realice la función utilizando la **desreferenciación** modificará **directamente y en tiempo real** a la variable original ubicada en el `main`. Al finalizar la ejecución de la función, los cambios persisten de manera permanente.


### 💻 Diagrama

<p align="center">
  <img src="ImagenesU3/pase_por_referencia_diagrama.png" alt="Diagrama de Pase por Referencia" width="750">
</p>


### 💻 Codificación

```c
#include <stdio.h>

// Prototipos de funciones
void mostrarMenu();
void leerNumero(int *numero);
void duplicarPorReferencia(int *numero);
void mostrarResultado(int numero);

int main() {
    int numero;

    // Ejecución estructurada y modular
    mostrarMenu();
    
    // Se envía la dirección de memoria usando '&'
    leerNumero(&numero);
    
    // La función modificará la variable original directamente
    duplicarPorReferencia(&numero);
    
    // Se muestra el valor que ya ha sido alterado en memoria
    mostrarResultado(numero);

    return 0;
}

// Muestra el encabezado del programa
void mostrarMenu() {
    printf("=====================================\n");
    printf("    PROGRAMA: PASE POR REFERENCIA\n");
    printf("=====================================\n");
}

// Lee un número y lo guarda directamente en la dirección recibida
void leerNumero(int *numero) {
    printf("Ingrese un numero: ");
    scanf("%d", numero); // 'numero' ya es una dirección de memoria, no requiere '&' aquí
}

// Duplica el número modificando directamente la variable original en el main
void duplicarPorReferencia(int *numero) {
    // Se usa el asterisco '*' para acceder y modificar el valor en esa dirección
    *numero = (*numero) * 2;
}

// Muestra el resultado final obtenido
void mostrarResultado(int numero) {
    printf("\nEl numero duplicado es: %d\n", numero);
}

```
---

### ▶️ Ejecución del Código

<p align="center">
  <img src="ImagenesU3/pase_por_referencia_ejecucion.png" alt="Captura de Pantalla Ejecución Pase por Referencia" width="750">
</p>


### 📝 Explicación del Código

El programa simula un pase de parámetros por referencia implementando punteros, permitiendo que las funciones alteren el estado de las variables del `main()` de forma directa.

* **`leerNumero(int *numero)`**: Recibe la dirección de memoria de la variable local `numero`. Al ejecutar `scanf`, el valor introducido por el usuario se almacena directamente en la celda de memoria asignada en el programa principal.
* **`duplicarPorReferencia(int *numero)`**: Accede al espacio físico de la variable original mediante el operador de desreferenciación (`*`). Multiplica el valor por dos y sobrescribe el espacio original.
* **`main()`**: Al llamar finalmente a `mostrarResultado()`, la variable `numero` ya contiene el valor modificado (10 si se ingresó 5), demostrando que la función logró romper el aislamiento local que existía en el pase por valor.


### 📌 Idea Principal

En el pase por referencia (simulado con punteros):

* Se envía la dirección de memoria RAM de la variable utilizando el operador `&`.
* Las funciones pueden modificar permanentemente los datos originales en tiempo real.
* Es indispensable cuando una función necesita "retornar" más de un valor o actualizar estructuras de datos complejas.

---

# 3. Arreglos en C

## 📌 Definición General
Un arreglo es una estructura de datos que permite almacenar múltiples valores bajo un mismo nombre. Tienen dos características fundamentales:
* **Homogéneos:** Todos sus elementos deben ser del mismo tipo de dato (como enteros o flotantes).
* **Estáticos:** Su tamaño se define al escribir el código y no puede crecer ni encogerse mientras el programa corre.


## 3.1 Arreglos Unidimensionales

### 💡 ¿Qué son?
Un arreglo unidimensional, comúnmente llamado **vector**, es una lista lineal de elementos ordenados en una sola fila. Imagínalo como una tira de casilleros numerados. Cada casillero tiene un índice para saber su posición. 

En computación y en lenguaje C siempre empezamos a contar desde el **índice 0**. Si el vector tiene un tamaño de 5, sus índices válidos serán 0, 1, 2, 3 y 4.


### 💻 Codificación

```c
#include <stdio.h>

int main() {
    // Declaración e inicialización de un vector de 5 posiciones
    float notas[5] = {8.5, 9.0, 7.2, 10.0, 6.8};
    float suma = 0.0;
    float promedio = 0.0;

    printf("==================================================\n");
    printf("       ARREGLO UNIDIMENSIONAL: NOTAS EN C\n");
    printf("==================================================\n");

    // Usamos un bucle 'for' para recorrer el vector desde el índice 0 al 4
    for(int i = 0; i < 5; i++) {
        printf("Indice [%d] -> Estudiante %d: %.2f\n", i, i + 1, notas[i]);
        suma = suma + notas[i]; // Acumulador
    }

    promedio = suma / 5;

    printf("--------------------------------------------------\n");
    printf("Promedio General de la Unidad 3: %.2f\n", promedio);
    printf("==================================================\n\n");

    return 0;
}

```

---

### ▶️ Ejecución del Código

<p align="center">
  <img src="ImagenesU3/arregloUni_ejecucion.png" alt="Captura de Pantalla Ejecución Arreglo Unidimensional" width="750">
</p>


### 📝 Explicación del Código

El programa ilustra la declaración, inicialización y recorrido secuencial de un arreglo unidimensional en C.

* **Declaración (`float notas[5]`)**: Reserva un espacio continuo en memoria para almacenar 5 valores de tipo flotante (`float`) inicializados explícitamente en una sola línea.
* **Bucle `for`**: Configura un iterador `i` que inicia en `0` y se incrementa de uno en uno mientras sea menor que `5`. Esto permite acceder de forma exacta a cada celda del vector mediante la sintaxis `notas[i]`.
* **Acumulador (`suma = suma + notas[i]`)**: En cada iteración se extrae el valor del índice correspondiente y se adiciona a la variable acumuladora para calcular el promedio final tras romper el ciclo.


### 📌 Idea Principal

En los arreglos unidimensionales (vectores):

* El acceso a cualquier elemento es directo y rápido utilizando su número de índice (`vector[indice]`).
* El primer elemento de la estructura siempre se encuentra en la posición `0`.
* Son ideales para iterar colecciones de datos lineales de forma compacta utilizando estructuras cíclicas controladas como el bucle `for`.

---

## 3.2 Arreglos Bidimensionales

### 💡 ¿Qué son?
Un arreglo bidimensional, conocido como **matriz**, organiza los elementos en dos dimensiones: **filas y columnas** (como un tablero de ajedrez o una cuadrícula de Excel). Para ubicar un elemento específico, necesitas proveer dos índices de coordenadas: `matriz[fila][columna]`.

Internamente en la memoria de la computadora, la matriz se guarda de forma lineal, una fila detrás de la otra (*Row-Major Order*), aunque nuestra mente la abstraiga en 2D.


### 💻 Codificación

```c
#include <stdio.h>

int main() {
    // Declaración de una matriz de 3 filas y 3 columnas (3x3)
    int matriz[3][3] = {
        {10, 20, 30}, // Fila 0
        {40, 50, 60}, // Fila 1
        {70, 80, 90}  // Fila 2
    };

    printf("==================================================\n");
    printf("        ARREGLO BIDIMENSIONAL: MATRIZ 3x3\n");
    printf("==================================================\n");

    // Bucle externo 'i' maneja las filas
    for(int i = 0; i < 3; i++) {
        // Bucle interno 'j' maneja las columnas
        for(int j = 0; j < 3; j++) {
            // '\t' sirve para dar un espaciado horizontal uniforme
            printf("%d\t", matriz[i][j]);
        }
        // Al terminar de imprimir una fila entera, saltamos de línea
        printf("\n");
    }
    printf("==================================================\n");

    return 0;
}

```

---

### ▶️ Ejecución del Código

<p align="center">
  <img src="ImagenesU3/arregloBidi_ejecucion.png" alt="Captura de Pantalla Ejecución Arreglo Bidimensional" width="750">
</p>


### 📝 Explicación del Código

El programa muestra la manera en que se procesan las estructuras bidimensionales mediante ciclos anidados.

* **Declaración (`int matriz[3][3]`)**: Inicializa una matriz fija de $3 \times 3$ (9 celdas en total) agrupando los datos entre llaves internas que representan cada una de las filas en la cuadrícula.  
* **Bucle Anidado**: Requiere de dos contadores estructurados en capas. El bucle externo `i` controla la fila actual, mientras que el bucle interno `j` itera secuencialmente a través de cada columna de esa fila antes de avanzar.  
* **Espaciador (`\t`)**: Aplica una tabulación horizontal para mantener las columnas perfectamente alineadas al imprimir los datos en la terminal, seguido de un salto de línea `\n` al finalizar cada ciclo interno.  


### 📌 Idea Principal

En los arreglos bidimensionales (matrices):

* Se requieren dos coordenadas para acceder a cualquier dato: el primer índice indica la fila y el segundo la columna (`matriz[f][c]`).  
* Su lectura o impresión en pantalla se optimiza mediante el uso de **bucles `for` anidados** (uno dentro de otro).
* Aunque se representen visualmente de forma rectangular o cuadrada, en la memoria física de la computadora se estructuran como una sola secuencia continua de celdas lineales.

---

## 3.3 Arreglos Tridimensionales

### 💡 ¿Qué son?
Un arreglo tridimensional añade una dimensión extra al almacenamiento, conceptualizándose como un **cubo o un contenedor de matrices**. La mejor forma de comprenderlo es imaginar un cuaderno de hojas cuadriculadas:
1. El primer índice indica la **Página o Capa** (en qué hoja estás).
2. El segundo índice indica la **Fila** (en qué renglón de esa hoja estás).
3. El tercer índice indica la **Columna** (en qué celda de esa fila te ubicas).

Se declaran bajo la sintaxis: `arreglo[capas][filas][columnas]`. Son muy utilizados para procesar imágenes digitales a color (canales RGB) o registros de bases de datos multiindexadas en el tiempo.


### 💻 Codificación

```c
#include <stdio.h>

int main() {
    // Estructura: [3 estaciones/capas] [2 zonas/filas] [2 sensores/columnas]
    float clima[3][2][2] = {
        { // Capa 0: Estación Norte
            {18.5, 19.0},
            {17.2, 16.8}
        },
        { // Capa 1: Estación Centro
            {24.0, 23.5},
            {22.1, 25.0}
        },
        { // Capa 2: Estación Sur
            {12.4, 13.0},
            {11.5, 10.9}
        }
    };

    printf("==================================================\n");
    printf(" ARREGLO TRIDIMENSIONAL: HISTORIAL CLIMÁTICO\n");
    printf("==================================================\n");

    // k controla las capas (Estaciones)
    for(int k = 0; k < 3; k++) {
        printf("\n--> ESTACIÓN METEOROLÓGICA #%d <--\n", k + 1);
        // i controla las filas (Zonas)
        for(int i = 0; i < 2; i++) {
            // j controla las columnas (Sensores)
            for(int j = 0; j < 2; j++) {
                printf("[Zona %d] [Sensor %d]: %.1f C\t", i, j, clima[k][i][j]);
            }
            printf("\n"); // Fin de la fila
        }
    }
    printf("==================================================\n");

    return 0;
}

```


### ▶️ Ejecución del Código

<p align="center">
  <img src="ImagenesU3/arregloTridi_ejecucion.png" alt="Captura de Pantalla Ejecución Arreglo Tridimensional" width="750">
</p>


### 📝 Explicación del Código

El programa ejemplifica el manejo de datos con tres niveles de abstracción espacial mediante bucles altamente anidados.

* **Declaración (`float clima[3][2][2]`)**: Define una estructura cúbica estática que almacena lecturas meteorológicas, distribuidas jerárquicamente en 3 estaciones (capas), 2 zonas por estación (filas) y 2 sensores por zona (columnas).
* **Triple Bucle Anidado**: Requiere tres contadores independientes. El bucle externo `k` selecciona de manera secuencial la capa o estación, el intermedio `i` selecciona la fila interna, y el más profundo `j` recorre las celdas de las columnas.
* **Acceso Multidimensional (`clima[k][i][j]`)**: Permite ubicar de forma unívoca y exacta la temperatura de un sensor específico cruzando las tres variables de control en cada iteración interna.


### 📌 Idea Principal

En los arreglos tridimensionales (cubos de datos):

* Se necesitan obligatoriamente tres coordenadas o índices para extraer o guardar un solo elemento en la estructura (`arreglo[capa][fila][columna]`).
* Su procesamiento requiere de forma natural la implementación de un triple bucle anidado.
* Son ideales para representar información compleja del mundo real estructurada por capas, como mapas tridimensionales, procesamiento de píxeles RGB o series de tiempo segmentadas geográficamente.

---

# 4. Principales Dificultades

* **Pelear con los Punteros:** El mayor tropiezo fue entender cómo usar los punteros (`*` y `&`) para cambiar datos por referencia. Al principio cuesta asimilar que se están manejando direcciones de la memoria RAM y no el valor directo, lo que suele causar errores donde el programa se cierra solo (*Segmentation Fault*).
* **Perderse entre tantos bucles for:** Al trabajar con matrices y cubos (2D y 3D), cuesta bastante coordinar varios bucles metidos uno dentro de otro. Es sumamente fácil equivocarse en los índices y terminar imprimiendo datos cruzados.
* **Errores Invisibles:** En lenguaje C, si se pone por error un índice que no existe (como buscar la posición 5 en un arreglo que solo llega hasta el 4), el compilador no avisa nada. El programa sigue corriendo pero empieza a leer o dañar datos de otras variables. Aprender a rastrear y limpiar estos fallos invisibles fue muy estresante.

---

# 5. Reflexión Crítica

Escribir código usando estas herramientas cambió completamente mi forma de programar. Con la modularidad me di cuenta de que no se trata de escribir líneas a lo loco, sino de diseñar piezas que encajen bien. Ahora puedo crear código ordenado y limpio que sé que podré reutilizar en futuros proyectos de mi carrera.

Por otro lado, aprender a usar arreglos y cubos de información me abrió la mente. Aunque manejar la memoria de la computadora de forma manual con punteros fue difícil, entiendo que es una habilidad clave en Computación para hacer programas rápidos y eficientes. Siento que estas bases me preparan para retos reales y mucho más grandes en el futuro.

---
