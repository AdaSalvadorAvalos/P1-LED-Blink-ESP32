# Práctica 1

## MATERIALES
- ESP32
- LED
- resistencia de 470ohms

## Presentación:
En esta práctica usamos el Plataform.io, he entendido el setup para incializar el LED y el bucle: void loop() que provoca que el LED se encienda y apague.

## Explicación del código: 
```
#include <Arduino.h>

//conecta el led 13 al pin 13
int led = 13;
void setup() {
  // inicializa el pin como OUTPUT
  pinMode(led, OUTPUT); 
}

void loop() {
 digitalWrite(led, HIGH);   // enciende el LED: HIGH, se refiere al voltaje
  delay(500);               // y espera 500ms
  digitalWrite(led, LOW);    // apaga el LED : off, voltaje en LOW
  delay(1000);               // y espera otros 1000ms
}
//de esta manera lo que se provoca es un bucle infinito de encender y apagar LEDs, algo así como un parpadeo.
```
Diagrama de flujos
```mermaid
flowchart TD
 id1([Codificación])
 id2([Build])
 id3([Conectar bien todos los componentes])
 id4([mensaje ON por el puerto])
  id5([mensaje OFF por el puerto])
   id7{encender LED}
    id8{Apagar LED}
 id6([Upload])
id1-->id3;
id3-->id2;
id2-->id6;
id6-->id7;
id7-->id4;
id4-->|Esperar 500ms|id8;
id8-->id5;
id5-->|Esperar 500ms|id7;
```

Diagrama de tiempos


![pr1timingdiagram](https://user-images.githubusercontent.com/100204789/160293699-6140ff81-15e0-44b8-9181-d3ed38781bfa.png)
