# 📗 Unidad 2 - Estructuras Condicionales y Repetitivas

> Desarrollo de los conceptos fundamentales de estructuras condicionales y repetitivas utilizadas en la construcción de algoritmos.

---

## 📑 Contenido

* [1. Estructuras Condicionales](#1-estructuras-condicionales)
* [2. Estructuras Repetitivas](#2-estructuras-repetitivas)
* [3. Ejercicio Integrador](#3-ejercicio-integrador)
* [4. Validación](#4-validación-prueba-de-escritorio)
* [5. Principales Dificultades](#5-principales-dificultades)
* [6. Reflexión Crítica](#6-reflexión-crítica)

---

# 1. Estructuras Condicionales

Las estructuras condicionales permiten al flujo de un algoritmo tomar caminos distintos basados en el cumplimiento de una condición (verdadera o falsa).

## A. Condicional Simple (Si-Entonces)

Ejecuta una acción únicamente cuando una condición es verdadera. Si la condición es falsa, el algoritmo continúa con su flujo normal.

### Pseudocódigo

```text
Si condición Entonces
    instrucciones
FinSi
```

### Diagrama de Flujo

![Condicional Simple](https://github.com/Luis-Carranza-CQ/PortafolioDigitalTP-/blob/main/Captura%20de%20pantalla%202026-06-09%20222852.png?raw=true)

---

## B. Condicional Compuesta (Si-Entonces-Sino)

Permite seleccionar entre dos caminos posibles. Si la condición es verdadera ejecuta un bloque de instrucciones; si es falsa ejecuta otro diferente.

### Pseudocódigo

```text
Si condición Entonces
    instrucciones_bloque_verdadero
Sino
    instrucciones_bloque_falso
FinSi
```

### Diagrama de Flujo

![Condicional Compuesta](https://github.com/Luis-Carranza-CQ/PortafolioDigitalTP-/blob/main/Captura%20de%20pantalla%202026-06-09%20222901.png?raw=true)

---

## C. Condicional Múltiple (Según Sea / Switch)

Evalúa una variable o condición entre varias alternativas posibles.

### Pseudocódigo

```text
Según variable Hacer
    opcion_1: instrucciones_1
    opcion_2: instrucciones_2
    De Otro Modo: instrucciones_defecto
FinSegun
```

### Diagrama de Flujo

![Condicional Múltiple](https://github.com/Luis-Carranza-CQ/PortafolioDigitalTP-/blob/main/Captura%20de%20pantalla%202026-06-09%20222911.png?raw=true)

---

# 2. Estructuras Repetitivas

Las estructuras repetitivas permiten ejecutar un conjunto de instrucciones varias veces mientras se cumpla una condición determinada.

## A. Mientras (While)

Evalúa la condición antes de ejecutar el bloque de instrucciones. Si la condición es falsa desde el inicio, el ciclo nunca se ejecuta.

### Pseudocódigo

```text
Mientras condición Hacer
    instrucciones
    actualización de variable de control
FinMientras
```

### Diagrama de Flujo

![While](https://github.com/Luis-Carranza-CQ/PortafolioDigitalTP-/blob/main/Captura%20de%20pantalla%202026-06-09%20222921.png?raw=true)

---

## B. Repetir-Hasta (Repeat Until)

Ejecuta el bloque de instrucciones al menos una vez, ya que la condición se evalúa al finalizar cada repetición.

### Pseudocódigo

```text
Repetir
    instrucciones
Hasta Que condición
```

### Diagrama de Flujo

![Repetir Hasta](https://github.com/Luis-Carranza-CQ/PortafolioDigitalTP-/blob/main/Captura%20de%20pantalla%202026-06-09%20222930.png?raw=true)

---

## C. Para (For)

Se utiliza cuando se conoce previamente la cantidad exacta de repeticiones que debe realizar el ciclo.

### Pseudocódigo

```text
Para variable_control <- valor_inicial Hasta valor_final Con Paso incremento Hacer
    instrucciones
FinPara
```

### Diagrama de Flujo

![For](https://github.com/Luis-Carranza-CQ/PortafolioDigitalTP-/blob/main/Captura%20de%20pantalla%202026-06-09%20222939.png?raw=true)

---

# 3. Ejercicio Integrador

## Planteamiento del Problema

Una tienda de tecnología ofrece un descuento especial a sus clientes.

Por cada cliente se ingresa el total de su compra:

* Si la compra es mayor a $100 se aplica un descuento del 15%.
* Si la compra es menor o igual a $100 no recibe descuento.
* El programa debe mostrar el total a pagar por cada cliente.
* Al finalizar debe mostrar el dinero total recaudado por la tienda.

## Análisis del Problema

### Entradas

* Número de clientes (N)
* Valor de compra de cada cliente

### Procesos

* Repetir el proceso N veces.
* Evaluar si la compra supera los $100.
* Calcular descuento cuando corresponda.
* Determinar el pago final.
* Acumular la recaudación total.

### Salidas

* Pago final por cliente.
* Total recaudado por la tienda.

### Diagrama de Flujo

![Ejercicio Integrador](https://github.com/Luis-Carranza-CQ/PortafolioDigitalTP-/blob/main/Gemini_Generated_Image_2tmwls2tmwls2tmw.png?raw=true)

---

## Codificación

```text
#include <stdio.h>

int main() {
    // Declaración de variables
    int n, i;
    float compra, descuento, pago_final;
    float total_tienda = 0.0; // Mi acumulador para el total

    printf("--- SISTEMA DE VENTAS ---\n");
    printf("Ingrese la cantidad de clientes a procesar: ");
    scanf("%d", &n);

    // Mi estructura repetitiva (un ciclo For)
    for (i = 1; i <= n; i++) {
        printf("\n--- Cliente %d ---\n", i);
        printf("Ingrese el monto de la compra: $");
        scanf("%f", &compra);
        
        // Mi estructura condicional (un If-Else)
        if (compra > 100) {
            descuento = compra * 0.15;
            printf("Felicidades Aplica un 15%% de descuento.\n");
        } else {
            descuento = 0.0;
            printf("No aplica descuento.\n");
        }
        
        // Calculo lo que paga este cliente y lo sumo al total de la tienda
        pago_final = compra - descuento;
        total_tienda = total_tienda + pago_final; 
        
        printf("Total a pagar por este cliente: $%.2f\n", pago_final);
    }

    // Al salir del ciclo, muestro el resultado final
    printf("\n=========================================\n");
    printf("Monto total recaudado por la tienda: $%.2f\n", total_tienda);
    printf("=========================================\n");

    return 0;
}
```

---

# 4. Validación (Prueba de Escritorio)

Supongamos que se procesan **2 clientes**.

| Cliente | Compra | ¿Mayor a $100? | Descuento | Pago Final |
| ------- | ------ | -------------- | --------- | ---------- |
| 1       | 120.00 | Sí             | 18.00     | 102.00     |
| 2       | 50.00  | No             | 0.00      | 50.00      |

![For](https://github.com/Luis-Carranza-CQ/PortafolioDigitalTP-/blob/main/Captura%20de%20pantalla%202026-06-09%20211054.png?raw=true)

### Resultado esperado

```text
Total Tienda = $152.00
```

---

# 5. Principales Dificultades

Durante la aplicación práctica de estas estructuras pueden surgir dificultades como:

* Olvidar actualizar la variable de control en ciclos Mientras, provocando ciclos infinitos.
* Confundir variables contadoras con variables acumuladoras.
* Cometer errores al establecer los límites de repetición.
* Procesar una iteración más o menos de las necesarias debido a condiciones mal definidas.

---

# 6. Reflexión Crítica

Aprender sobre estructuras condicionales y repetitivas permitió comprender cómo una computadora puede tomar decisiones y automatizar procesos. El principal aprendizaje fue reconocer que antes de programar es necesario analizar el problema y organizar correctamente la lógica de solución. Un diseño adecuado mediante diagramas de flujo y pseudocódigo facilita la implementación y reduce significativamente los errores durante la codificación.

---

[⬅ Volver al Portafolio Principal](../index.md)
