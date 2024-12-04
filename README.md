Este código simula el control de un sistema de elevador, utilizando un microcontrolador compatible con Arduino. Incluye detección de pisos, selección de pisos mediante botones y un teclado de membrana, además de un mecanismo de parada de emergencia.

Descripción del Código
Componentes del Hardware
Motores

Pines motorUp y motorDown controlan la dirección del motor (subida/bajada).
Control por PWM para ajustar la velocidad (analogWrite).
Sensores de piso

Pines floorSensorX detectan la posición actual del elevador.
Botones de selección de piso

Pines floorButtonX para seleccionar el piso destino.
Buzzer

Pin buzzer para emitir un sonido en caso de emergencia.
Teclado de membrana

Conecta un teclado matricial de 4x4 para selección de pisos y control.
Display TM1637

Muestra el piso actual del elevador.
Flujo del Programa
1. Inicialización
Configura los pines como entradas o salidas.
Inicia el display TM1637 y ajusta el brillo.
2. Identificación del Piso Actual
Verifica el estado de los sensores de piso (floorSensorX).
Actualiza la variable currentFloor con el piso detectado.
Muestra el piso actual en el display.
3. Selección de Piso
Detecta si un botón físico o una tecla del teclado es presionado.
Actualiza la variable targetFloor según el piso seleccionado.
4. Movimiento del Elevador
Compara currentFloor con targetFloor:
Si el destino está por encima, activa motorUp para subir.
Si el destino está por debajo, activa motorDown para bajar.
Si el elevador ya está en el destino, detiene los motores.
5. Emergencia
Detecta si se presiona el botón de emergencia (A en el teclado):
Detiene los motores.
Activa el buzzer para alertar de la emergencia.
Establece emergencyStop = true.
6. Respuesta a Teclado
Procesa entradas del teclado para selección de pisos o activación de emergencia.
Variables Clave
currentFloor: Piso actual detectado por los sensores.
targetFloor: Piso al que debe dirigirse el elevador.
emergencyStop: Bandera para manejar el estado de emergencia.
motorSpeed: Velocidad del motor, controlada por PWM.
