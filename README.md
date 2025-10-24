5-Sensor Digital Line Follower Robot

Project Overview Note: In the below content, the directions (left and right) areaccording to the model i have uploaded in my repo(I made the model on TinkerCad)

This project is the Arduino code for a 4-wheel drive (4WD) line-following robot. It uses a 5-sensor IR array in digital mode to detect a black line on a white surface. The robot's logic is based on simple if/else conditions to check which sensors are on the line, allowing it to drive forward, turn, and stop.

Hardware Required

1x Arduino Uno

1x 5-Sensor IR (used in digital mode)

2x L293D Motor Driver ICs

4x Hobby Geared Motors

1x Power Supply for Arduino (9V battery)

This code assumes the following connections:

Motor Controller 1 (Left Side Motors)

Enable 1 & 2 (L293D Pin 1): Arduino Pin 5 Input 1 (L293D Pin 2): Arduino Pin 3 (motor12Dir1) Input 2 (L293D Pin 7): Arduino Pin 4 (motor12Dir2)

(Left side motors are connected to Output 1 & 2)

Motor Controller 2 (Right Side Motors)

Enable 1 & 2 (L293D Pin 1): Arduino Pin 10 Input 1 (L293D Pin 2): Arduino Pin 11 (motor34Dir1) Input 2 (L293D Pin 7): Arduino Pin 12 (motor34Dir2)

(Right side motors are connected to Output 1 & 2)

5 IR Sensors :

Sensor1 (Far Left): Arduino Pin A1 Sensor2 (Left): Arduino Pin A2 Sensor3 (Center): Arduino Pin A3 Sensor4 (Right): Arduino Pin A4 Sensor5 (Far Right): Arduino Pin A5

( I have used analog pins A1 through A5 are used as digital inputs in this code.)

How it Works :

The code operates on a simple logic loop:

Read Sensors: In each loop, it does a digitalRead() on all 5 sensors. Assume Logic: The code assumes that HIGH means the sensor is over the black line and LOW means it's over the white surface. Make Decision: Based on which sensors are HIGH, the robot decides what to do: Center Sensor HIGH: driveForward() Left Sensors HIGH: turnLeft() Right Sensors HIGH: turnRight() All Sensors LOW: stopMotors() (Line lost) All Sensors HIGH: driveForward() (Intersection)

How to use:

Upload code: Upload the sketch to your Arduino. Power On: Connect both your Arduino and motor power supplies. Place on Line: Place the robot on the track with the center sensor (A3) on the black line. Run: The robot will start following the line based on the logic.

If it doesn't work : My code's assumption is BLACK = HIGH. If your robot immediately drives off the line, the sensor might be the opposite (BLACK = LOW).

To fix this: Change every == HIGH in the void loop() section to == LOW.


WHAT I LEARNT WHILE MAKING THIS:
This is my first ever project in any domain. I had never ever used Arduino before. I used to make robots only through kits availble in market.
So in this process, 
I learnt the coding language for Arduino.
I learnt how to use breadboard.
I learnt how to make circuits in projects.
I learnt how make connections in Arduino.
I got to learn about motor drivers and how to operate them with arduino.
(Like online i used to see L298M motor driver but only l293d was available in tinkercad...so in that process i got to learn a bit deeper about motor drivers.
And had a lot of fun using Tinkercad.
I am still learning how to use PID and will shortly make a line follower robot based on analogRead , PWM using PID.
