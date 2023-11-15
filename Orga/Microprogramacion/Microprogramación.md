En la arquitectura de la materia, esta parte se ve representada por la [[Unidad de control]]. Estas son secuencias de instrucciones quemadas en el procesador en una memoria no modificable (ROM) que operan como un pequeño programa aparte y manejan al funcionamiento total del CPU por medio de la activación y desactivación de señales de control.

### RTL (Register Transfer language)
Sabemos que cada instrucción esta formada por un conjunto de microoperaciones. Estas las representamos con RLT.
Ejemplo (Fetch en Marie)
	t1:MAR<-\[PC\] 
	t2:MBR<-mem\[MAR\],PC<-PC+1 
	t3:IR<-\[MBR\]

