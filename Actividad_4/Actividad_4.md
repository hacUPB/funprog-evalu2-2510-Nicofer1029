> ### Pregunta orientadora:
> 
> - ¿Por qué crees que el pseudocódigo es útil antes de escribir un programa en C?
R/ Porque es pseudocodigo nos da una idea general sobre el programa que debemos realizar; ademas nos indica la logica que posteriormente vamos a usar en el codigo en c y nos ayuda a estructurar mejor y en algunos casos optimzar antes de empezar a escribir codigo.
>
> ### Pregunta orientadora
> 
> - ¿Por qué es importante declarar el tipo de variable (int, float, etc.) antes de usarla en C?
R/ Porque es impoirtante que el computador sepa que tipo de variable va a ingresar el usuario y ademas el compilador luego tiene que saber cuanto espacio ocupa cada variable en la memoria.

### Actividad
 
- Escribe tu propio pseudocódigo para calcular el promedio de una lista de calificaciones y tradúcelo a C.

#### Pseudocódigo
```
Algoritmo Promedio_de_una_lista
	Escribir "Ingrese el numero de calificaciones que va a evaluar"
	leer num
	contador = 0
	suma = 0	
	Repetir
		Escribir "Ingrese la calificación"
		leer calificacion
		suma = suma + calificacion
		contador = contador + 1
	Hasta Que contador = num
	promedio = suma/num
	Escribir "El promedio de las calificaciones es:" promedio
FinAlgoritmo
```

#### Codigo en C

```
#include <stdio.h>

int main() {
    int num, contador = 0;
    float suma = 0, calificacion, promedio;

    // Pedir el número de calificaciones
    printf("Ingrese el número de calificaciones que va a evaluar: ");
    scanf("%d", &num);


    // Bucle equivalente a Repetir = Do"
    do {
        printf("Ingrese la calificación: ");
        scanf("%f", &calificacion);
        suma = suma + calificacion;
        contador++;
    } while (contador < num);

    // Calcular el promedio
    promedio = suma / num;

    // Mostrar el resultado
    printf("El promedio de las calificaciones es: %.2f\n", promedio);

    return 0;
}
```



