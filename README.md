# Parrot Mini Drone - Red Line Following Simulation

## Overview

This project demonstrates a red line following algorithm using a `Parrot Mini Drone` simulation in Simulink. The drone uses a camera feed to detect a red line on the ground and autonomously navigates through the environment by following this line. The algorithm processes the video input to detect red pixels and adjust the drone's trajectory accordingly. This simulation provides a robust example of **vision-based control** for drones in a virtual environment.

## Project Structure

1. **Vision-Based Line Detection**
The core of this project lies in processing the drone’s camera input to detect the red line. The image is converted from the drone’s native format into RGB values, and the red intensity is isolated using a custom algorithm:

- **RGB Conversion**: Captured images are processed to isolate the red pixels using the formula `R - (B/2) - (G/2)`.
- **Thresholding**: After isolating the red components, the image is thresholded to filter only relevant red pixels.
- **Summation & Detection**: If the red pixel count exceeds a predefined threshold, the drone recognizes the red line and adjusts its path accordingly.
  
2. **Stateflow Controller for Drone Navigation**
The Stateflow diagram manages the drone’s movements based on the detected line and time-based constraints:

- **TakeOff**: The drone initiates a vertical takeoff.
- **StraightMoveForward**: Upon detecting the red line, the drone moves forward.
- **TurnMoveForward**: After a set time, the drone turns to align itself with the detected red line.
- **Hover**: The drone hovers in place when no line is detected or the task is completed.

3. **Simulink Control System**
The Simulink model integrates the vision processing and drone navigation subsystems, allowing seamless interaction between the visual input and the drone's movement outputs. All outputs are processed and converted into motion commands for the simulated drone.

## Key Features

- **Red Line Detection**: Implements real-time image processing to identify and follow red-colored lines.
- **Stateflow Logic**: Ensures stable and efficient control of drone navigation.
- **Fully Simulated**: No hardware is required; the entire project runs in a simulated environment.
  
## Conclusion
This project showcases the implementation of a `vision-based control system` for drones using `Simulink` and `Stateflow`. It can serve as a foundation for advanced `autonomous drone navigation algorithms`. The model is easy to `modify`, `extend`, and `optimize` for different environments and conditions.

## Requirements
- `MATLAB` & `Simulink`
- Simulink Support Package for `Parrot Minidrones`
  
## How to Run
- Install the required Simulink package for `Parrot Minidrones`.
- Open the Simulink model and run the simulation.
- Watch as the drone detects and follows the red line in the simulated environment.
