# nagel_schreckenberg_extension
An extension of the nagel schreckenberg model for traffic and an analysis of the resulting traffic flow

---
\* The following introduction file can also be found in the notebook


## Introduction
The aim of this project is to explore how traffic patterns impact traffic flow. This work expands upon Nagel Schreckenberg's one-way ring road (Nagel & Schreckenberg, 1992) by incorporating an additional intersecting lane and a traffic light at the intersection. The project will answer how this simulation can be used in real life and explore the notion of optimisation in terms of traffic lights. The paper will also propose a number of extensions that this simulation could begin to incorporate or accomodate or account for.

## Rules of the Simulation
The following are rules used in the update section of the simulation. These are the rules that the simulation follows at each time step. Rules 1, 2, 3 and 5 are from the Nagel Schreckenberg Model. Rule 4 was developed for the purposes of this extension.

### Rule 1
If the car is travelling below maximum velocity AND the distance to the car directly in front is larger than the current velocity plus one, increase the velocity of the car by one. This is the rule for acceleration.

e.g. The car is travelling at 2, the maximum velocity is 5, and the distance to the next car is 5. The car is updated to a velocity of 3.

### Rule 2
If the distance to the car directly in front is less than OR equal to the current velocity, decrease the velocity of the car to the distance to the next car minus one. This is to avoid collisions.

e.g. The car is travelling at 5 and the distance to the next car is 4. The car is updated to a velocity of 3.

### Rule 3
If the current car velocity is larger than zero, with a certain probability, reduce the current velocity by one. This adds a degree of randomness to the simulation.

e.g. The car is travelling at 3, with a 10% probability, update the velocity of the car to 2

### Rule 4
If the traffic light is red, the velocity of the car is reduced to the distance to the traffic light minus one, bringing the car to a stop at the light. If the traffic light is green, the car travels as usual. Unless the car will update into the middle of the intersection. In that case, if the car is not at maximum velocity, the car speeds up through the intersection by one. If the car is travelling at maximum velocity, it slows down by one to avoid being caught in the middle of the intersection.

e.g. The light is red, the car is travelling at 4, the distance to the traffic light is 2. The velocity of the car is updated to 1.

e.g. The light is green, the car is travelling at 3, the distance to the traffic light is 2. The velocity of the car is not updated by this rule

e.g. The light is green, the car is travelling at 2, the maximum velocity is 5, the distance to the traffic light is 2. The velocity of the car is updated to 3.

e.g. The light is green, the car is travelling at 5, the maximum velocity is 5, the distance to the traffic light is 5. The velocity of the car is updated to 4.

### Rule 5
The cars move forward in accordance with their velocities with each time step.

e.g. The car is travelling at 4. The car's position is updated to be positioned 4 steps in front of where it previously was.

## Assumptions
Most, if not all, simulations have assumptions built into them, and this simulation model is no different. Below are some of the key assumptions:

* Cars do not overtake each other
* There are no accidents
* Cars respect the traffic signal
* Cars do not turn at the intersection
* All cars behave and act by the same rules
