# 3.4 Practica 3: PicoW Wi-Fi Server

```
#include <WiFi.h>

// Reemplaza estos valores con tu SSID y contraseña
const char* ssid = "ete";         
const char* password = "elefante";

void setup() {
  Serial.begin(115200);  // Inicia la comunicación serie a 115200 baudios
  delay(10);             // Pequeña demora para asegurar que la comunicación serie está lista
  
  Serial.println("Iniciando...");  // Mensaje inicial
  
  // Conectar a la red WiFi
  Serial.print("Conectando a ");
  Serial.println(ssid);

  WiFi.begin(ssid, password);  // Inicia la conexión WiFi

  int attempt = 0;  // Contador de intentos de conexión
  while (WiFi.status() != WL_CONNECTED) {
    delay(500);
    Serial.print(".");
    attempt++;
    if (attempt >= 60) {  // Intentar conectar por 30 segundos (60*500ms)
      Serial.println();
      Serial.println("No se pudo conectar a WiFi");
      return;
    }
  }

  Serial.println();
  Serial.println("WiFi conectado");
  Serial.print("Dirección IP: ");
  Serial.println(WiFi.localIP());  // Imprime la dirección IP obtenida
}

void loop() {
  // Aquí va el código principal
}
```

![imagen](https://i.imgur.com/mzHZzR5.png)
