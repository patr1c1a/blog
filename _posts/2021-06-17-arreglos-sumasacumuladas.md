---
layout: post
title: Ejercicio con arreglos, resuelto en 3 lenguajes
date: 2021-06-17 12:00:00
categories: ejercicios java python c++
tags: arreglos
published: true
---

Sigamos ejercitando con arreglos. ¿Te animas a intentar una resolución antes de leer las que están en la imagen?

🔸 Código ejecutable:

[C++](https://jdoodle.com/a/3pwV){:target="_blank"}

{% include codeEditor.html id="3pwV" %}

[Java](https://jdoodle.com/a/3pwZ){:target="_blank"}

{% include codeEditor.html id="3pwZ" %}

[Python](https://jdoodle.com/a/3px1){:target="_blank"}

{% include codeEditor.html id="3px1" %}


![Ejercicio con arreglos, sumas acumuladas]({{ site.url }}/assets/2021-06-17-arreglos-sumasacumuladas.png)
<hr />
### Versión accesible (apta para lectores electrónicos):

Obtener las sumas acumuladas del arreglo nums tal que sumasAcumuladas[i] = suma(nums[0] .. nums[i]).

Ejemplo:

Entrada: [1,2,3,4]

Salida: [1,3,6,10] (se calcula como: [1, 1+2, 1+2+3, 1+2+3+4])

Posibles soluciones:

C++:
~~~
vector<int> sumasAcumuladas(vector<int> &nums) {
    vector<int> resultado = {nums[0]};
    for (int i = 1; i < nums.size(); i++) {
        resultado.push_back(resultado.back() + nums[i]);
    }
    return resultado;
}
~~~
{: .language-cpp}


Java:

~~~
public int[] sumasAcumuladas(int[] nums) {
    int[] resultado = new int[nums.length];
   resultado[0] = nums[0];
    for (int i = 1; i < nums.length; i++) {
        resultado[i] = resultado [i - 1] + nums[i];
    }
    return resultado;
}
~~~
{: .language-java}


Python:

~~~
def sumasAcumuladas(nums):
    resultado = [nums[0]]
    for i in range(1, len(nums)):
        resultado.append(resultado[-1] + nums[i])
    return resultado
~~~
{: .language-python}
