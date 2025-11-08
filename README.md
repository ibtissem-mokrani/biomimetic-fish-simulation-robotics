# Biomimetic Fish Simulation — Robotics Inspired by the Mandarinfish

Python project for simulating the locomotion and purposeful behavior of a Mandarinfish (*Synchiropus splendidus*) — created for robotics master applications. Includes code, visualization, scientific context, and discussion.

---

## General Overview
This project simulates the undulatory swimming and foraging journey of a single Mandarinfish using Python.  
Inspired by natural aquatic locomotion and bio-inspired robotics, the model reproduces the fish’s wave-like movement and its behavioral routine: leaving its vibrant coral shelter to hunt for food, then returning home.

---

## Author

- Ibtissem Mokrani
- Contact: ibtissemokrani@gmail.com
- University: Sorbonne Université & Trinity College Dublin (Erasmus)

---

## Why the Mandarinfish?

### Species Description

The Mandarinfish is a small, brilliantly colored reef fish native to the Pacific Ocean, especially the coral-rich waters of Southeast Asia.  
Notable for its vivid blue/gold/orange patterns, it is famous among marine biologists and divers for both its appearance and its fascinating behavior.

Key biological traits:
- **Territoriality:** Mandarinfish maintain a defined ‘home base’ (typically among corals or rocks), to which they always return after foraging.
- **Foraging habits:** They make regular, purposeful excursions from this shelter to hunt small invertebrates, then navigate back home—demonstrating spatial memory and habitat fidelity.
- **Swimming style:** Their locomotion involves refined undulatory waves along an elongated, flexible body—perfect for sliding through tight coral spaces and maneuvering with agility.

### Mandarinfish in Biomimetic Robotics

The behaviors and swimming mechanics of the Mandarinfish exemplify:
- Energy-efficient undulatory propulsion
- Highly controlled movement in complex 3D environments
- Strong sense of place (‘homing’), which is highly relevant for the design of autonomous underwater robots required to explore, return, and operate safely in dynamic habitats.

---

## Project Introduction

### Aim

This project aims to recreate the Mandarinfish’s undulatory swimming and purposeful navigation using a chain-of-segments model and a sinusoidal wave formula.

The simulation animates:
- The fish’s signature wave-like propulsion.
- Its behavioral cycle: leaving a ‘home’ zone, reaching a target (food), and returning home—mirroring real Mandarinfish behavior.

---

## Scientific Context

- The Mandarinfish’s motion is rooted in biomechanical undulation, using propagating sinusoidal waves along the body axis.
- In robotics, such natural movements inspire the design of flexible, efficient, and maneuverable underwater robots for ecology and exploration.
- This simulation connects physical modeling, behavioral programming, and biomimetic engineering principles to illustrate how real animal strategies can inform the future of robotics.

### Project Plan

- **Define physical parameters specific to the Mandarinfish:** amplitude, frequency, phase shift, number of segments, overall size—using values inspired by scientific observations of mandarinfish swimming.
- **Implement the mathematical model** for the traveling sinusoidal wave that mimics the Mandarinfish’s undulatory propulsion.
- **Build the articulated 2D visualization** of a single Mandarinfish, with characteristic proportions and undulation style.
- **Simulate purposeful foraging behavior:** The Mandarinfish will leave its “home” (a coral or rock shelter), use undulatory swimming to reach a food target, then return homing—mirroring the natural spatial behavior of the species.
- **Run and analyze simulations:** Vary physical and behavioral parameters (amplitude, speed, memory of home, trajectory), observe how the swimming pattern and trajectory adapt.
- **Discuss extensions:** Potential for multi-fish behavior, environmental complexity (coral maze), more advanced goal-seeking and obstacle avoidance.

### Principle Behind Mandarinfish Locomotion

Undulatory swimming confers:
- **Energy efficiency** suited for frequent short-distance foraging trips.
- **Agility** needed for navigation in cluttered, confined reef environments.
- **Precision** for safe return to its home base—a central feature of Mandarinfish ecology.

### Sinusoidal Wave Model and Parameters

To biologically ground the simulation, the body shape and movement are parameterized with data reflecting Mandarinfish morphology.  
The swimming is modeled as:  
  **y(x, t) = A × sin(k × x – ω × t + φ)**

with:
- **A (Amplitude):** Mandarinfish use relatively low amplitude, focusing more on control than burst speed.
- **k (Wave number, related to wavelength λ):** Set based on body length (usually 2–6 wavelengths total along the body).
- **ω (Angular frequency):** Chosen to match Mandarinfish foraging tail-beat rates from scientific studies.
- **φ (Phase offset):** May be tuned for “tight” vs “broad” turns.

By adjusting these, the simulation recreates both the signature “wave” and the purposeful exploratory/return motion of a real Mandarinfish navigating its home reef.  
This also provides a robust testbed for biomimetic robotics—demonstrating how animal-inspired control algorithms produce lifelike behaviors.

### Simulation Objective and Approach (Mandarinfish Case Study)

- The single Mandarinfish starts at a defined “home” (e.g., coral position).
- Using real swimming dynamics, it undulates away, seeks out a food location, simulates a “foraging” behavior, then returns to its home base—reflecting homing seen in wild individuals.
- This focused case not only visualizes animal movement but encodes ecological and behavioral context into a compact computational model, ideal for both academic study and robotic inspiration.

--- 

## Project Developpement and Key Steps

### Implementation 

The practical coding work began with building a sinusoidal backbone model, calibrating physical parameters to closely mimics Mandarinfish biomecanics.
Using Matplotlib for vizualization ensured an interactive approach - enabling rapid prototyping and refinement of the ondulatory swimming algorithm.

Key implementation steps were:

- Translating wave mechanics from biological observation to mathematical models.
- Structuring the backbone as a chain of articulated segments driven by a time-dependent sinusoidal function.
- Validating swimming motion with plots and debugging body parameter settings to guarantee lifelike behavior.

### Introducing Navigation

To simulate purposeful movement, the Mandarinfish received a “home” position and a distant “food” target.
Coding the behavioral cycle—departure, travel, foraging, and return—required synchronizing path planning logic with the backbone undulatory dynamics.

### Obstacle Avoidance & Environmental Challenges

Successfully integrating obstacle avoidance proved a notable challenge and a key learning point.
Obstacles (“corals”) were modeled as circular zones, and the simulation utilized geometric checks (circle-line intersection) to decide when the Mandarinfish should divert from its straight path.

At times, obstacle positioning—close to home or food—revealed that avoidance could overpower direct trajectory selection, leading the Mandarinfish to trace elaborate arcs rather than optimal routes.
This behavior, while visually interesting, mirrors real-world complexities discussed in the scientific literature: organisms and robots alike must continuously adapt locomotion and path-planning to environmental constraints.

Several strategies were explored:

- Tuning avoidance thresholds, arc length constraints, and recovery logic.
- Testing various obstacle configurations: simple reefs, complex multi-coral fields.
- Balancing “tangent escape” with realistic foraging and homing cycles for more natural movement.

### Visualization & Aesthetic Enhancements

To make the simulation compelling and educational, significant attention was given to graphical detail:

- Distinct palette choices for corals and fish body segments.
- Clear “Home” and “Food” markers for ecological context.
- Layering, legends, and animated wave propagation for maximal clarity.

### Challenges & Insights

Key difficulties included:

- Achieving robust transitions between traveling, obstacle avoidance, and returning.
- Ensuring the Mandarinfish always commenced its journey from “home,” especially when obstacles were positioned close by.
- Managing boundary cases where avoidance could dominate, sometimes leading to unexpected or non-optimal navigation—true to both synthetic and biological systems.

Iterative refinement and dialogue between code, biological principle, and visual output formed the heart of this project.

### Notable Implementation Challenges

Throughout development, several technical and logical challenges arose:

- Head orientation and directionality:
Initial versions occasionally generated backbone waves propagating in the wrong direction, resulting in the Mandarinfish’s head pointing away from its intended trajectory.

- Robust obstacle avoidance:
Tuning the geometric detection and avoidance response required careful adjustment—too sensitive, and the fish would begin avoidance too early; too lax, and it risked intersecting the coral.

- Complete arc (“full turn”) constraint:
Achieving a visually and behaviorally satisfying avoidance arc demanded a minimum turn angle (e.g., quarter or half-circle), preventing abrupt direction changes and unrealistic shortcuts.

- Goal reaching and return:
Ensuring the Mandarinfish both departed from the “home” location and arrived precisely at the food target (and returned) required synchronizing position/angle updates and careful threshold selection.

Each issue was addressed through parameter tuning, code refinement, and iterative visualization—mirroring the kind of troubleshooting performed in both biological modeling and robotic control development.

---

## Conclusion

This project brings together biomechanics, behavioral modeling, and robotics within a unified Python simulation.
Despite minor technical and ecological challenges,
the resulting animated Mandarinfish reliably demonstrates undulatory swimming, purposeful foraging, and adaptive obstacle avoidance—all within a visually engaging, extensible framework.

The simulation is thus both scientifically robust and visually accessible, illustrating how bio-inspired code can bridge theory and application in modern robotics.
