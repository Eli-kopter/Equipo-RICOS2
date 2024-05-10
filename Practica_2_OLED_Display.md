
```
#include <Wire.h>
#include <Adafruit_GFX.h>
#include <Adafruit_SSD1306.h>

#define SCREEN_WIDTH 128 // Ancho de la pantalla OLED
#define SCREEN_HEIGHT 64 // Altura de la pantalla OLED

// Declaración del objeto display
Adafruit_SSD1306 display(SCREEN_WIDTH, SCREEN_HEIGHT, &Wire);

void setup() {
  // Iniciar la pantalla OLED
  if (!display.begin(SSD1306_SWITCHCAPVCC, 0x3C)) {  // Asegúrate de que la dirección I2C es correcta (0x3C o 0x3D)
    Serial.println(F("SSD1306 allocation failed"));
    for (;;); // Bucle infinito si falla la pantalla
  }
  
  display.clearDisplay();

  display.setTextSize(3);             // Tamaño del texto
  display.setTextColor(SSD1306_WHITE); // Color del texto
  display.setCursor(0,0);             // Posición inicial del texto
  display.println(F("Somos Abraham, Manuel, Iván y América. Helou"));
  display.display(); // Mostrar todo en la pantalla
}

void loop() {
  
}
```

![WhatsApp Image 2024-05-07 at 3 41 23 PM](https://github.com/Eli-kopter/Equipo-RICOS2/assets/158227726/a7173cbb-a3fd-4cac-aafb-376ed61f0f6f)
