
```
/*
Title: Hola Mundo en Raspberry Pi Pico W   
Filename: holaMundo
Autor: Abraham García
Date: 19/03/2024
Description: Impresión de Hola Mundo
Imput: -
Ouput: Hola Mundo
*/

´´´
void setup() {
  // Inicializar comunicación serial
  Serial.begin(115200);
}

void loop() {
  // Enviar "Hola Mundo" cada segundo
  Serial.println("Hola Mundo");
  delay(1000); // Esperar un segundo
}

```

![image](https://github.com/Eli-kopter/Equipo-RICOS2/assets/158227726/2fd7e494-bd09-44d3-8813-b1ea7c94e39a)
