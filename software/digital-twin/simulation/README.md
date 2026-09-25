# Multi-Physics Simulation Models

This directory contains numerical physics models simulating the cutting machine's mechanical, electromechanical, and biological interactions.

## Components
- `motor_model.py`: ODE solvers for BLDC cutter motor and feed stepper kinematics.
- `biomass_cutting_physics.py`: Mechanistic model calculating shear force and torque curves for mulberry stems as a function of diameter and moisture content.
- `kinematics.py`: Kinematic linkage equations relating feed roller linear velocity to cut length on the rotary drum.
