---
layout: post
title: Desafío Java número 2
date: 2020-05-26 21:00:00
categories: desafios java
tags: metodos strings
published: false
---
☕ Nuevo desafío Java: si desciframos lo que hace este método, sabremos qué retorna ante el argumento pasado en la llamada...

<details><summary>Click aquí para desplegar la solución. 👈</summary>
<br />✅ La respuesta correcta es la b).
<br />
<br />✏️ Explicación: el método recibe un arreglo de String y retorna el String más largo contenido en el arreglo. Para esto, itera por todos los elementos, quedándose con el primero que tenga la mayor longitud.
<br />
<br />🚫 Respuestas incorrectas:
<br />a) "junio" tiene la mayor longitud de todos los elementos en el arreglo (5 caracteres), pero también la tienen los strings "abril" y "julio". Dado que la comparación se hace como cadena.length() > long_mas_l y no como cadena.length() >= long_mas_l, cuando la longitud de "junio" se compara con la de "abril", al no ser mayor, el valor almacenado en la variable mas_l no se reemplaza.
<br />c) "mayo" es un String de 4 caracteres y hay otros con 5 caracteres dentro del arreglo, por lo que no es el más largo.
<br />
<div markdown="1">💻 [Código ejecutable](https://repl.it/@programacionde1/Java-Desafio-2){:target="_blank"}
  </div>
<br />
<div markdown="1">![Solución al desafío]({{ site.url }}/assets/2020-05-25-desafio-java-2-solucion.png)
  </div></details>

<br />
<br />
**Desafío Java** 👇
![Desafío Java número 2]({{ site.url }}/assets/2020-05-25-desafio-java-2.png)
