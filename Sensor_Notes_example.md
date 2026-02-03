# Example of sensor notes

# Sensor 1: (Sensor name)

### Basic Information
- Sensor name: 
- Purpose: 
- Interface: (Analog or digital output?)
- Operating voltage:
- Source / Reference: 

- ### How it works
> Write a short explanation of how the sensor reacts. For example:  
> - Describe the basic mechanism of the sensor (e.g., it contains a photoresistor that changes resistance depending on light).  
> - Explain how the sensor’s output is read as a value (e.g., Light-dependent resistance: Bright light → resistance decreases → output voltage decreases; Darkness → resistance increases → output voltage increases).  
> - Give an example of how the sensor can be used (e.g., Useful for brightness detection, automatic light control, or basic environmental sensing).

---

### Hardware Setup 

### Software Setup (Arduino IDE)
> Explain your set up here. 
> ex)
- Platform: Arduino Uno
- Programming language: C / Arduino
- Library: None required (uses built-in analogRead())

#### PIN Connection - Arduino Uno (Joy-IT R3 DIP)
> How did you connect it? explain, or show it with picture.
> ex)
- VCC → 5V
- GND → GND
- Signal  → A5

#### Arduino Sketch

> Try to run the sensor by yourself, and make sure that the code you looked up is actually working with the setup you mentioned.
> Try to understand the meaning of each line of the code.
> Add explanation comments in the code using // signs to describe what each part does.
> This will help you remember how the sensor works and how to integrate it with other tasks later.

> ex)

```cpp

void setup() {
  Serial.begin(9600);  // Start serial communication for monitoring
}

void loop() {
  int lightValue = analogRead(A0);  // Read analog value from KY-018
  
  Serial.print("Light (analog): "); // Print description
  
  Serial.println(lightValue);       // Print measured value
  
  delay(500);                       // Wait 500ms before next reading
}

```
