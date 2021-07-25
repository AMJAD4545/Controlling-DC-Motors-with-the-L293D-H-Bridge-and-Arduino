# Controlling-DC-Motors-with-the-L293D-H-Bridge-and-Arduino
# Pre requirement  
* Create an account in [tinkercad](https://www.tinkercad.com/) 
*  * Create a new Circui
# Tools:
1. Breadboard.
2. Arduino Uno R3.
3. DC Motors.
4. Wires. 
5. L293D H Bridge.
6. Battery 
  <img width="722" alt="126025503-9585c978-9fe4-44d1-a189-04eda20e7190" src="https://user-images.githubusercontent.com/85800978/126887555-8c8ecf2e-7fdb-48b6-b2bb-423b3e49914e.png">

# What is L293D H Bridge?
A motor driver is an integrated circuit chip which is usually used to control motors in autonomous robots. Motor driver act as an interface between Arduino and the motors . The most commonly used motor driver IC’s are from the L293 series such as L293D, L293NE, etc. These ICs are designed to control 2 DC motors simultaneously. L293D consist of two H-bridge. H-bridge is the simplest circuit for controlling a low current rated motor.L293D has 16 pins.

![126024531-2352ce31-70c4-43a8-b05c-1f0a9c5078bd](https://user-images.githubusercontent.com/86169417/126885693-eda3444c-3c2e-4d5d-ba8b-328e36831b49.png)

# Steps : 
#### step1: Connect Enable1&amp;amp;2,Enable3&amp;amp;4 and power1 with (5v) pin on Arduino. 
#### step2: Connect input1 with 13 pin, input2 with 12, input3 with 8 pin pin, input4 with 7 pin on Arduino. 
#### step3: Ground pins (4,5,12,13) on L293D connected to GND pin on Arduino. 
#### step4: Connect Output1&amp;amp;Output2 with DC Motor1, Output3&amp;amp;Output4 with DC Motor2. 
NOTE: DC Motor will rotating in clockwise direction and if you want to run DC motor in anticlockwise direction we need to some change in the code (Replace HIGH to LOW and vice versa).
```c++  
void loop()
{  

digitalWrite(13, LOW); 
digitalWrite(12, HIGH); 
digitalWrite(8, LOW); 
digitalWrite(7, HIGH);   
} 
```
But, if you want it to rotate in both directions with a while in between, then you need to set a delay for number of millisecond then the direction of rotation changes to other side.  
```c++
void setup() 
{  
pinMode(13, OUTPUT); 
pinMode(12, OUTPUT); 
pinMode(8, OUTPUT);  
pinMode(7, OUTPUT);
}  
void loop() 
{ 
digitalWrite(13, HIGH); 
digitalWrite(12, LOW); 
digitalWrite(8, HIGH); 
digitalWrite(7, LOW); 
delay(2000); // Wait for 1000 millisecond(s)   
digitalWrite(13, LOW);   
digitalWrite(12, HIGH);  
digitalWrite(8, LOW); 
digitalWrite(7, HIGH); 
delay(2000); // Wait for 1000 millisecond(s) 
}  
``` 
# Output Sample 
![Daring Hillar (2)](https://user-images.githubusercontent.com/86169417/126885789-1774cd0a-1eb1-4e61-ac2e-5bf00c7379e2.png) 
# Learning references: 
* [Click here](https://www.youtube.com/watch?v=qJeAo4zo0IY)
