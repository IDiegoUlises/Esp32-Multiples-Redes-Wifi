# Esp32-Multiples-Redes-Wifi

```c++
#include <WiFi.h>
#include <WiFiMulti.h>

WiFiMulti wifiMulti;

void setup()
{
  Serial.begin(115200);
  delay(10);

  wifiMulti.addAP("ssid_1", "your_password");
  wifiMulti.addAP("ssid_2", "your_password");
  wifiMulti.addAP("ssid_3", "your_password");

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
