Spring–Damper System Simulation

This project models and simulates a mass–spring–damper system using MATLAB Simulink, demonstrating how mechanical systems respond to external forces when both spring stiffness and damping effects are present. It is one of the most fundamental systems studied in mechanical and mechatronic engineering to understand vibration, oscillation, and system dynamics.

System Description

The spring–damper system consists of a mass connected to a spring and a damper. When an external force is applied, the spring resists displacement through its stiffness, while the damper provides a resistive force proportional to velocity, reducing oscillations.

This combination allows the system to simulate real-world behaviors such as:

Oscillation and vibration in mechanical structures

Energy storage and dissipation

System stability and settling behavior

Depending on the damping level, the system may behave as:

Underdamped – oscillatory motion that gradually settles

Critically damped – fastest response without oscillation

Overdamped – slow return to equilibrium with no oscillation

Purpose of the Simulation

The Simulink model demonstrates how the displacement, velocity, and acceleration of the mass change over time when subjected to an input force. It provides a visual and dynamic understanding of second-order systems and helps students analyze the effects of mass, spring stiffness, and damping on system behavior.

Model Implementation

In the Simulink environment, the system is modeled using:

A Sum block to represent the force balance equation

Gain blocks to scale terms by system parameters (mass, damping, stiffness)

Integrator blocks to compute velocity and displacement from acceleration

Scope blocks to visualize real-time responses

The simulation can easily be modified to explore how changing system parameters affects performance, such as response speed, oscillation amplitude, and damping behavior.

Applications

The spring–damper model is widely used in various engineering fields, including:

Automotive engineering — suspension and shock absorber systems

Robotics — actuator control and joint damping

Civil engineering — vibration control in buildings and bridges

Aerospace — modeling landing gear and structural dynamics

It serves as a foundation for understanding dynamic system design, control systems, and vibration analysis.
1. System Overview

The mass–spring–damper system consists of:

A mass (m) that moves in response to applied forces,

A spring (k) that provides a restoring force proportional to displacement,

A damper (c) that resists motion proportionally to velocity.

The system’s equation of motion is derived from Newton’s second law:

𝑚
𝑥
¨
(
𝑡
)
+
𝑐
𝑥
˙
(
𝑡
)
+
𝑘
𝑥
(
𝑡
)
=
𝐹
(
𝑡
)
m
x
¨
(t)+c
x
˙
(t)+kx(t)=F(t)

where

𝑥
(
𝑡
)
x(t): displacement (m)

𝑥
˙
(
𝑡
)
x
˙
(t): velocity (m/s)

𝑥
¨
(
𝑡
)
x
¨
(t): acceleration (m/s²)

𝐹
(
𝑡
)
F(t): external force (N)

This second-order differential equation describes how the system behaves when subjected to external excitation or disturbance.

2. Analytical Parameters

Key characteristics of the system include:

Natural frequency

𝜔n = root (𝑘/
𝑚)


Damping ratio

𝜁 =
𝑐/
2
root (𝑘
𝑚)


Damped natural frequency (for underdamped case, 
𝜁 = (ζ < 1)

𝜔
𝑑 = 
𝜔
𝑛
root(1
−
𝜁^2)


These parameters define how quickly and smoothly the system returns to equilibrium after a disturbance.

3. Example Calculation

Let’s consider a numerical example:

Parameter	          |          Symbol	         |         Value  
	
Mass                          	𝑚                       1 kg

Spring constant	                𝑘                       100 N/m

Damping coefficient	            𝑐                      	10 N·s/m

Step input force	              𝐹0                      1N

Calculated results:

𝜔
𝑛 =
root(100 /
1)
=
10
 rad/s

𝜁 =
10 /
2
root 100
=
0.5

𝜔
𝑑 =
10
root(1
−
0.5^2)
=
8.66
 rad/s

𝑥
𝑠
𝑠 = 
𝐹
0 /
𝑘 
= 0.01m


Performance indicators:

Percent overshoot: 16.3%

Time to first peak: 0.36 s

Steady-state displacement: 0.01 m


These results indicate an underdamped system with oscillatory behavior that gradually settles at 0.01 m.

4. Simulink Implementation

The Simulink model (spring_damper.slx) consists of:

A Sum block implementing 
𝐹
−
𝑐
𝑥
˙
−
𝑘
𝑥
F−c
x
˙
−kx

A Gain block for 
1
/
𝑚
1/m to compute acceleration

Integrator blocks to obtain velocity and displacement

Optional Scope blocks to visualize system response

The model allows simulation under various damping and stiffness values to observe underdamped, critically damped, or overdamped behaviors.

5. How to Run the Simulation

Open MATLAB and navigate to the project folder.

Open the Simulink model spring_damper.slx.

Edit the parameters (m, k, c) in the workspace or block mask.

Use a Step Input block to apply a force 
𝐹
(
𝑡
)
F(t).

Click Run to simulate.

Observe displacement, velocity, and acceleration responses on the Scope.

6. Expected Results

For the given parameters:

The system will oscillate with a gradually decreasing amplitude (underdamped).

The displacement will overshoot slightly (~16%) before settling.

The final steady-state displacement will be 0.01 m.

The Simulink scope will show a damped oscillatory waveform that visually confirms the theoretical calculations.

7. Applications

The spring–damper model is fundamental in:

Vehicle suspension systems

Building vibration analysis

Robotics (joint motion control)

Machine design and structural dynamics

It provides an excellent base for understanding second-order dynamic systems and for verifying theoretical vibration models.


9. Conclusion

This project provides both theoretical and simulation-based analysis of a simple mechanical vibration system.
By adjusting mass, damping, and stiffness values, users can explore how these parameters affect oscillation, settling time, and stability in a real-world dynamic system.
