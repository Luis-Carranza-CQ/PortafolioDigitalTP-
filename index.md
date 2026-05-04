<p align="center">
  <img src="<img width="400" height="156" alt="logo_unl" src="https://github.com/user-attachments/assets/03e5ccab-6a18-40ac-a3c1-6cb6c8173eb5" />
" width="350" alt="Logo Universidad Nacional de Loja">
</p>

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

## 🎯 Objetivo del Portafolio
Documentar de manera técnica y estructurada el aprendizaje obtenido sobre la lógica de programación, el uso de herramientas de diseño como **PSeInt** y la implementación final en **Lenguaje C**.

---

## 🛠️ Herramientas Utilizadas
<p align="left">
  <img src="https://img.shields.io/badge/C-00599C?style=flat-square&logo=c&logoColor=white" alt="C">
  <img src="https://img.shields.io/badge/Markdown-000000?style=flat-square&logo=markdown&logoColor=white" alt="Markdown">
  <img src="https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white" alt="GitHub">
  <img src="https://img.shields.io/badge/PSeInt-E1E1E1?style=flat-square" alt="PSeInt">
</p>


---

## **Contenidos**

### 1. Algoritmos
Un algoritmo se define como un conjunto ordenado, finito y preciso de instrucciones lógicas diseñadas para resolver un problema o ejecutar una tarea específica. Su funcionamiento se basa en un flujo estructurado que transforma datos iniciales (entradas) en resultados útiles (salidas) mediante la aplicación de reglas y cálculos predefinidos.
*   **Finitud:** Posee un inicio y un fin determinados tras un número exacto de pasos.
*   **Precisión:** Cada paso está definido sin ambigüedades.
*   **Eficiencia:** Cada paso está definido sin ambigüedades.
•	Eficiencia: Permite procesar datos y obtener soluciones de forma sistemática y reproducible.

#### 1.1 Pseudocódigo
El pseudocódigo es una forma de expresar la lógica de un algoritmo utilizando un lenguaje intermedio, a medio camino entre el lenguaje humano natural y el lenguaje de programación real. Su objetivo principal es permitir que el desarrollador se centre en la solución lógica del problema sin preocuparse por las reglas sintácticas estrictas de un lenguaje específico (como C++, Java o Python).

##### Ejemplo de pseudocódigo en PSeInt:
<img width="886" height="665" alt="image" src="https://github.com/user-attachments/assets/ffb67e0d-67db-4629-9608-72790b6ca7a3" />

##### Codigo en PseInt
```
Algoritmo AhorroAnual
	//Variables
	Definir sueldo_mensual, sueldo_semanal, ahorro_semanal, ahorro_anual Como Real;
	
	//Entrada
	Escribir "------------------------------------------"
	Escribir "$$$-CALCULO DE AHORRO SEMANAL Y ANUAL-$$$"
	Escribir "------------------------------------------"
	Escribir "Ingrese su sueldo mensual ($):";
	Leer sueldo_mensual;
	
	//Proceso
	sueldo_semanal=sueldo_mensual/4;
	ahorro_semanal=sueldo_semanal*0.15;
	
	//Calculo de ahorro anual (12 meses = 48 semanas)
	ahorro_anual = ahorro_semanal*48;
	
	//Salida
	Escribir "-------------------------------------------"
	Escribir "SU AHORRO SEMANAL ES DE: ", ahorro_semanal "$"
	Escribir "------------------------------------------";
	Escribir "SU AHORRO ANUAL ES DE: ", ahorro_anual "$"
	Escribir "------------------------------------------"
	
FinAlgoritmo
```

#### 1.2 Diagrama de flujo: 
Un diagrama de flujo es una herramienta visual que utiliza símbolos estandarizados para representar los pasos sucesivos de un proceso o algoritmo. Mientras que el pseudocódigo es una descripción narrativa, el diagrama de flujo ofrece una perspectiva geométrica que facilita la identificación de errores lógicos, bucles y bifurcaciones en el sistema.
<img width="758" height="1239" alt="image" src="https://github.com/user-attachments/assets/f1395712-6eb4-44df-ac6e-d0a3b5999a64" />

#### 1.3 Prueba de Escritorio
Una prueba de escritorio es un proceso de simulación manual en el que el desarrollador actúa como el procesador de la computadora. Consiste en seguir paso a paso las instrucciones de un algoritmo o pseudocódigo, utilizando valores de entrada arbitrarios y registrando los cambios en las variables en una tabla.
Su objetivo principal es detectar errores de lógica, como fórmulas incorrectas, bucles infinitos o condiciones mal planteadas, que a menudo pasan desapercibidos durante la redacción del código.

| Variable | Procedimiento Matemático | Valor Resultante |
| :--- | :--- | :---: |
| **sueldo_mensual** | Entrada de datos | 800 |
| **sueldo_semanal** | sueldo_mensual / 4 | 200 |
| **ahorro_semanal** | sueldo_semanal * 0.15 | 30 |
| **ahorro_anual** | ahorro_semanal * 48 | **1440** |

#### 1.4 Lenguajes de programación 
Un lenguaje de programación es un conjunto de reglas y símbolos que permiten a los humanos dar instrucciones precisas a una computadora para resolver problemas o procesar datos. Estas herramientas se clasifican principalmente por cómo traducen esas órdenes: los lenguajes compilados, como C, traducen todo el código de una sola vez antes de ejecutarlo para ganar velocidad; los interpretados, como Python, traducen y ejecutan el código línea por línea en tiempo real para ser más flexibles; mientras que lenguajes como Java usan un método híbrido que traduce el código a un formato intermedio para que pueda funcionar en cualquier dispositivo sin cambios.

##### Ejemplo de mi pseudocódigo, pero en lenguaje C
<img width="820" height="1021" alt="image" src="https://github.com/user-attachments/assets/db4b189b-b599-4f72-a051-5402e36441e8" />

##### Codigo en C
```
#include <stdio.h>

int main() {
    // Definir las variables
    float sueldo_mensual, sueldo_semanal, ahorro_semanal, ahorro_anual;

    // Entrada de datos
    printf("----------------------------------------------------\n");
    printf("$$$-CALCULO DE AHORRO SEMANAL Y ANUAL-$$$\n");
    printf("----------------------------------------------------\n");
    printf("Ingrese su sueldo mensual ($): ");
    scanf("%f", &sueldo_mensual);

    // Proceso
    sueldo_semanal = sueldo_mensual / 4;
    ahorro_semanal = sueldo_semanal * 0.15;
    
    // Calculo de ahorro anual (12 meses = 48 semanas)
    ahorro_anual = ahorro_semanal * 48;

    // Salida de resultados
    printf("----------------------------------------------------\n");
    printf("SU AHORRO SEMANAL ES DE: %.2f $\n", ahorro_semanal);
    printf("----------------------------------------------------\n");
    printf("SU AHORRO ANUAL ES DE: %.2f $\n", ahorro_anual);
    printf("----------------------------------------------------\n");

    return 0;
}
```

---

### 2. Programación por bloques
La programación por bloques es una forma de programar diseñada para facilitar el aprendizaje de la lógica computacional sin necesidad de escribir código manualmente. En lugar de usar texto complejo, se utilizan piezas gráficas (parecidas a bloques de construcción o rompecabezas) que se arrastran y conectan entre sí para crear instrucciones.
<img width="383" height="259" alt="image" src="https://github.com/user-attachments/assets/fb95ffec-cbbe-4c0b-b879-570298713b2d" />
<img width="690" height="222" alt="image" src="https://github.com/user-attachments/assets/1796956e-760e-45ea-bacb-48c734f67532" />

---

## Ejercicio con estructura secuencial (lenguaje dado en clase)

### 1. Planteamiento del problema
Se requiere un programa que automatice el cálculo del área de un triángulo. El sistema debe solicitar al usuario la base y la altura, procesar estos datos mediante la fórmula geométrica estándar y mostrar el resultado exacto en pantalla.
### 2. Análisis del problema
* **Variables:** Se utilizan variables de tipo float en C para permitir el uso de decimales
* **Entrada:** base y altura (Números reales/decimales)
* **Proceso:** Aplicar la formula: área = (base*altura) / 2
* **Salida:** Un mensaje con el valor resultante del área

### 3. Diseño del Algoritmo
#### 3.1 Pseudocódigo
<img width="886" height="878" alt="image" src="https://github.com/user-attachments/assets/c580fac5-fc3a-428f-a443-1f1b4666ede7" />

##### Codigo en PSeInt
```c
Algoritmo area_Triangulo
	//Definir Variables
	Definir base Como Real;
	Definir altura Como Real;
	Definir area Como Real;
	
	//Datos de Entrada
	Escribir "Ingrese la base";
	leer base;
	
	Escribir "Ingrese la altura";
	leer altura;
	
	//Proceso 
	//base * altura / 2
	area = (base * altura) /2;
	
	//Salida
	Escribir "El area es: ", area;
	
FinAlgoritmo
```

#### 3.2 Diagrama de flujo:
<img width="739" height="1172" alt="image" src="https://github.com/user-attachments/assets/c4719960-0cf5-4803-9fa1-862979908907" />


### 4. Codificación (código fuente)
<img width="791" height="951" alt="image" src="https://github.com/user-attachments/assets/9b1e18a0-3f05-4526-adaf-43b9734e0f39" />


#### Codigo en C  
```c
#include <stdio.h>

int main() {
    // Definir Variables
    float base, altura, area;

    // Datos de Entrada
    printf("Ingrese la base: ");
    scanf("%f", &base);

    printf("Ingrese la altura: ");
    scanf("%f", &altura);

    // Proceso: Aplicación de la fórmula geométrica estándar
    area = (base * altura) / 2;

    // Salida: Resultado formateado con dos decimales
    printf("El area es: %.2f\n", area);

    return 0;
}
```

### 5. Validación (prueba de escritorio) 

| Variable | Valor Resultante | Procedimiento Matemático Aplicado |
| :--- | :---: | :--- |
| **base** | 10 | Valor ingresado por el usuario |
| **altura** | 5 | Valor ingresado por el usuario |
| **área** | **25** | $(10 \times 5) / 2$ (Base por altura dividido para dos) |


---

## Principales dificultades y reflexión crítica en la aplicación de los contenidos.
### 1. Principales dificultades de los contenidos 
Lo más difícil es que C es mucho más estricto con las reglas: si olvidas un punto y coma ( ; ) o una llave ({ }), el programa no funciona. También es confuso aprender a usar códigos como %f o el símbolo & para guardar datos en la memoria, algo que en PSeInt no era necesario. Por último, está la pelea con el antivirus o Windows, que a veces bloquea tus archivos .exe y no te deja ver si tu código quedó bien.

### 2. Reflexión critica en la aplicación
Programar en C me enseñó que la lógica no lo es todo; la precisión técnica es vital. A diferencia de PSeInt, aquí un pequeño error de escritura detiene todo. Esta experiencia me ayudó a ser más ordenado y a entender que, como ingeniero, debo dominar tanto la resolución de problemas como el funcionamiento real de las herramientas y la seguridad de la computadora.

### 3. Conclusión
En conclusión, el desarrollo de este programa demuestra que la programación es un proceso que va desde la lógica básica hasta la implementación técnica real. Lograr que el código pase de un simulador como PSeInt a un lenguaje profesional como C requiere no solo saber resolver el problema matemático, sino también aprender a configurar el entorno de trabajo y superar los bloqueos de seguridad del sistema. Esta práctica es fundamental para entender cómo se construye el software de manera estructurada y funcional.

---

## Bibliografía


## Unidad 3
