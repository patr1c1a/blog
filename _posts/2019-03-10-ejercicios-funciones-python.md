---
layout: post
title: Ejercicios resueltos de funciones en Python
date: 2019-03-10 23:53
categories: ejercicios python
tags: algoritmo estructura funciones
published: true
---

Acá encontrarás ejercicios para practicar programar usando funciones.

En los siguientes videos podrás ver una explicación del tema y también la resolución paso a paso de estos ejercicios:
+ [Funciones](https://www.youtube.com/watch?v=IF34NgjldXs)
+ [Ejemplos de funciones](https://www.youtube.com/watch?v=ivcnLfOkbrU)
+ [Errores comunes con funciones](https://youtu.be/LD61E3g6GjM)
+ [Ejercicios con funciones](https://www.youtube.com/watch?v=Uze9KWL6ZGs)
+ [Ejercicio con varias funciones](https://www.youtube.com/watch?v=N_-YhYH_DyU)

La resolución de cada ejercicio se muestra al hacer click sobre la consigna.

### 1
<details> 
  <summary>Solicitar al usuario que ingrese su dirección email. Imprimir un mensaje indicando si la dirección es válida o no, valiéndose de una función para decidirlo. Una dirección se considerará válida si contiene el símbolo "@".</summary>
  <br>Solución:
  <pre><code>def validar(email):
    caracterBuscado="@"
    emailValido=False
    for c in email:
        if c==caracterBuscado:
            return True
    return False
<br>&nbsp;
direccion=input("Tu email: ")
if validar(direccion):
    print("Dirección válida")
else:
    print("Dirección inválida")</code></pre>
</details>


### 2
<details> 
  <summary>Solicitar números al usuario hasta que ingrese el cero. Por cada uno, mostrar la suma de sus dígitos (utilizando una función que realice dicha suma).</summary>
<br>Solución:
<pre><code>def sumaDigitos(numero):
    suma=0
    while numero!=0:
        digito=numero%10
        suma=suma+digito
        numero=numero//10
    return suma
<br>&nbsp;
num=int(input("Número a procesar: "))
while num!=0:
    print("Suma:",sumaDigitos(num))
    num=int(input("Número a procesar: "))</code></pre>
</details>



### 3
<details> 
  <summary>Solicitar números al usuario hasta que ingrese el cero. Por cada uno, mostrar la suma de sus dígitos.
Al finalizar, mostrar la sumatoria de todos los números ingresados y la suma de sus dígitos. Reutilizar la misma función realizada en el ejercicio 2.</summary>
<br>Solución:
<pre><code>def sumaDigitos(numero):
    suma=0
    while numero!=0:
        digito=numero%10
        suma=suma+digito
        numero=numero//10
    return suma
<br>&nbsp;
sumatoria=0
num=int(input("Número a procesar: "))
while num!=0:
    print("Suma:",sumaDigitos(num))
    sumatoria=sumatoria+num
    num=int(input("Número a procesar: "))
print("Sumatoria:", sumatoria)
print("Dígitos:", sumaDigitos(sumatoria))</code></pre>
</details>


### 4
<details> 
  <summary>Requerir al usuario que ingrese un número entero e informar si es primo o no, utilizando una función booleana que lo decida.</summary>
<br>Solución:
<pre><code>def primo(num):
   for i in range(2,num):
       if num%i==0:           
           return False
   return True
<br>&nbsp;
numero=int(input("Número: "))
if primo(numero):
    print("Es primo")
else:
    print("No es primo")</code></pre>
</details>


### 5
<details> 
  <summary>Solicitar al usuario un número entero y luego un dígito. Informar la cantidad de ocurrencias del dígito en el número, utilizando para ello una función que calcule la frecuencia.</summary>
<br>Solución:
<pre><code>def frecuencia(numero,digito):
   cantidad=0
   while numero!=0:
       ultDigito=numero%10
       if ultDigito==digito:
           cantidad+=1
       numero=numero//10
   return cantidad
<br>&nbsp;
num=int(input("Número: "))
un_digito=int(input("Dígito: "))
print("Frecuencia del dígito en el número:",frecuencia(num,un_digito))</code></pre>
</details>


### 6
<details> 
  <summary>Escribir un programa que pida números al usuario, motrar el factorial de cada uno y, al finalizar, la cantidad total de números leídos en total. Utilizar una o más funciones, según sea necesario.</summary>
<br>Solución:
<pre><code>def factorial(numero):
   f=1
   if numero!=0:
       for i in range(1,numero+1):
           f=f*i
   return f
<br>&nbsp;
cantidad=0
num=int(input("Número (-1 para cortar): "))
while num!=-1:
    print("Factorial:", factorial(num))
    cantidad+=1
    num=int(input("Número (-1 para cortar): "))
print("Se leyeron",cantidad,"números")</code></pre>
</details>


### 7
<details> 
  <summary>Escribir un programa que pida números positivos al usuario. Mostrar el número cuya sumatoria de dígitos fue mayor y la cantidad de números cuya sumatoria de dígitos fue menor que 10. Utilizar una o más funciones, según sea necesario.</summary>
<br>Solución:
<pre><code>def sumaDigitos(numero):
  suma=0
  while numero!=0:
      digito=numero%10
      suma=suma+digito
      numero=numero//10
  return suma
<br>&nbsp;
cantidad=0
mayor=-1
numero=int(input("Número positivo: "))
while numero>=0:
    suma=sumaDigitos(numero)
    if suma > mayor:
          mayor=suma
          n_mayorsuma=numero
    if suma < 10:
        cantidad+=1
    numero=int(input("Número positivo: "))
print("Sumatoria de dígitos de",n_mayorsuma,":",mayor)
print("Cantidad con sumatoria menor a 10:",cantidad)</code></pre>
</details>


### 8
<details> 
  <summary>Solicitar al usuario el ingreso de números primos. La lectura finalizará cuando ingrese un número que no sea primo. Por cada número, mostrar la suma de sus dígitos. También solicitar al usuario un dígito e informar la cantidad de veces que aparece en el número (frecuencia). Al finalizar el programa, mostrar el factorial del mayor número ingresado.</summary>
<br>Solución:
<pre><code>def primo(num):
   for i in range(2,num):
       if num%i==0:           
           return False
   return True
<br>&nbsp;
def frecuencia(numero,digito):
   cantidad=0
   while numero!=0:
       ultDigito=numero%10
       if ultDigito==digito:
           cantidad+=1
       numero=numero//10
   return cantidad
<br>&nbsp;
def factorial(numero):
   f=1
   if numero!=0:
       for i in range(1,numero+1):
           f=f*i
   return f
<br>&nbsp;
def sumaDigitos(numero):
  suma=0
  while numero!=0:
      digito=numero%10
      suma=suma+digito
      numero=numero//10
  return suma
<br>&nbsp;
mayor=0
numero=int(input("Número primo: "))
while primo(numero):
    print("Suma de los dígitos:",sumaDigitos(numero))
    digito=int(input("Dígito: "))
    print("El",digito,"aparece",frecuencia(numero,digito),"veces")
    if numero > mayor:
          mayor=numero
    numero=int(input("Número primo: "))
print("Factorial de",mayor,":",factorial(mayor))</code></pre>
</details>


### 9
<details> 
  <summary>Sin ejecutar el siguiente programa, determinar cuál es la salida en pantalla si se ingresan los valores x=6, y=7:
<pre><code>def coordenadaZ(x,y):
  x=x+10
  y=y+15
  return x+y
<br>&nbsp;
#programa principal
x=int(input("Coordenada eje x: "))
y=int(input("Coordenada eje y: "))
for i in range(3):
  z=coordenadaZ(x,y)
  x=x+1
  y=y+1
print(x," . ",y)</code></pre></summary>
<br>Solución: 9 . 10
</details>


### 10
<details> 
  <summary>El siguiente programa debería imprimir el número 2 si se le ingresan como valores x=5, y=1 pero en su lugar imprime 5. ¿Qué hay que corregir?
<pre><code>def maximo(a,b):
  if x>y:
    return x
  else:
    return y
<br>&nbsp;
def minimo(a,b):
  if x<y:
    return x
  else:
    return y
<br>&nbsp;
#programa principal
x=int(input("Un número: "))
y=int(input("Otro número: "))
print(maximo(x-3, minimo(x+2, y-5)))</code></pre></summary>
<br>Solución: Las funciones no utilizan sus parámetros a, b sino las variables globales x, y. Para corregir el error se deben utilizar los parámetros dentro del cuerpo de ambas funciones.</details>



### 11
<details> 
  <summary>Escribir una función que, dado un número de DNI, retorne True si el número es válido y False si no lo es.
Para que un número de DNI sea válido debe tener entre 7 y 8 dígitos.</summary>
<br>Solución:
<pre><code>def validarDNI(dni):
   cantidad=0
   while dni!=0:
       cantidad+=1
       dni//=10
   return cantidad==7 or cantidad==8</code></pre>
</details>




### 12
<details> 
  <summary>Escribir una función que, dado un string, retorne la longitud de la última palabra. Se considera que las palabras están separadas por uno o más espacios. También podría haber espacios al principio o al final del string pasado por parámetro.</summary>
<br>Solución:
<pre><code>def lenUltimaPalabra(frase):
   if len(frase)==0:
       return 0
   cantidad=0
   for i in range(len(frase)):
       if frase[i]!=' ':
           cantidad+=1
       else:
           if frase[i]==' ' and i<len(frase)-1 and frase[i+1]!=' ':
               cantidad=0
   return cantidad</code></pre>
</details>




### 12
<details> 
  <summary>Escribir un programa que permita al usuario obtener un identificador para cada uno de los socios de un club. Para eso ingresará nombre completo y número de DNI de cada socio, indicando que finalizará el procesamiento mediante el ingreso de un nombre vacío.
    <br>Precondición: el formato del nombre de los socios será: nombre apellido. Podría ingresarse más de un nombre, en cuyo caso será: nombre1 nombre2 apellido. Si un socio tuviera más de un apellido, el usuario sólo ingresará uno.
    <br>Se debe validar que el número de DNI tenga 7 u 8 dígitos. En caso contrario, el programa debe dejar al usuario en un bucle hasta que ingrese un DNI correcto.
    <br>Por cada socio se debe imprimir su identificador único, el cual estará formado por: el primer nombre, la cantidad de letras del apellido y los primeros 3 dígitos de su DNI. Ejemplo:
    <br>Nombre: Alba María Linares
    <br>DNI: 25834910
    <br>Alba7258</summary>
<br>Solución:
<pre><code>def lenUltimaPalabra(cadena):
   longitud=len(cadena)
   if longitud==0:
       return 0
   cantidad=0
   for i in range(longitud):
       if cadena[i]!=' ':
           cantidad+=1
       else:
           if cadena[i]==' ' and i<(longitud-1) and cadena[i+1]!=' ':
               cantidad=0
   return cantidad
<br>&nbsp;
def DNIvalido(dni):
   cantidad=0
   while dni!=0:
       cantidad+=1
       dni//=10
   return cantidad==7 or cantidad==8
<br>&nbsp;
def primerosTresDigitos(numero):
 while numero >= 1000:
   numero = numero // 10
 return numero
<br>&nbsp;
def obtenerIdentificador(nombre, dni):
   nombre=nombre.strip()
   id=nombre[:nombre.find(" ")]
   id=id+str(lenUltimaPalabra(nombre))
   id=id+str(primerosTresDigitos(dni))
   return id
<br>&nbsp;
#programa principal
nombre=input("Nombre del socio: ")
while nombre!="":
   dni=int(input("DNI del socio: "))
   while !(DNIvalido(dni)):
      print("Número inválido.")
   dni=int(input("DNI del socio: "))
   print(obtenerIdentificador(nombre,dni))
   nombre=input("Nombre del socio: ")</code></pre>
</details>
