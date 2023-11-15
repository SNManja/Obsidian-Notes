Maneja el acceso a memoria aparte de la CPU y le prepara los datos para cuando los necesita. La idea es poder extrapolar las tareas de la I/O del CPU y que las pueda administrar el DMA mientras el CPU se dedica a hacer otras cosas.
Sin la DMA el CPU al estar usando [[Programmed Input-Output (PIO)]] esta ocupado a lo largo de toda la operación de Read/Write. Cuando al DMA termina de procesar lo necesitado, manda una interrupción a la CPU.

![[Pasted image 20231026030341.png]]

En las arquitecturas Intel se usaba 8237A como Programmable DMA Controller

### Limitaciones
Cuando los discos se hicieron mucho mas grandes, es que el DMA termina generando bottleneck. Gracias a esto mas adelante nace el Ultra DMA. 

### Usos
No solo se usa al nivel CPU, si no que también se usan dentro de tarjetas graficas, tarjetas de red y tarjetas de sonido. Además en algunas arquitecturas, es el medio por el que se comunican entre hilos de procesador en CPUs multi núcleo.