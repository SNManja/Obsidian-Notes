 - Vienen de los arboles digitales
 - Árbol (K+1)ario para alfabetos de k elementos
 - Los ejes del árbol toman interés: representan componentes de las claves (por ej. si las claves son strings los ejes representan caracteres, si son enteros representan dígitos o bits)
 - Cada subárbol representa al conjunto de claves que comienza con las etiquetas de los ejes que llevan hasta el
 - Los nodos internos no contienen claves, solo las hojas pueden tener claves (tampoco siempre es así).

### Propiedades principales
- La estructura del trie es igual sin importar el orden de las claves
- La búsqueda/inserción de un trie es construido a partir de n claves de b bits. Necesita log n comparaciones de bits en promedio y b comparaciones en el peor caso.

### Versiones optimizadas usadas en practica
- Tries compactos: Cuando los nodos tiene todos un único hijo compacto el árbol a la palabra
	![[Pasted image 20231106184549.png]]
- Tries Patricia: Viene de la sigla Practical Algorithm To Retrieve Información Coded Alphanumeric. Acorta los caminos de solo una letra
	![[Pasted image 20231106184924.png]]

