<!---

This file is used to generate your project datasheet. Please fill in the information below and delete any unused
sections.

You can also include images in this folder and reference them in the markdown. Each image must be less than
512 kb in size, and the combined size of all images must be less than 1 MB.
-->

## How it works

The PID controller module works by continuously adjusting its output based on the difference between the desired value (setpoint) and the measured value (feedback). It does this using three components:

Proportional Term (P): This term corrects the error in proportion to the current difference between the setpoint and the feedback. It applies an immediate response to reduce the error.

Integral Term (I): This term accumulates the past error over time, helping to eliminate any steady-state error that may persist after the proportional correction.

Derivative Term (D): This term predicts future error by observing the rate of change of the current error, thus providing a damping effect to reduce overshooting.

The controller follows a state machine with states to calculate the error, update the integral and derivative terms, compute the output, and update the previous error value. Each calculation is performed on every clock cycle, ensuring that the controller continuously adapts the output to minimize the error between the setpoint and the feedback.

## How to test

Set different values for setpoint and feedback and observe the output in response to it. Change the setpoint to play around.

## External hardware

No specific external hardware is required to test the module in a simulation environment. However, for practical deployment, you may need:

Sensor: A sensor to provide the feedback signal, representing the process variable you wish to control.

Actuator: An actuator driven by the control_out signal to affect the process, such as a motor or a heating element.