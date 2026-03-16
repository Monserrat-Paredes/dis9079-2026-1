# sesion-02

lunes 16 marzo 2026

---

04-06 primera solemne de Interacción digital

Grupo: Sofía Cartes - Monserrat Paredes - Valentina Ruz

---

## Apuntes 

```bash
bash sirve para copiar directamente lo que escribo / agregarle un botoncito para copiar y pegar
```

`Arduino IDE`

- Void: vacío
- Loop: repetir
- Setup: se configura


- Nomenclatura `Semver:` es la versión de un software que utiliza tres números (mayot.menor.parche) para indicar la magnitud de los cambios de un software
- Homebrew: se creó para poder instalar cosas en la terminal del computador (deberíamos instalarla)
- Usaremos el Arduino UNO R4 wifi

Todo lo que escribimos en Arduino es en lenguaje c++

OSC:

MQTT: los arduino se conectaran a traves de mosquitto y se enviaran cosas desde mosquitto

---

**EJEMPLO 01**

- Código para escribir textos en la pantalla de Arduino
- 
```cpp
// ejemplo01
// imprime la sigla del curso en la pantalla led
// de la Arduino Uno R4 WiFi
// basado en
// https://docs.arduino.cc/tutorials/uno-r4-wifi/led-matrix/#scrolling-text-example
// marzo 2026
// por montoyamoraga para disenoUDP

// incluir bibliotecas
#include <ArduinoGraphics.h>
#include "Arduino_LED_Matrix.h"

// declarar instancia de ArduinoLEDMatrix
// con nombre pantalla
ArduinoLEDMatrix pantalla;

void setup() {

  // iniciar puerto serial
  Serial.begin(115200);

  // inicializar pantalla
  pantalla.begin();

}

void loop() {

  // definir nuevo dibujo
  pantalla.beginDraw();

  // definir trazo
  pantalla.stroke(0xFFFFFFFF);

  // definir velocidad de deslizamiento
  pantalla.textScrollSpeed(100);

  // definir texto
  const char texto[] = "    diseno udp dis9704 interacciones inalambricas    ";
  
  // definir tipo
  pantalla.textFont(Font_5x7);

  // definir inicio del texto
  pantalla.beginText(0, 1, 0xFFFFFF);

  // imprimir el texto
  pantalla.println(texto);

  // deslizar hacia la izquierda
  pantalla.endText(SCROLL_LEFT);

  // fin del dibujo
  pantalla.endDraw();
}
```
