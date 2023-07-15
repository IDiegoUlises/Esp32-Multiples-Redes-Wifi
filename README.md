# Esp32-Multiples-Redes-Wifi

```c++
#include <WiFi.h>
#include <WiFiMulti.h>

WiFiMulti wifiMulti;

void setup()
{
  Serial.begin(115200);
  delay(10);

  wifiMulti.addAP("ssid_1", "password");
  wifiMulti.addAP("ssid_2", "password");
  wifiMulti.addAP("ssid_3", "password");

  Serial.println("Conectando WiFi...");
  if (wifiMulti.run() == WL_CONNECTED) 
  {
    Serial.println("");
    Serial.println("WiFi Conectado");
    Serial.println("IP address: ");
    Serial.println(WiFi.localIP());
  }
}

void loop()
{
  if (wifiMulti.run() != WL_CONNECTED)
  {
    Serial.println("WiFi no conectado!");
    delay(1000);
  }
}
```
* Este codigo realiza la conexion WiFi con las redes disponibles del dispositivo en caso que una red no este disponible se conectara a la segunda red asi sucesivamente ademas el orden en el cual es definida es la preferencia de conexion
