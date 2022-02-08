# Gesture Control Computer Using Python

## main:
establish the connection between the program and the arduino, then keep reading the 
output, if the output contains:
- 'Play/Pause' => both hands between 40 and 50: 
  - it clicks the space button
- 'Rewind' => right hand < 10: 
  - it clicks Ctrl + left
- 'Forward =>  20 < right hand  < 40: 
  - it clicks Ctrl + right
- 'Vdown' => 20 < left hand  < 40: 
  - it clicks the down button
- "Vup"  left hand < 10:
  - it clicks the up button

## arduino logic:
- setup:
  - Serial.begin() 
    - establishes serial communication between your Arduino board and the computer
    with baud rate or 9600
  - pinMode()
    - establish the input and output ports
  - calculate_distance()
    - calculate distance using the Ultrasound sensors
    - if dist is greater than 50 it set it to 50 (the max value is 50)

## the application logic:
1. calculate the distance from the first sensor (distL)
2. calculate the distance from the second sensor (distR)

- if both distances (L & R) is in between 40 and 50:
  - print: "Play/Pause"

- if distL between 13 and 17:
  - enter "left Lock"
    - in "left lock" while distL<=40:
      - if (distL<10) => print "Vup"
      - if (distL>20) => print "Vdown"
      
- if distR between 13 and 17:
  - enter "Right Lock"
    - in "Right lock" while distR<=40:
      - if (distR<10) => print "Rewind"
      - if (distR>20) => print "Forward"


## Circuit Diagram
![circuitdiagram](Control-your-Computer-with-Hand-Gestures-using-Arduino-circuit%20(1).jpg)