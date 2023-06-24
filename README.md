# Esp32-Multiples-Redes-Wifi

```c++
#include <WiFi.h>
#include <WiFiMulti.h>

WiFiMulti wifiMulti;

void setup()
{
  Serial.begin(115200);
  delay(10);

  wifiMulti.addAP("ssid_from_AP_1", "your_password");
  wifiMulti.addAP("ssid_from_AP_2", "your_password");
  wifiMulti.addAP("ssid_from_AP_3", "your_password");

  Serial.println("Connecting Wifi...");
  if (wifiMulti.run() == WL_CONNECTED) 
  {
    Serial.println("");
    Serial.println("WiFi connected");
    Serial.println("IP address: ");
    Serial.println(WiFi.localIP());
  }
}

void loop()
{
  if (wifiMulti.run() != WL_CONNECTED)
  {
    Serial.println("WiFi not connected!");
    delay(1000);
  }
}
```
