# Experiment-no-6-DC-Motor-Speed-Control-Using-Arduino
###  DATE: 08-04-2024
###  NAME: Ashwin Akash M
###  ROLL NO : 212223230024
###  DEPARTMENT: AI&DS

### AIM : To control the speed and the direction of a DC motor using L293D driver ic( H- bridge)

### Components Required:
•	Arduino UNO board
•	L293D driver
•	12V DC motor
•	10K ohm potentiometer
•	Pushbutton
•	12V source
•	Breadboard
•	Jumper wires
### THEORY 
The L293D quadruple half-H drivers chip allows us to drive 2 motors in both directions, with two PWM outputs from the Arduino we can easily control the speed as well as the direction of rotation of one DC motor. (PWM: Pulse Width Modulation).
Arduino DC motor control circuit:
Project circuit schematic diagram is the one below.

![image](https://user-images.githubusercontent.com/36288975/167763051-b230c183-afc5-46f2-ba95-0f95e10dd6c9.png)
FIGURE-01 H BRIDGE CIRUCIT INTERFACE 
 
The speed of the DC motor (both directions) is controlled with the 10k potentiometer which is connected to analog channel 0 (A0) and the direction of rotation is controlled with the push button which is connected to pin 8 of the Arduino UNO board. If the button is pressed the motor will change its direction directly.
The L293D driver has 2 VCCs: VCC1 is +5V and VCC2 is +12V (same as motor nominal voltage). Pins IN1 and IN2 are the control pins where:
![image](https://user-images.githubusercontent.com/36288975/167763120-1421c2c5-8381-49eb-b376-03f6e1113b7a.png)
TABLE-01 EXITATION TABLE FOR H BRIDGE 

As shown in the circuit diagram we need only 3 Arduino terminal pins, pin 8 is for the push button which toggles the motor direction of rotation. Pins 9 and 10 are PWM signal outputs, at any time there is only 1 active PWM, this allows us to control the direction as well as the speed by varying the duty cycle of the PWM signal. The active PWM pin decides the motor direction of rotation (one at a time, the other output is logic 0).

### PROGRAM 
```
int in1=5;
int in2=6;
int en=3;

void setup()
{
  pinMode(in1, OUTPUT);
  pinMode(in2, OUTPUT);
  pinMode(en,OUTPUT);
}

void loop()
{
  analogWrite(en,30);
  digitalWrite(in1, HIGH);
  digitalWrite(in2, LOW);
  delay(500);
  
}
```
### OUTPUT
### Schematic Simulation:
![ROBOEXP6SIM](https://github.com/AshwinAkash24/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/144979248/faa229c7-079a-41dc-860b-8012fc827e06)

### ON Condition:
![ROBOEXP6ON](https://github.com/AshwinAkash24/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/144979248/fe37c6cf-5031-4ba0-8e9a-7b337663dc89)

### OFF Condition:
![ROBOEXP6OFF](https://github.com/AshwinAkash24/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/144979248/9de9a658-e3d4-43f8-8ecc-8d5059a1de38)


### Table:
![ROBOEXP6TABLE (2)](https://github.com/AshwinAkash24/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/144979248/7cbd8494-52c5-4079-9343-263f035aeba3)

### Graph:

![ROBOEXP6GRAPH](https://github.com/AshwinAkash24/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/144979248/0fbc7af7-ec32-46db-93db-ab45f01b4f6b)

### RESULTS AND DISCUSSION :
Hence,to control the speed and the direction of a DC motor using L293D driver ic( H- bridge) is successfully executed.

