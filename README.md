# Esp32-Multiples-Redes-Wifi

### Codigo no probado y falta descargar las librerias
```c++
#include <Wifi.h>
#include <WiFiMulti.h>

WiFiMulti wifi;


void setup() {

wifi.addAP("ssid","Paswwrod"); //red 1
wifi.addAP("ssid2","Paswwrod"); //red 2

//buscar una forma para verificar que existaa internet y se conecte 
//a la red que tenga internet
}

void loop() {
  // put your main code here, to run repeatedly:

}
```
