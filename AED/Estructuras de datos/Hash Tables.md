Con un preHash constante nos simplificamos la indexación. De ahí tenemos diferentes maneras de tratar los choques de valores (valores diferentes con mismo índice).
## Paradoja del cumpleaños
Si tenemos 23 personas hay un 50% de chance de que 2 cumplan el mismo día. Con esto podemos que las colisiones no son algo raro, lo mismo pasa con un sistema de hash tables.
## Direccionamiento cerrado
A la i-ésima posición de la tabla se le asocia una lista de los elementos tales que h(k) = 1
La complejidad de las operaciones en este método seria:
- Insertar(el, k) -> O(1): Insertando al principio
- Buscar(k) -> O(Long de la lista asociada a h(k)) siendo h(k) la posición
- Eliminar(k) -> búsqueda en la lista asociada de posición h(k): costo O(Long de la lista asociada a h(k))
Tener en cuenta que si están equitativamente distribuidos los índices, nos acotamos todas las listas por igual, mejorando el peor caso.
## Direccionamiento abierto
Todos los elemento se guardan en la tabla. Las colisiones se resuelven en la tabla misma, si la posición esta ocupada se busca otra disponible.
Para la resolución de esto hay diferentes métodos de barrido:
- Barrido linear
- Barrido cuadrático
- Hashing doble