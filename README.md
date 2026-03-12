# Sensor Ultrasónico HC-SR04 con Alarma LED Rojo

![Arduino](https://img.shields.io/badge/Arduino-UNO-blue?style=flat&logo=arduino&logoColor=white)
![HC-SR04](https://img.shields.io/badge/Sensor-HC--SR04-green?style=flat)
![C++](https://img.shields.io/badge/C%2B%2B-Embedded-red?style=flat&logo=c%2B%2B&logoColor=white)

Proyecto físico con Arduino: mide la distancia a un objeto usando sensor ultrasónico HC-SR04 y enciende un **LED rojo** cuando está demasiado cerca (menos de 20 cm). Muestra la distancia en tiempo real en el Monitor Serial.

Ideal para alarmas de proximidad, robots anti-choque o proyectos IoT básicos.

## Características
- Medición precisa de distancia (2 cm a ~400 cm)
- Alarma visual (LED rojo) en zona crítica
- Actualización cada 200 ms
- Código limpio y comentado
- Fácil de modificar (cambia distancia crítica en una variable)

## Hardware utilizado
- Arduino UNO (o compatible)
- Sensor ultrasónico HC-SR04
- LED rojo + resistencia 220–330 Ω
- Cables jumper y breadboard

## Conexiones
- HC-SR04 VCC → 5V  
- HC-SR04 GND → GND  
- HC-SR04 Trig → Pin 9  
- HC-SR04 Echo → Pin 10  
- LED rojo (ánodo) → Pin 13 + resistencia → GND

## Fotos del prototipo

![ultrasonico1](https://github.com/user-attachments/assets/91e059fa-34f3-48f5-a811-9fc8489403fa)
![ultrasonico3](https://github.com/user-attachments/assets/30d57fa9-06df-45a9-8735-b2c2a3fe7784)
![ultrasonico2](https://github.com/user-attachments/assets/8fd85b7d-fa7a-4f50-90e5-0258895bfc86)


## Video de funcionamiento
[Ver demo en YouTube](https://youtube.com/shorts/paYnZs_GQvg?feature=share)  


## Cómo replicar
1. Clona este repositorio
2. Abre `src/main.cpp` en Arduino IDE o PlatformIO
3. Conecta el hardware como se indica
4. Sube el código a tu Arduino
5. Abre Monitor Serial (9600 baudios) y prueba acercando objetos

## Código destacado
```cpp
if (distancia > 0 && distancia < distanciaCritica) {
  digitalWrite(ledRojo, HIGH);
  Serial.println("¡ALERTA! Objeto en zona crítica");
} else {

Disponible para proyectos freelance similares en Workana: sensores de distancia, alarmas, automatización, IoT básico con Arduino/ESP32.
¡Contáctame para colaboraciones!
Hecho con ❤️ por Juan David Moreno Jurado
📍 Zarzal / Cali, Valle del Cauca, Colombia
GitHub: github.com/JuanDavid-electronics
  digitalWrite(ledRojo, LOW);
}
