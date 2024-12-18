# Obstacle-Avoiding Robot using Ultrasonic Sensor

## Description
This project implements an obstacle-avoiding robot using an ultrasonic sensor for distance measurement and motor driver control. The robot moves forward until it detects an obstacle within 15 cm, at which point it stops, moves backward, and makes a left turn to avoid the obstacle. 

The robot's motion is controlled by an Arduino and includes functions for moving forward, backward, turning left, and stopping. The ultrasonic sensor continuously monitors the distance to obstacles and adjusts the robot's motion accordingly.

---

## Components Required
1. **Arduino Uno** (or any compatible board)
2. **Ultrasonic Sensor (HC-SR04)**  
   - **Trig Pin**: Sends ultrasonic sound waves  
   - **Echo Pin**: Receives reflected waves
3. **Motor Driver (L298N)** or equivalent
4. **DC Motors** (2 motors, left and right)
5. **Wheels** (compatible with the DC motors)
6. **Power Supply** (for motors and Arduino)
7. **Connecting Wires** and a **Breadboard**

---

## Features
- **Obstacle Detection**: Measures distance using an ultrasonic sensor.
- **Autonomous Navigation**: The robot moves forward, avoids obstacles, and recalculates its path.
- **Motor Control**: Utilizes PWM signals for speed control of DC motors.

---

## Pin Configuration
| **Component**       | **Arduino Pin**         |
|----------------------|-------------------------|
| Ultrasonic Sensor Trig | 2                      |
| Ultrasonic Sensor Echo | 3                      |
| Motor Driver ENA      | 11                     |
| Motor Driver ENB      | 10                     |
| Left Motor Pin 1      | 7                      |
| Left Motor Pin 2      | 6                      |
| Right Motor Pin 1     | 5                      |
| Right Motor Pin 2     | 4                      |

---

## Functional Overview

### Ultrasonic Sensor
- Measures the distance to the nearest object using sound waves.
- The trigger pin sends a short pulse, and the echo pin receives the reflected pulse.
- The time taken for the pulse to return is converted to distance.

### Motor Control
- The L298N motor driver controls the left and right DC motors.
- Motors are driven in different directions to achieve forward, backward, or turning movements.

### Movement Logic
1. **Move Forward**: If no obstacle is detected within 15 cm.
2. **Stop**: When an obstacle is detected.
3. **Move Backward**: Reverses direction for 2.5 seconds upon obstacle detection.
4. **Turn Left**: Rotates left for 2 seconds to find a clear path.

---

## Code Breakdown
### Setup Function
- Initializes the ultrasonic sensor pins, motor driver pins, and the serial monitor for debugging.

### Movement Functions
- `moveForward()`: Sets motor directions and speeds for forward motion.
- `moveBackward()`: Reverses motor directions for backward motion.
- `turnLeft()`: Spins the robot left by controlling motor directions and speeds.
- `Stop()`: Stops the robot by setting motor speeds to zero.

### Loop Function
- Measures the distance to the nearest object.
- Executes movement commands based on the measured distance:
  - **Distance ≥ 15 cm**: Move forward.
  - **Distance < 15 cm**: Stop, move backward, and turn left.

---

## Installation and Usage
1. Connect the components as per the pin configuration table.
2. Upload the provided Arduino code to the Arduino board.
3. Power the robot using an appropriate power source.
4. Place the robot on a flat surface and observe its obstacle-avoidance behavior.

---

## Future Improvements
- Add additional sensors for more precise navigation.
- Implement turning right as an additional obstacle avoidance option.
- Enhance the logic to handle more complex obstacle layouts.
- Introduce a buzzer or LED indicators for feedback.

---

## License
This project is open-source and can be freely used and modified for educational purposes.
