# Sensor 1: KY-028 Temperature Sensor Modul (Thermistor)

### Basic Information
- Sensor name: Temperature Sensor Modul (Thermistor)
- Purpose: Reads temperature from an analog thermistor module
- Interface: Analog 

- ### How it works
 A thermistor is a temperature-dependent resistor. In this module, an NTC thermistor is used, meaning its resistance decreases as temperature increases. The Arduino measures temperature indirectly by reading an analog voltage through a voltage divider.
- Measure room temperature
- Temperature-controlled fan
- Simple thermostat system
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


# Sensor 2: KY-050 Ultrasonic Distance Sensor
### Basic Information
- Sensor name: Ultrasonic Distance Sensor
- Purpose: Measures distance using an ultrasonic sensor
- Interface: Digital

- ### How it works
The ultrasonic distance sensor measures distance by emitting an ultrasonic pulse and measuring the time it takes for the echo to return. Distance is calculated using the speed of sound.
- Obstacle detection for robots
- Parking sensors for cars
- Measuring water level in a tank
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

# Sensor 3: KY-033 Line Tracking Sensor Module

### Basic Information
- Sensor name: Line Tracking Sensor Module
- Purpose: Reads digital output from a line tracking sensor
- Interface: Digital

- ### How it works
The line tracking sensor uses an infrared LED and phototransistor to detect reflective surfaces. It outputs a digital signal indicating whether a dark or light surface is detected.
- Line-following robots
- Edge detection on conveyor belts
- Detecting black/white markers
---

### Hardware Setup 

### Software Setup (Arduino IDE)
- Platform: Arduino Uno
- Programming language: C / Arduino
- Library: None required (uses built-in analogRead())

#### PIN Connection - Arduino Uno (Joy-IT R3 DIP)
- VCC	---> 5V
- GND	---> GND
- DO	---> D3

#### Arduino Sketch

```cpp
const int trackingPin = 3;


void setup() {
Serial.begin(9600);
pinMode(trackingPin, INPUT);
}


void loop() {
int sensorState = digitalRead(trackingPin);


if (sensorState == LOW) {
Serial.println("Dark surface detected");
} else {
Serial.println("Light surface detected");
}


delay(300);
}
```

# Sensor 4: KY-027 Magic Light Cup Module

### Basic Information
- Sensor name: Magic Light Cup Module
- Purpose: Reads tilt state from Magic Light Cup module
- Interface: Digital

- ### How it works
The Magic Light Cup module contains a tilt-sensitive switch that controls LEDs depending on orientation. It is commonly used to demonstrate digital input behavior.
- Tilt detection in cups or devices
- Orientation detection for toys or games
- Motion-activated LEDs
---

### Hardware Setup 

### Software Setup (Arduino IDE)
- Platform: Arduino Uno
- Programming language: C / Arduino
- Library: None required (uses built-in analogRead())

#### PIN Connection - Arduino Uno (Joy-IT R3 DIP)
-VCC	---> 5V
-GND	---> GND
-DO	---> D4

#### Arduino Sketch

```cpp
const int tiltPin = 4;


void setup() {
Serial.begin(9600);
pinMode(tiltPin, INPUT);
}


void loop() {
int tiltState = digitalRead(tiltPin);


if (tiltState == HIGH) {
Serial.println("Module tilted");
} else {
Serial.println("Module level");
}


delay(300);
}
```

# Sensor 5: KY-019 5V Relay Module

### Basic Information
- Sensor name: 5V Relay Module
- Purpose: Controls a 5V relay module
- Interface: Digital

- ### How it works
The 5V relay module allows the Arduino to control high-voltage or high-current devices using a low-voltage digital signal. It acts as an electrically isolated switch.
- Switching lamps or fans
- Automation in home devices
- Controlling motors safely
---

### Hardware Setup 

### Software Setup (Arduino IDE)
- Platform: Arduino Uno
- Programming language: C / Arduino
- Library: None required (uses built-in analogRead())

#### PIN Connection - Arduino Uno (Joy-IT R3 DIP)
- VCC	---> 5V
- GND	---> GND
- IN	---> D7

#### Arduino Sketch

```cpp

const int relayPin = 7;


void setup() {
pinMode(relayPin, OUTPUT);
}


void loop() {
digitalWrite(relayPin, HIGH); // Relay ON
delay(1000);
digitalWrite(relayPin, LOW); // Relay OFF
delay(1000);
}
```

# Sensor 6: KY-013 Temperature Sensor Module

### Basic Information
- Sensor name: KY-013 Temperature Sensor Module
- Purpose: Reads temperature from an analog thermistor module
- Interface: Digital

- ### How it works
The KY-013 module uses an NTC thermistor, whose resistance decreases as temperature increases. Arduino reads the temperature indirectly through the analog voltage on the AO pin
- Measure room temperature
- Temperature-controlled fan
- Simple thermostat system

---

### Hardware Setup 

### Software Setup (Arduino IDE)
- Platform: Arduino Uno
- Programming language: C / Arduino
- Library: None required (uses built-in analogRead())

#### PIN Connection - Arduino Uno (Joy-IT R3 DIP)
- VCC	---> 5V
- GND	--->GND
- AO	---> A0

#### Arduino Sketch

```cpp

const int tempPin = A0; // AO pin

void setup() {
  Serial.begin(9600);
}

void loop() {
  int analogValue = analogRead(tempPin); // 0–1023
  Serial.print("Raw analog value: ");
  Serial.println(analogValue);
  
  // Optional: Convert to approximate voltage
  float voltage = analogValue * 5.0 / 1023;
  Serial.print("Voltage: ");
  Serial.println(voltage);

  delay(500);
}
```
