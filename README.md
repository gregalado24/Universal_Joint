# Universal Joint Kinematic Analysis

<p align="center">
  <img src="https://github.com/Jose-Rodriguez-22/Slider-Crank/blob/main/slider_crank%20motion.gif" width="600"/>
</p>

## Overview

This project investigates the kinematic behavior of a universal joint using parametric CAD modeling and mechanism simulation in **PTC Creo Mechanism**. The objective is to determine the relationship between the input shaft motion and the resulting output shaft velocity and acceleration under different shaft misalignment angles.

Universal joints are widely used in mechanical power transmission systems where rotational motion must be transferred between shafts that are not perfectly aligned.

---

## System Description

The mechanism consists of three main components:

| Component | Description |
|----------|-------------|
| Input Shaft | Driven shaft with constant angular velocity |
| Connector (Cross) | Transfers motion between shafts |
| Output Shaft | Misaligned shaft receiving transmitted motion |

The output shaft is offset by a **misalignment angle α**, which causes non-uniform angular velocity during rotation.

---

## Kinematic Relationship

The angular position relationship between the input shaft (θ₁) and output shaft (θ₂) is:


$\theta_2 = \tan^{-1} \left( \frac{\tan(\theta_1)}{\cos(\alpha)} \right)$


Assuming the misalignment angle α remains constant. :contentReference[oaicite:1]{index=1}

From this equation, the output angular velocity can be derived as:

$\omega_2 = \frac{\omega_1 \cos(\alpha)} {1 - \sin^2(\alpha)\cos^2(\theta_1)}$

where:

- ω₁ = input angular velocity  
- ω₂ = output angular velocity  
- α = shaft misalignment angle

---

## Simulation Setup

The assembly was created in Creo Mechanism with the following configuration:

• Cylindrical joints applied to both shafts  
• Misalignment angle controlled using assembly datum planes  
• Angular velocity servomotor applied to the input shaft  
• Motor speed: **360 deg/sec**  
• Simulation duration: **1 second**

The analysis tracked:

- Input angular position
- Output angular velocity
- Output angular acceleration

---

## Results

Two misalignment conditions were analyzed:

| Misalignment Angle | Observation |
|-------------------|-------------|
| 10° | Small velocity fluctuation |
| 30° | Significant velocity variation |

The universal joint does **not transmit constant angular velocity**. Instead, the output shaft speed oscillates twice per revolution.

As misalignment increases:

• velocity fluctuations increase  
• acceleration amplitudes increase significantly  

This behavior is a fundamental limitation of single universal joints.

---

## Simulation Results (Creo)

### Velocity vs Input Position

α = 10°

![Velocity10](plots/velocity_10deg.png)

α = 30°

![Velocity30](plots/velocity_30deg.png)

---

### Acceleration vs Input Position

α = 10°

![Accel10](plots/acceleration_10deg.png)

α = 30°

![Accel30](plots/acceleration_30deg.png)

---

## Analytical Results

Theoretical velocity and acceleration curves were generated using the derived equations and plotted in **Excel**.

The simulation and analytical results show strong agreement, confirming the correctness of the kinematic model.

---

## Skills Demonstrated

- Parametric CAD assembly modeling
- Mechanism simulation
- Kinematic analysis
- Mathematical derivation of motion equations
- Data comparison between analytical and simulated results

---

## Repository Structure

```
Universal_Joint_Kinematics
│
├── assembly
├── motion
├── plots
├── theory
└── README.md
```

---

## Application Relevance

This project demonstrates the creation of mechanical CAD assemblies with validated kinematic behavior. The workflow combines parametric modeling, motion simulation, and analytical verification, producing structured digital assets suitable for engineering analysis or AI-assisted CAD modeling workflows.
