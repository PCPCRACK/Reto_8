# Reto_8
1. Imprimir un listado con los números del 1 al 100 cada uno con su respectivo cuadrado.
```python
if __name__ == "__main__":
    n = int(1) #inicializa a n en 1
    while n <= 100:
        
        """Mientras el valor de n sea menor o igual a 100, se
        va a repertir el print y se le sumara 1 a n cada vez
        que se repita el ciclo"""
        
        print("El cuadrado del número ",n," es", n**2) #se eleva el numero dentro del print
        n +=1 #se le suma 1 a n cada ciclo
```
2.  Imprimir un listado con los números impares desde 1 hasta 999 y seguidamente otro listado con los números pares desde 2 hasta 1000.
```python
if __name__ == "__main__":
    n = 1 #inicializa n en 1
    print ("un listado con los números impares desde 1 hasta 999") #se ejecuta antes de iniciar el ciclo
    while n < 1000: #mientras n sea menor que 1000
        if n%2 > 0: #compara si el valor del la divion por residuo de n es mayor a cero
            print (n) #imprime el valor de n en cada ciclo
        n += 1 #suma 1 al valor de n
        
    n = 2 #cambia el valor de n a 2
    print("listado con los números pares desde 2 hasta 1000.") #se ejecuta antes de iniciar el ciclo
    while n <= 1000: #mientras n sea menor o igual que 1000
        if n%2 == 0: #compara si el valor del la divion por residuo de n es igual a cero
            print (n) #imprime el valor de n en cada ciclo
        n += 1 #resta 1 al valor de n
```
3.  Imprimir los números pares en forma descendente hasta 2 que son menores o iguales a un número natural n ≥ 2 dado
```python
if __name__ == "__main__" :
    n = int(1000) #inicializa n en 1000
    print("números pares en forma descendente hasta 2") #se ejecuta antes de iniciar el ciclo
    while n>=2: #mientras n sea mayor que 1
        if n%2 == 0: #compara si el valor del la divion por residuo de n es igual a cero
            print(n) #imprime el valor de n en cada ciclo si se cumple la condicion
        n -= 1 #resta 1 al valor de n
```
4. Imprimir los números de 1 hasta un número natural n dado, cada uno con su respectivo factorial
```python
def factorial(n): #definimos un funcion
    # Verificar si el número es 0 o 1 (en cuyo caso su factorial es 1)
    if n == 0 or n == 1:
        return 1
    else:
        # Calcular el factorial multiplicando el número por el factorial de su predecesor
        return n * factorial(n-1)

if __name__ == "__main__":
    # Solicitar al usuario que ingrese un número natural
    n = int(input("Ingrese un número natural: "))

    # Utilizar un bucle for para imprimir los números del 1 al n junto con su factorial correspondiente
    for i in range(1, n+1):
        # Utilizar la función factorial definida anteriormente para calcular el factorial de cada número
        print(f"{i}! = {factorial(i)}")
```
Version alterna a ese codigo
```python
n = int(input("Ingrese numero final: "))
a = 1
i = 1
t = 1
while a <= n:
    while i <= a:
        t *= i
        i += 1
    print ("el factoria de ",a," es ",t)
    t = 1
    i = 1
    a += 1
```
5. Calcular el valor de 2 elevado a la potencia n usando ciclos for.
```python
if __name__ == "__main__":
    # Solicitar al usuario que ingrese un número entero
    n = int(input("Ingrese un número entero: "))

    # Inicializar la variable resultado en 1
    resultado = 1

    # Utilizar un bucle for para multiplicar 2 por sí mismo n veces
    for i in range(n):
        resultado *= 2

    # Imprimir el resultado utilizando una cadena formateada
    print(f"2^{n} = {resultado}")
```
6. Leer un número natural n, leer otro dato de tipo real x y calcular x^n usando ciclos for.
```python
if __name__ == "__main__":
    # Solicitar al usuario que ingrese un número natural
    n = int(input("Ingrese un número natural: "))

    # Solicitar al usuario que ingrese un número real
    x = float(input("Ingrese un número real: "))

    # Inicializar la variable resultado en 1
    resultado = 1

    # Utilizar un bucle for para multiplicar x por sí mismo n veces
    for i in range(n):
        resultado *= x

    # Imprimir el resultado utilizando una cadena formateada
    print(f"{x}^{n} = {resultado}")
```
7. Diseñe un programa que muestre las tablas de multiplicar del 1 al 9.
```
if __name__ == "__main__":
# Iterar por cada número del 1 al 9
    for i in range(1, 10):
    # Imprimir el encabezado de la tabla
        print(f"Tabla del {i}:")
        # Iterar por cada número del 1 al 10
        for j in range(1, 11):
        # Calcular el producto de i y j y mostrarlo en la consola
            print(f"{i} x {j} = {i*j}")
    # Imprimir una línea en blanco para separar las tablas
    print()
```
8. Diseñar una función que permita calcular una aproximación de la función exponencial alrededor de 0 para cualquier valor x (real), utilizando los primeros n términos de la serie de Maclaurin. **nota:** use *math* para traer la función exponencial y mostrar la diferencia entre el valor real y la aproximación.
$$e^x \approx exp(x,n) \approx \sum_{i=0}^{n}\frac{x^i}{i!}$$
```python
import math

def exp_aprox(x, n):
    """
    Calcula una aproximación de la función exponencial alrededor de 0 para cualquier valor x (real),
    utilizando los primeros n términos de la serie de Maclaurin.

    Parámetros:
    x -- El valor para el cual se desea aproximar la función exponencial.
    n -- El número de términos de la serie de Maclaurin que se utilizarán para la aproximación.

    Retorna:
    El valor de la aproximación de la función exponencial alrededor de 0 para el valor de x dado.
    """

    # Inicializar el resultado en 0
    resultado = 0

    # Utilizar un bucle for para sumar los primeros n términos de la serie de Maclaurin
    for i in range(n):
        # Calcular el término actual de la serie de Maclaurin
        termino = x**i / math.factorial(i)
        # Agregar el término actual al resultado
        resultado += termino

    # Devolver el resultado de la aproximación
    return resultado

if __name__ == "__main__":
    # Pedir al usuario que ingrese los valores de x y n
    x = float(input("Ingrese el valor de x: "))
    n = int(input("Ingrese el número de términos de la serie de Maclaurin que se utilizarán para la aproximación: "))

    # Calcular el valor real de la función exponencial para x
    valor_real = math.exp(x)

    # Calcular la aproximación utilizando la función exp_aprox
    aproximacion = exp_aprox(x, n)

    # Imprimir el valor real, la aproximación y la diferencia entre ellos
    print(f"Valor real: {valor_real}")
    print(f"Aproximación: {aproximacion}")
    print(f"Diferencia: {abs(valor_real - aproximacion)}")
```
9. Diseñar una función que permita calcular una aproximación de la función seno alrededor de 0 para cualquier valor x (real), utilizando los primeros n términos de la serie de Maclaurin. **nota:** use *math* para traer la función seno y mostrar la diferencia entre el valor real y la aproximación.
$$sin(x) \approx sin(x,n) \approx \sum_{i=0}^{n} (-1)^i \frac{x^{2i+1}}{(2i+1)!}$$
```python
import math

def sin_aprox(x, n):
    """
    Calcula una aproximación de la función seno alrededor de 0 para cualquier valor x (real),
    utilizando los primeros n términos de la serie de Maclaurin.

    Parámetros:
    x -- El valor para el cual se desea aproximar la función seno.
    n -- El número de términos de la serie de Maclaurin que se utilizarán para la aproximación.

    Retorna:
    El valor de la aproximación de la función seno alrededor de 0 para el valor de x dado.
    """

    # Inicializar el resultado en 0
    resultado = 0

    # Utilizar un bucle for para sumar los primeros n términos de la serie de Maclaurin
    for i in range(n):
        # Calcular el término actual de la serie de Maclaurin
        termino = (-1)**i * x**(2*i + 1) / math.factorial(2*i + 1)
        # Agregar el término actual al resultado
        resultado += termino

    # Devolver el resultado de la aproximación
    return resultado

if __name__ == "__main__":
    # Pedir al usuario que ingrese los valores de x y n
    x = float(input("Ingrese el valor de x: "))
    n = int(input("Ingrese el número de términos de la serie de Maclaurin que se utilizarán para la aproximación: "))

    # Calcular el valor real de la función seno para x
    valor_real = math.sin(x)

    # Calcular la aproximación utilizando la función sin_aprox
    aproximacion = sin_aprox(x, n)

    # Imprimir el valor real, la aproximación y la diferencia entre ellos
    print(f"Valor real: {valor_real}")
    print(f"Aproximación: {aproximacion}")
    print(f"Diferencia: {abs(valor_real - aproximacion)}")
```
10. Diseñar una función que permita calcular una aproximación de la función arcotangente alrededor de 0 para cualquier valor x en el rango [-1, 1], utilizando los primeros n términos de la serie de Maclaurin. **nota:** use *math* para traer la función arctan y mostrar la diferencia entre el valor real y la aproximación.
$$arctan(x) \approx arctan(x,n) \approx \sum_{i=0}^{n} (-1)^i \frac{x^{2i+1}}{(2i+1)}$$
```python
import math

def arcotangente_aprox(x, n):
    """
    Calcula una aproximación de la función arcotangente alrededor de 0 para cualquier valor x en el rango [-1, 1],
    utilizando los primeros n términos de la serie de Maclaurin.

    Parámetros:
    x -- El valor para el cual se desea aproximar la función arcotangente. Debe estar en el rango [-1, 1].
    n -- El número de términos de la serie de Maclaurin que se utilizarán para la aproximación.

    Retorna:
    El valor de la aproximación de la función arcotangente alrededor de 0 para el valor de x dado.
    """

    # Verificar que el valor de x esté en el rango [-1, 1]
    if x < -1 or x > 1:
        raise ValueError("El valor de x debe estar en el rango [-1, 1].")

    # Inicializar el resultado en 0
    resultado = 0

    # Utilizar un bucle for para sumar los primeros n términos de la serie de Maclaurin
    for i in range(n):
        # Calcular el término actual de la serie de Maclaurin
        termino = (-1)**i * x**(2*i + 1) / (2*i + 1)
        # Agregar el término actual al resultado
        resultado += termino

    # Devolver el resultado de la aproximación
    return resultado

if __name__ == "__main__":
    # Pedir al usuario que ingrese el valor de x y el número de términos de la serie de Maclaurin
    x = float(input("Ingrese el valor de x (debe estar en el rango [-1, 1]): "))
    n = int(input("Ingrese el número de términos de la serie de Maclaurin que se utilizarán para la aproximación: "))

    # Calcular el valor real de la función arcotangente para x
    valor_real = math.atan(x)

    # Calcular la aproximación utilizando la función arcotangente_aprox
    aproximacion = arcotangente_aprox(x, n)

    # Imprimir el valor real, la aproximación y la diferencia entre ellos
    print(f"Valor real: {valor_real}")
    print(f"Aproximación: {aproximacion}")
    print(f"Diferencia: {abs(valor_real - aproximacion)}")
```
