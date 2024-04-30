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
