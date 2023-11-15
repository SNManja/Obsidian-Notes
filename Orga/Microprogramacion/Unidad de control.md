La unidad de control es la que maneja las señales de control según el microprograma que tenga asignado a respectivo opcode. Este maneja su propio pc, el micro PC. 
Las salidas de la unidad de control van cableadas a los bits de cada palabra en la memoria interna.

### micro PC
Por defecto este se incrementa de a uno la posición de memoria a ser leída. Las salidas de control que pueden modificar su comportamiento son <b>load_microOp, reset_microOp</b>. 
Este siempre comienza en 00000, con load se carga la nueva operación, con reset se prepara para la próxima.

### Condicionales
Como hacemos en un caso como 
```RTL
IF Z=1 
	PC := DE_imm
```
Vamos a sobrescribir el valor del micro PC solo si se encuentra habilitada la señal correspondiente en la ALU. 
![[Pasted image 20231026180129.png]]

#### Nota para el TP 
![[Pasted image 20231026175407.png]]