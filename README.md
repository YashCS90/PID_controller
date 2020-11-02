# PID Controller

Udacity Self-Driving Car Nanodegree - PID Control project

# Overview

This project implements a PID controller to control a car in Udacity's simulator

# Prerequisites

The project has the following dependencies:

- cmake >= 3.5
- make >= 4.1
- gcc/g++ >= 5.4
- Udacity's simulator.


# Compiling and executing the project

In order to build the project there is a follow below steps.

```
root@a22d62ce52d6:/home/workspace/CarND-PID-Control-Project/build# cmake ..
-- Configuring done
-- Generating done
-- Build files have been written to: /home/workspace/CarND-PID-Control-Project/build
```

```

root@a22d62ce52d6:/home/workspace/CarND-PID-Control-Project/build# make
[100%] Built target pid
root@a22d62ce52d6:/home/workspace/CarND-PID-Control-Project/build# ./pid
Listening to port 4567
```


Now the PID controller is running and listening on port 4567 for messages from the simulator. Next step is to open Udacity's simulator:



# [Rubric] points

## Compilation

### Your code should compile.

The code compiles without errors or warnings.

## Implementation

### The PID procedure follows what was taught in the lessons.

The PID implementation is done on the [./src/PID.cpp](./src/PID.cpp). 

## Reflection

### Describe the effect each of the P, I, D components had in your implementation.

- The 'P' of the PID controller keeps the car towards the center line (against the cross-track error). If used along, the car overshoots the center line very easily and go out of the road very quickly.

- The 'I' of the PID controller tries to remove the bias on the PID system. If it makes the car to go in circles. 

- The 'D' of the PID controller helps to compensate the proportional trend to overshoot the center line by smoothing the approaching towards it.



### Describe how the final hyperparameters were chosen.

- The parameters are chosen by hit and trial.
- The car moves straight with [P: 0.0, I: 0.0, D: 0.0].
- The car moves along the road but goes out of it for [P: 1.0, I: 0.0, D: 0.0].
- The car tries to compensate the overshooting due to just the 'p' term for [P: 1.0, I: 0.0, D: 1.0].
- The car moves out of road with [P: 1.0, I: 1.0, D: 1.0].
- Finally the value which helped complete the full lap of the track. [P: 0.135, I: 0.0, D: 2.55].



## Simulation

### The vehicle must successfully drive a lap around the track.

