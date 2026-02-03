# Sensor 1: Temperature Sensor Modul (Thermistor)

### Basic Information
- Sensor name: Temperature Sensor Modul (Thermistor)
- Purpose: Reads temperature from an analog thermistor module
- Interface: Analog
- Operating voltage:
- Source / Reference: 

- ### How it works
 A thermistor is a temperature-dependent resistor. In this module, an NTC thermistor is used, meaning its resistance decreases as temperature increases. The Arduino measures temperature indirectly by reading an analog voltage through a voltage divider.
> - Give an example of how the sensor can be used (e.g., Useful for brightness detection, automatic light control, or basic environmental sensing).

---

### Hardware Setup 

### Software Setup (Arduino IDE)
- Platform: Arduino Uno
- Programming language: C / Arduino
- Library: None required (uses built-in analogRead())

#### PIN Connection - Arduino Uno (Joy-IT R3 DIP)
- VCC	---> 5V
- GND	---> GND
- AO	---> A0

#### Arduino Sketch

```cpp

const int thermistorPin = A0;


void setup() {
Serial.begin(9600); // Initialize serial communication
}


void loop() {
int analogValue = analogRead(thermistorPin); // Read ADC value
Serial.print("Thermistor raw value: ");
Serial.println(analogValue);
delay(500);
}

```


# Sensor 2: Ultrasonic Distance Sensor
### Basic Information
- Sensor name: Ultrasonic Distance Sensor
- Purpose: Measures distance using an ultrasonic sensor
- Interface: Digital
- Operating voltage:
- Source / Reference: 

- ### How it works
The ultrasonic distance sensor measures distance by emitting an ultrasonic pulse and measuring the time it takes for the echo to return. Distance is calculated using the speed of sound.
> - Give an example of how the sensor can be used (e.g., Useful for brightness detection, automatic light control, or basic environmental sensing).

---

### Hardware Setup 

### Software Setup (Arduino IDE)
- Platform: Arduino Uno
- Programming language: C / Arduino
- Library: None required (uses built-in analogRead())

#### PIN Connection - Arduino Uno (Joy-IT R3 DIP)
- VCC	  ---> 5V
- GND	  ---> GND
- TRIG	---> D9
- ECHO	---> D10

#### Arduino Sketch

```cpp

const int trigPin = 9;
const int echoPin = 10;


void setup() {
Serial.begin(9600);
pinMode(trigPin, OUTPUT);
pinMode(echoPin, INPUT);
}


void loop() {
digitalWrite(trigPin, LOW);
delayMicroseconds(2);
digitalWrite(trigPin, HIGH);
delayMicroseconds(10);
digitalWrite(trigPin, LOW);


long duration = pulseIn(echoPin, HIGH); // Measure echo time
float distance = duration * 0.034 / 2; // Convert to cm


Serial.print("Distance: ");
Serial.print(distance);
Serial.println(" cm");


delay(500);
}
```


