# Smart Fan Controller using Arduino UNO

## Overview

This project implements a Smart Fan Controller using an Arduino UNO, a DC motor, a potentiometer, a push button, and a MOSFET motor driver circuit.

The system operates in three modes:

* OFF Mode
* MANUAL Mode
* AUTO Mode

The push button is used to switch between operating modes. In MANUAL mode, the potentiometer directly controls the fan speed using PWM. In AUTO mode, the potentiometer acts as a simulated temperature sensor, and the controller automatically adjusts the fan speed according to predefined thresholds.

---

## Features

* Three operating modes
* PWM-based motor speed control
* State machine implementation
* Automatic speed control logic
* MOSFET motor driver
* External motor power supply
* Serial monitor debugging

---

## Components Used

* Arduino UNO
* DC Motor
* N-Channel MOSFET
* Flyback Diode
* Push Button
* 10k Potentiometer
* 9V Battery
* Breadboard
* Jumper Wires

---

## Working Principle

### OFF Mode

The motor remains stopped.

### MANUAL Mode

The potentiometer value is read using the Arduino ADC and converted into a PWM value ranging from 0 to 255. The PWM signal controls the motor speed.

### AUTO Mode

The potentiometer acts as a simulated temperature sensor.

* Low value → Low fan speed
* Medium value → Medium fan speed
* High value → Maximum fan speed

---

## State Machine

OFF → MANUAL → AUTO → OFF

Each press of the push button advances the system to the next state.

---

## Concepts Demonstrated

* PWM Control
* Analog-to-Digital Conversion
* State Machines
* Embedded Control Logic
* MOSFET Motor Driving
* Hardware Debugging

---

## Future Improvements

* Replace potentiometer with LM35 temperature sensor
* Add LCD display
* Add OLED dashboard
* Add Bluetooth control
* Implement hysteresis control
* Implement closed-loop speed control

---

## Author

SREEHARI VALLIKATTU

Electronics and Electrical Engineering Student



