# Open Loop Control - Motor Characterization (Report)

**Name:** Vishal Jagannathan 
**Department:** EECE 
**Year:** 1
**Date:** 16 March 2026

## Abstract
The fundamental purpose of this experiment is to understand open loop based systems and therefore characterize motors in order to enable a buggy to travel in a straight line.

## Introduction
The significance of this experiment cannot be completely understood without the knowledge of open and closed loop systems.
Although this report will not focus on closed loop systems, it is important to know the diffenece.
Consider a case whereby you need to control the temperature of a room, you can do this in two ways:
One of the methods would involve setting your desired temperature without considering external variables.
The second method would involve setting up an adaptive system such as increasing/decreasing the temperature to meet the desired temperature i.e if a window is open, etc.
This experiment will be based on the first case.

## Theory
In order to characterize a motor, it is important to understand the principles of open loop control [1].
Open loop control is based on a simple system which does not constantly send out signals to adapt to its environment and this means that it does not support a feedback loop.
Due to its rather significantly less complex approach, and lower components, it is deemed quite reliable [1].

## Experimental method
In order to test a buggy at three different speeds, the pwm values of the right and left motors need to be adjusted.
The buggy was tested at the following pwm values:
1. 100
2. 150
3. 200

at a fixed distance of 2 metres.

The constants LEFT_OFFSET and RIGHT_OFFSET have been introduced in the source code in order to enable the buggy to move in a straight line

## Results
| Right Motor PWM | Left Motor PWM | Distance (m) | Right Offset | Left Offset | Speed (ms<sup>-1</sup>) | Direction of Travel   |
|-----------------|----------------|--------------|--------------|-------------|-------------------------|-----------------------|
| 100             | 100            | 1.0          | 0            | 0           | 0                       | Veers off to the left |
|                 |                | 1.0          | 0            | 24          | 0.278                   | Straight              |
|                 |                | 1.5          | 0            | 24          | 0.265                   | Straight              |
|                 |                | 2.0          | 0            | 24          | 0.295                   | Straight              |
|                 |                |              |              |             |                         |                       |
| 150             | 150            | 1.0          | 0            | 0           | 0                       | Veers off to the left |
|                 |                | 1.0          | 0            | 40          | 0.300                   | Straight              |
|                 |                | 1.5          | 0            | 40          | 0.257                   | Straight              |
|                 |                | 2.0          | 0            | 40          | 0.204                   | Straight              |
|                 |                |              |              |             |                         |                       |
| 200             |                | 1.0          | 0            | 0           | 0                       | Veers off to the left |
|                 |                | 1.0          | 0            | 44          | 0.400                   | Straight              |
|                 |                | 1.5          | 0            | 44          | 0.420                   | Straight              |
|                 |                | 2.0          | 0            | 44          | 0.460                   | Straight              |

## Analysis
The speed of the buggy was calculated for the following distances; 1.0,1.5,2.0 metres to setup a benchmark for the most optimized value for left and right motor pwm.
As shown in the table, when the pwm values are set equal, the buggy tends to veer of to the left, suggesting that the influence of the right motor is stronger.
In all cases displayed in the table above, the left offset has been adjusted so that the buggy can move along in a straight line.
Left offset calculation is as follows:
Eg. Consider the following case:
Initial Left Motor PWM = 100
Left Offset = 24

Left Motor PWM = Initial Left Motor PWM + Left Offset
Left Motor PWM = 100 + 24
               = 124

The dataset has been limited to 2 metres as this is the maximum treshold before the buggy begins to veer off its path.
The code for motor control can be found in the github repository: open-loop-motor-control.ino [2]

## Conclusion
The experiment has facilitated the development and understanding in implementing an open loop control based system.

## References
1. W. Bolton, *Mechatronics: Electronic Control Systems in Mechanical and Electrical Engineering*, 6th ed. Harlow, U.K.: Pearson Education, 2015.
2. Canvas learning material
