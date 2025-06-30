# Examen-de-Electronica "Punto de encuentro"
Procesos del examen

# Decisiones e ideas
Micro problemática: Esquina de mi casa = lugar de 'encuentro'
Problema social específico que ocurre fuera de mi casa, donde veo constantemente personas drogandose toda la noche la mayor parte de los días, una realidad donde no depende de mi hacer algo, pero si decido verlos y comprender su situación, finalmente a la que todos llegan lamentablemente
- Medio: Acrílico sobre lienzo
- Ampolletas Verde, Azul y Rojo junto con relé (programación)
Con ambos materiales hice una pintura dependiente de la luz que encienda, donde aparece y desaparecen distintos estados de la zona
Fotos del pre examen:
![20250610_165645](https://github.com/user-attachments/assets/0dfd3019-518b-4a75-92e2-83301781a05b)
![20250610_165633](https://github.com/user-attachments/assets/b9245cee-1d71-4221-ba7c-9c2c0e7ec689)
![20250610_165626](https://github.com/user-attachments/assets/69b05e8d-f942-43e7-9214-816492b24cee)
Código pre examen:
int ledRojo = 3;

int ledVerde = 5;

int ledAzul = 6;

void setup() {

pinMode(ledRojo, OUTPUT);

pinMode(ledVerde, OUTPUT);

pinMode(ledAzul, OUTPUT);

}

void loop() {

fadeToColor(0,0,250);   // azul

delay(10500);

fadeToColor(5,213,255);   // celeste

delay(150);

fadeToColor(0,250,0);   // verde

delay(10500);

fadeToColor(254,115,6);   // naranja

delay(150);

fadeToColor(250,0,0);   // rojo

delay(10500);

fadeToColor(136,5,255);   // morado

delay(150);

}

void fadeToColor(int r, int g, int b) {

// Obtener valores actuales

int currentR = analogRead(ledRojo);

int currentG = analogRead(ledVerde);

int currentB = analogRead(ledAzul);

// Pero analogRead no lee PWM, mejor guardamos los valores antes

// Mejor declaramos variables globales para guardar el estado actual

static int currentR_ = 0;

static int currentG_ = 0;

static int currentB_ = 0;

int steps = 100; // número de pasos para la transición

for (int i = 0; i <= steps; i++) {

int valR = currentR_ + (r - currentR_) * i / steps;

int valG = currentG_ + (g - currentG_) * i / steps;

int valB = currentB_ + (b - currentB_) * i / steps;

analogWrite(ledRojo, valR);

analogWrite(ledVerde, valG);

analogWrite(ledAzul, valB);

delay(10);

}

currentR_ = r;

currentG_ = g;

currentB_ = b;

}

Final:
![20250629_045907](https://github.com/user-attachments/assets/373966c9-28eb-4ec9-8f83-5e245a888709)
![20250629_045704](https://github.com/user-attachments/assets/ba872ca1-87fe-489a-9fd5-7e95b8d00cde)
![20250629_045654](https://github.com/user-attachments/assets/1e7045a0-5d92-4e83-b1ed-98e7c8399733)

código final:
void setup() {

  pinMode(9, OUTPUT);
}

void loop() {
  digitalWrite(9, HIGH);   
  delay(10000);            // Espera 10 segundos 
  digitalWrite(9, LOW);    // Apaga el LED
  delay(10000);            // Espera otros 10 segundos
}




