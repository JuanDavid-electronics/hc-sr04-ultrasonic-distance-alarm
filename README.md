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

![Montaje completo](images/foto-montaje.jpg)
![Sensor ultrasónico](images/foto-sensor.jpg)
![LED rojo encendido (alerta)](images/foto-led-encendido.jpg)

## Video de funcionamiento
[Ver demo en YouTube](https://youtu.be/TU_VIDEO_ID)  
*(Sube un video corto a YouTube como "no listado" y pega el enlace aquí)*

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
  digitalWrite(ledRojo, LOW);
}
