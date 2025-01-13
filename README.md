# Truck-Trailer Hybrid Automaton with LQ Control

This repository contains the hybrid automaton model of a truck-trailer system stabilized using LQ control. The model and configuration files are designed for reachability analysis and safety verification using Flowstar.

## Project Overview
This project models the system using a hybrid automaton with three discrete modes:

1. **Backward Straight Line**: The truck reverses along a straight path.
2. **Backward Arc**: The truck reverses along a circular trajectory.
3. **Forward Motion**: The truck aligns itself forward for subsequent backward maneuvers.

Each mode is governed by linear-quadratic (LQ) controllers derived from the linearized system dynamics. Switching between modes is determined by state-dependent guards.

### Model Files
- **`HA_LQ_controller.cfg`**: Configuration file defining the automaton parameters.
- **`HA_LQ_controller.xml`**: Automaton structure with state variables, dynamics, and transitions.
- **`HA_LQ_controller.yml`**: Initial conditions, safety constraints, and settings for Flowstar reachability analysis.

## Getting Started
### Prerequisites
- [Flowstar](https://flowstar.org): A tool for reachability analysis of hybrid systems.

### Safety Properties
The project includes predefined safety constraints, such as:
- Avoiding jack-knife configurations (e.g., `beta3 >= 1.0`).

These are encoded in the `unsafe` section of the `.yml` file.

## Reference
For a detailed explanation of the hybrid control strategy and modeling approach, refer to the following paper:

> Claudio Altafini, Alberto Speranzon, and Karl Henrik Johansson. "Hybrid Control of a Truck and Trailer Vehicle." HSCC 2002. [Link to paper](https://doi.org/10.1007/3-540-45873-5_3)

## License
This project is licensed under [MIT License](LICENSE).
