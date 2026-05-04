# Teoria de la Programación

## Unidad 1
# 🎓 Portafolio Digital de Aprendizaje - Unidad 1
## Carrera de Computación | Universidad Nacional de Loja

---

### 👤 Datos Informativos
> **Facultad de la Energía, las Industrias y los Recursos Naturales No Renovables**

*   **Estudiante:** Luis Carranza
*   **Ciclo/Paralelo:** I “A”
*   **Unidad:** 1
*   **Docente:** Ing. Lissette Geoconda López Faicán
*   **Periodo Académico:** Marzo 2026 – Agosto 2026

---

## 📚 Fundamentos Teóricos

### 1. Algoritmos
Un algoritmo es un conjunto **ordenado, finito y preciso** de instrucciones lógicas diseñadas para resolver un problema específico. Sus pilares fundamentales son:
*   **Finitud:** Posee un inicio y un fin determinados.
*   **Precisión:** Cada paso está definido sin ambigüedades.
*   **Eficiencia:** Permite obtener soluciones de forma sistemática.

### 2. Pseudocódigo
El pseudocódigo es una forma de expresar la lógica de un algoritmo utilizando un lenguaje intermedio, a medio camino entre el lenguaje humano natural y el lenguaje de programación real. Su objetivo principal es permitir que el desarrollador se centre en la solución lógica del problema sin preocuparse por las reglas sintácticas estrictas de un lenguaje específico (como C++, Java o Python).

### 3. Metodologías de Diseño
Para pasar de una idea al código, utilizamos herramientas intermedias:
*   **Pseudocódigo:** Permite centrarse en la lógica sin preocuparse por la sintaxis estricta de un lenguaje real.
*   **Diagrama de Flujo:** Perspectiva geométrica que facilita identificar errores lógicos y bucles.
*   **Prueba de Escritorio:** Proceso de simulación manual para detectar fallos en fórmulas o condiciones antes de programar.

---

## 💻 Aplicación Práctica: Estructura Secuencial

### Planteamiento del Problema
Diseñar un sistema que automatice el cálculo del **área de un triángulo** solicitando al usuario la base y la altura.

### Codificación en Lenguaje C
Utilizamos variables de tipo `float` para garantizar precisión con números decimales.

```c
#include <stdio.h>

int main() {
    // Definición de Variables
    float base, altura, area;

    // Entrada de Datos
    printf("Ingrese la base: ");
    scanf("%f", &base);

    printf("Ingrese la altura: ");
    scanf("%f", &altura);

    // Proceso: área = (base * altura) / 2
    area = (base * altura) / 2;

    // Salida de Resultados
    printf("El area calculada es: %.2f\n", area);

    return 0;
}


## Unidad 2

## Unidad 3
