Title: Hola Mundo en Raspberry Pi Pico W   
Filename: holaMundo
Autor: Abraham García
Date: 19/03/2024
Description: Impresión de Hola Mundo
Imput: -
Ouput: Hola Mundo

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
