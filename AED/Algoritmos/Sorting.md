Tenemos varios algoritmos de ordenamiento. 
## Selection Sort
Por cada elemento i, busca el elemento mas chico entre i y fin del arreglo. Una vez encontrado si arr\[i] > arr\[min] los intercambia. Es O(n\*\*2)
## Insertion sort
Por cada elem i checkea si el elemento adelante suyo es menor, si es así lo mueve a la posición indicada. Es O(n\*\*2)
## Heap sort 
Aplica Floyd para sortear el array y convertirlo en [[Heap]]. De ahí extrae cada elemento y lo deja al final del array. Sorteando el array de mayor a menor si es un minHeap y de menor a mayor si es un maxHeap. Es O(n\*log(n))
## Merge sort
Diseñado con metodología [[Divide & Conquer]]. Tiene sentido si la división y la combinación no sean excesivamente caras.
- Si el n < 2 el arreglo esta ordenado
- En caso contrario:
	- Dividir el arreglo en dos partes iguales
	- Ordenar recursivamente(con el mismo algoritmo) ambas mitades
	- Fundir ambas mitades ya ordenadas en un único arreglo
![[Pasted image 20231114000742.png]]
![[Pasted image 20231114001229.png]]
### Análisis temporal en Merge sort
Hay que recalcar que como este algoritmo usa recursividad, acá el análisis temporal es diferente al enseñado en clase. Podemos ver como se llama de nuevo T(n/2) eso hace que se sea la misma expresión que T(n) toda dividida 2.  
Así se ve un patrón logarítmico, sabemos que vamos a poder dividir por 2 un total de log2(n) veces. Como el Merge en cada uno de estos arreglos ordenados es O(n-1), sería O(n\*log(n)). 

## Quick Sort
Similar a Merge sort, también [[Divide & Conquer]]. Envés de partir todo por la mitad buscamos dividir todo en si es mayor o menor a un elemento particular, el elemento mediano. Si encontramos el mediano en tiempo lineal se ve que es O(n\*log(n)). 
Encontrar el elemento mediano tiene mucho overhead (Espacio o tiempo adicional para realizar una operación). Si tomamos un elemento aleatorio en el array esto cambia. En la practica funciona mas rápido, pero no nos permite acotarlo como eficiente.

## Radix sort y Counting sort
Son algoritmos que no se tocan en clase, pero que van por abajo de la cota de omega(n\*log(n)). Funcionan solo para enteros