# Actividad 4: de algoritmo a código fuente

### Pregunta orientadora:
 
- ¿Por qué crees que el pseudocódigo es útil antes de escribir un programa en C?

- R/ Porque es pseudocodigo nos da una idea general sobre el programa que debemos realizar; ademas nos indica la logica que posteriormente vamos a usar en el codigo en c y nos ayuda a estructurar mejor y en algunos casos optimzar antes de empezar a escribir codigo.


### Pregunta orientadora

- ¿Por qué es importante declarar el tipo de variable (int, float, etc.) antes de usarla en C?

- R/ Porque es impoirtante que el computador sepa que tipo de variable va a ingresar el usuario y ademas el compilador luego tiene que saber cuanto espacio ocupa cada variable en la memoria.

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



### Pregunta orientadora
 
- ¿Por qué es importante comentar el código, aunque sea breve y conciso?

- R/ Porque ayudara a que sea facil de entender no solo para ti sino para las demas persona que vean tu codigo. Tambien estos comentarios le dan orden y claridad a la hora de escribir codigo.

## Reto final

### Reto 1

```
#include <stdio.h>
#include <math.h>  // Biblioteca para la función sqrt()

int main() {
    float x1, x2, y1, y2, distancia;

    // Pedir los valores al usuario
    printf("Para calcular la distancia de P1 a P2 ingrese los valores:\n");
    
    printf("Ingrese x1: ");
    scanf("%f", &x1);

    printf("Ingrese x2: ");
    scanf("%f", &x2);

    printf("Ingrese y1: ");
    scanf("%f", &y1);

    printf("Ingrese y2: ");
    scanf("%f", &y2);

    // Calcular la distancia usando la fórmula
    distancia = sqrt(pow(x2 - x1, 2) + pow(y2 - y1, 2));

    // Mostrar el resultado
    printf("La distancia entre los puntos es: %.2f\n", distancia);

    return 0;
}
```

### Reto 2

```
#include <stdio.h>

int main() {
    float metros, pulgadas;

    // Pedir al usuario la cantidad en metros
    printf("Ingrese la cantidad de tela en metros que desea comprar: ");
    scanf("%f", &metros);

    // Convertir metros a pulgadas (1 pulgada = 0.0254 metros)
    pulgadas = metros / 0.0254;

    // Mostrar el resultado
    printf("La cantidad de pulgadas que debe pedir al extranjero son: %.2f\n", pulgadas);

    return 0;
}
```

### Reto 3

```
int main() {
    float cateto1, cateto2, hipotenusa;

    // Pedir los valores al usuario
    printf("Ingrese el cateto 1: ");
    scanf("%f", &cateto1);

    printf("Ingrese el cateto 2: ");
    scanf("%f", &cateto2);

    // Calcular la hipotenusa con la fórmula de Pitágoras
    hipotenusa = sqrt(pow(cateto1, 2) + pow(cateto2, 2));

    // Mostrar el resultado
    printf("La hipotenusa es: %.2f\n", hipotenusa);

    return 0;
}
```

### Reto 4

```
#include <stdio.h>

int main() {
    int dia, mes, ano;
    int dia_actual, mes_actual, ano_actual;
    int edad;

    // Pedir la fecha de nacimiento
    printf("Ingrese su fecha de nacimiento\n");
    printf("Ingrese el dia: ");
    scanf("%d", &dia);
    printf("Ingrese el mes: ");
    scanf("%d", &mes);
    printf("Ingrese el año: ");
    scanf("%d", &ano);

    // Pedir la fecha actual
    printf("Ingrese la fecha actual\n");
    printf("Ingrese el dia actual: ");
    scanf("%d", &dia_actual);
    printf("Ingrese el mes actual: ");
    scanf("%d", &mes_actual);
    printf("Ingrese el año actual: ");
    scanf("%d", &ano_actual);

    // Calcular la edad inicial
    edad = ano_actual - ano;

    // Comprobar si ya cumplió años
    if (mes_actual < mes) {  
        edad = edad - 1;  
    } else {  
        if (mes_actual == mes) {  
            if (dia_actual < dia) {  
                edad = edad - 1;  
            }  
        }  
    }

    // Mensaje de cumpleaños
    if (mes_actual == mes) {  
        if (dia_actual == dia) {  
            printf("Hoy es su cumpleaños, ¡Feliz Cumpleaños!\n");  
        }  
    }

    // Mostrar la edad final
    printf("Usted tiene %d años\n", edad);

    return 0;
}
```
### Reto 5

```
#include <stdio.h>

int main() {
    int horas_trabajadas;
    float pago_por_hora, sueldo;

    // Pedir horas trabajadas
    printf("Para calcular su sueldo semanal\n");
    printf("Ingrese el numero de horas trabajadas: ");
    scanf("%d", &horas_trabajadas);

    // Verificar si excede el límite
    if (horas_trabajadas > 50) {
        printf("No está permitido trabajar más de 50 horas\n");
    } else {
        // Pedir el pago por hora
        printf("Ingrese el pago que recibe por hora: ");
        scanf("%f", &pago_por_hora);

        // Cálculo inicial del sueldo
        sueldo = horas_trabajadas * pago_por_hora;

        // Verificar si se aplican pagos extra
        if (horas_trabajadas > 40) {
            if (horas_trabajadas > 45) {
                sueldo = horas_trabajadas * (3 * pago_por_hora);
            } else {
                sueldo = horas_trabajadas * (2 * pago_por_hora);
            }
        } else {
            if (horas_trabajadas < 41) {
                sueldo = horas_trabajadas * pago_por_hora;
            }
        }

        // Imprimir el sueldo final
        printf("Su sueldo semanal es: $%.2f pesos\n", sueldo);
    }

    return 0;
}
```

### Pregunta final

- Después de este tutorial, ¿qué puntos crees que deberías reforzar para sentirte más seguro al traducir pseudocódigo a C?

- R/ Aprender a diferenciar mejor entre pseudocodigo y codigo, porque por ejemplo el pseudocodigo lo hago en español y hay cosas que cambian cunado estas programando porque es en ingles y tambien tener e cuenta que hay algunas estructuras que cambian en la redaccion y es imortante tenerlas en cuenta. Ademas no olvidarse de los pequeños detalles como los puntos y coma que se olvidan con mucha facilidad.