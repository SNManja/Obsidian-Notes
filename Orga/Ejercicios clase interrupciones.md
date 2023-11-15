Monitoreo montaña rusa
Tiene 2 dispositivos E/S que actúan como sensores, una alarma y otro que efectúa una parada de emergencia.
Cada  sensor posee un registro de E/S que reporta lo siguiente:
- Velocidad: VEL_STATUS
- Frenos: BR_STATUS
Tenemos 2 etiquetas contantes MAX_SPEED y MIN_BRAKES que son constantes de 16 bits
La alarma posee un registro ALARMA con el que se activan las alarmas al setearse algún bit en 1.
- El bit menos significativo representa la alarma de velocidad, que indica que esta yendo muy rápido.
- El segundo bit representa el estado de los frenos comunes  e indica que hubo un problema con ellos. Se activan los frenos de emergencia y se apagan las alarmas manualmente.
Para activar los frenos de emergencia se setean todos los bits en 1 de FRENOS_EM

1. Mapear los registros de E/S a direcciones de E/S de ORGA1i.
	Tenemos la alarma y la parada de emergencia
	Digamos que la alarma esta en R0 y el de parada en R1

2. Realizar el código para sensar y activar las alarmas correspondientes. 
	En este caso tenemos en cuenta que Orga1i tiene manejo de interrupciones y que no hace polling.
	
```NASM

// Podria el dispositivo avisarme cuando la alarma esta prendida que es cuando me interesa, pero en este caso parece que no es asi.

_int: 
	MOV R0 VEL_STATUS
	MOV R1 BR_STATUS
	MOV R2 0x0000
	// En R2 voy a guardar los datos de la alarma
	CALL CHECKVEL
	CALL CHECKBR
	

CHECKVEL:
	CMP R0 MAX_SPEED
	JLE ADDSpeedALRM // si R0 < MAX_SPEED
	RET

CHECKBRK:
	CMP MIN_brakes R1
	JLE ADDBrakeALRM // si R0 < MAX_SPEED
	RET

ADDSpeedALRM:
	AND R2 0xFFFE
	ADD R2 0x0001
	RET

ADDBrkALRM:
	AND R2 0xFFFD
	ADD R2 0x0002
	RET
```
