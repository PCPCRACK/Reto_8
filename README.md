# Reto_8
1. Imprimir un listado con los números del 1 al 100 cada uno con su respectivo cuadrado.
```python
if __name__ == "__main__":
    # Utilizar un bucle for para imprimir los números del 1 al 100
    for i in range (1,101): 
    
        # Muestra el resultado y eleva al cuadrado el resultado
        print("El numero es",i,"y su cuadrado es",i**2) 
```
2.  Imprimir un listado con los números impares desde 1 hasta 999 y seguidamente otro listado con los números pares desde 2 hasta 1000.
```python
if __name__ == "__main__":
    # Utilizar un bucle for para imprimir los números del 1 al 999 
    for i in range (1,1000,2): #se establece un rango 
        print(i) 
        
    # Utilizar un bucle for para imprimir los números del 2 al 1000
    for i in range (0,1001,2): 
        print(i) 
```
3.  Imprimir los números pares en forma descendente hasta 2 que son menores o iguales a un número natural n ≥ 2 dado
```python
if __name__ == "__main__":
    # Definimos n
    n = int(input("valor inicial ")) 
    
    # Si n no es par le resta 1
    if n%2 != 0: 
        n -= 1 
        
    # Utilizar un bucle for para imprimir los números del n al 1
    for i in range (n,1,-2):
        print(i) 
```
4. Imprimir los números de 1 hasta un número natural n dado, cada uno con su respectivo factorial
```python
if __name__ == "__main__":
    # Definimos n
    n = int(input("valor final "))
    
    if n == 0 or n == 1:
        print("1")
    else:
        # Utilizar un bucle for para imprimir los números del 1 al n
        for i in range (1,n+1): 

            # sum es igual al valor de i
            sum = i 

            # Utilizar un bucle for para multiplicar los números del i-1 al 1
            for a in range (i-1,1,-1):
                sum *= a
            print("El numero es ",i," y su factorial es ",sum)
```
Version alterna a ese codigo
```python
if __name__ == "__main__":
    # Definimos n,a,i y t
    n = int(input("Ingrese numero final: ")) 
    a = 1
    i = 1
    t = 1

    # Mientras a sea menor que n
    while a <= n: 

        # Minetras i sea menor que a
        while i <= a: 
            t *= i
            i += 1

        # Muestra los resultados
        print ("el factoria de ",a," es ",t) 

        # Se restablecen los valores de t y i
        t = 1 
        i = 1

        # Se suma 1 a a
        a += 1 
```
5. Calcular el valor de 2 elevado a la potencia n usando ciclos for.
```python
if __name__ == "__main__":
    # Definimos n y sum
    n = int(input("valor ")) 
    sum = 2
    
    # Utilizar un bucle for para multiplicar por 2, n cantidad de veces
    for i in range (1,n+1):
        
        #i dentro del bucle coje un valor de 2, que no afecta el valor de i en for
        i = 2
        sum *= i
    
    # Muestra el resultado
    print (sum) 
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

    # Imprimir el resultado
    print(x,"^",n,"=",resultado)
```
7. Diseñe un programa que muestre las tablas de multiplicar del 1 al 9.
```python
if __name__ == "__main__":
    # Iterar por cada número del 1 al 9
    for i in range(1, 10):
        
        # Imprimir el encabezado de la tabla
        print("Tabla del", i)
        
        # Iterar por cada número del 1 al 10
        for j in range(1, 11):
            
            # Calcular el producto de i y j y mostrarlo en la consola
            print(i,"x",j,"=",i*j)
            
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
