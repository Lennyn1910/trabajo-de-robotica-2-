# trabajo-de-robotica-2-
<img width="998" height="667" alt="image" src="https://github.com/user-attachments/assets/003a81f9-a2e5-4456-864f-81ccf320bd8c" />
const int LED1 = 4;
const int LED2 = 5;
const int LED3 = 6;
const int LED4 = A1;
const int LED5 = A3;
const int LED6 = A2;
const int LED7 = A0;

const int PUSH = 7;

int RESULTADO = 0;

void setup()
{
pinMode(LED1,OUTPUT);
pinMode(LED2,OUTPUT);
pinMode(LED3,OUTPUT);
pinMode(LED4,OUTPUT);
pinMode(LED5,OUTPUT);
pinMode(LED6,OUTPUT);
pinMode(LED7,OUTPUT);
  
pinMode(PUSH,INPUT_PULLUP);
Serial.begin(9600);   
}

void loop()
{ 
  if(digitalRead(PUSH)==LOW)
  {
  RESULTADO = random(1,7);
  Serial.println(RESULTADO);  
  delay(500);  
  } 
  if (RESULTADO==1)
  {
    digitalWrite(LED1,LOW);
    digitalWrite(LED2,LOW);
    digitalWrite(LED3,LOW);
    digitalWrite(LED4,HIGH);
    digitalWrite(LED5,LOW);
    digitalWrite(LED6,LOW);
    digitalWrite(LED7,LOW);
  }
   if (RESULTADO==2)
  {
    digitalWrite(LED1,LOW);
    digitalWrite(LED2,LOW);
    digitalWrite(LED3,HIGH);
    digitalWrite(LED4,LOW);
    digitalWrite(LED5,HIGH);
    digitalWrite(LED6,LOW);
    digitalWrite(LED7,LOW);
  }
   if (RESULTADO==3)
  {
    digitalWrite(LED1,LOW);
    digitalWrite(LED2,LOW);
    digitalWrite(LED3,HIGH);
    digitalWrite(LED4,HIGH);
    digitalWrite(LED5,HIGH);
    digitalWrite(LED6,LOW);
    digitalWrite(LED7,LOW);
  }
   if (RESULTADO==4)
  {
    digitalWrite(LED1,HIGH);
    digitalWrite(LED2,LOW);
    digitalWrite(LED3,HIGH);
    digitalWrite(LED4,LOW);
    digitalWrite(LED5,HIGH);
    digitalWrite(LED6,LOW);
    digitalWrite(LED7,HIGH);
  }
   if (RESULTADO==5)
  {
    digitalWrite(LED1,HIGH);
    digitalWrite(LED2,LOW);
    digitalWrite(LED3,HIGH);
    digitalWrite(LED4,HIGH);
    digitalWrite(LED5,HIGH);
    digitalWrite(LED6,LOW);
    digitalWrite(LED7,HIGH);
  }
   if (RESULTADO==6)
  {
    digitalWrite(LED1,HIGH);
    digitalWrite(LED2,HIGH);
    digitalWrite(LED3,HIGH);
    digitalWrite(LED4,LOW);
    digitalWrite(LED5,HIGH);
    digitalWrite(LED6,HIGH);
    digitalWrite(LED7,HIGH);
  }
}
**Descripción General**

Un circuito interactivo de juego de azar o habilidad (tipo "ruleta" o "juego de reflejos") simulado en Tinkercad. Utiliza una placa Arduino Uno como cerebro central para controlar componentes visuales y auditivos en respuesta a la interacción del usuario.

---

**Función del Sistema**

* **Entrada:** El usuario presiona el pulsador (*push button*).
* **Procesamiento:** El programa activa una secuencia de luces rápida y de ida y vuelta (efecto ping-pong) a través de los cinco LEDs mientras el botón permanezca presionado.
* **Salida:** Al soltar el botón, el ciclo se detiene inmediatamente en una posición aleatoria o fija, dejando encendido un solo LED para indicar el resultado final y activando una señal sonora con el zumbador.

---

**Componentes Principales**

* **Arduino Uno:** Microcontrolador encargado de ejecutar la lógica del código y suministrar alimentación.
* **5 LEDs Rojos:** Indicadores luminosos conectados a las salidas digitales.
* **5 Resistencias (220 $\Omega$ - 330 $\Omega$):** Conectadas en serie a los LEDs para limitar la corriente y evitar que se quemen.
* **1 Pulsador (Push Button):** Interrupter que genera la señal de entrada al Arduino.
* **1 Resistencia (10 k$\Omega$):** Configurada como resistencia *pull-down* para mantener estable la lectura del pulsador en `LOW` hasta que se presione.
* **1 Zumbador Piezoeléctrico (Buzzer):** Emite tonos sonoros para acompañar el evento visual.
* **Protoboard y Cables (Jumper Wires):** Base de pruebas para realizar el cableado sin necesidad de soldadura.
