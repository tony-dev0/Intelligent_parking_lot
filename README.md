## INTRODUCTION
An Intelligent parking lot controller system is an automatic parking lot system 
whenever a vehicle approaches the gate. the distance of the vehicle from the parking lot is been detected
by an ultasonic sensor and the presence of the vehicle is detected by an infrared sensor.the gates automatically opens and when the car passes.
the gates are closed.

To use the code, 
you will need to attach the ultrasonic sensor and infrared sensor to the appropriate pins on the Arduino, and connect 
the motor driver and relay to the Arduino. 
in the `setup()` function You will need to:
  - Define the pins for the sensors and motor driver,
  - Define the constants for the parking lot dimensions and opening speed 
  - Define the variables for the parking lot gates
  - Define the variables for the ultrasonic sensor

Example
include the servo library
``` #include <Servo.h> ```

defining constatnts
``` const int ultrasonicPin = 3 // or #define ultrasonicPin 3
    const int parkingLotWidth = 10;
    const int openingSpeed = 50;
    int gateLeft = 0;
    int sensorDistance = 0; ```

In the `loop()` function
 Detect the approach of a car using the ultrasonic sensor
``` if (sensorDistance < 200)
 {  // Open the parking lot gates 
   digitalWrite(motorDriverPin, HIGH); 
   gateLeft = 1; 
   gateRight = 1; 
    // Close the parking lot gates when the car passes 
if (sensorDistance > 0) 
  { digitalWrite(motorDriverPin, LOW); 
    gateLeft = 0; 
    gateRight = 0; } } 
    // Detect the presence of a car in the parking lot using the infrared sensor 
if (digitalRead(infraredPin) == HIGH) {
   // Close the parking lot gates if a car is detected digitalWrite(motorDriverPin, LOW);
  gateLeft = 0; 
  gateRight = 0; } } 
  ```

## Components Used
- UBTECH Ukit Pack (robotic body)
- Arduino uno
- Ultrasonic sensor
- 2 Servo motors
- infrared sensors
- 9v battery
- jumper wires

## Softwares / IDE
- Arduino 
- ucode
