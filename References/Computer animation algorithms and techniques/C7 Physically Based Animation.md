2022-10-18, 18:28
Status: #reference 
Tags:

---
# Physically Based Animation

7.1 Basic physica - a review
7.1.1 Spring-damper pair
7.2 Spring animation examples
7.2.1 Flexible objects

7.3 Particle systems
 some of the common assumptions:
Particles do not collide with other particles.
Particles do not cast shadows, except in an aggregate sense.
Particles only cast shadows on the rest of the environment, not on each other.
Particles do not reflect light --- they are each modeled as point light sources.

7.3.1 Particle generation
7.3.2 Particle attributes
7.3.3 Particle termination
7.3.4 Particle animation
7.3.5 Particle rendering
7.3.6 Particle system representation
7.3.7 Forces on particles
7.3.8 Particle life span

7.4 Rigid body simulation
7.4.1 Bodies in free fall
A note about numeric approximation
Equations of motion for a rigid body
Orientation and rotational movement
Center of mass
Forces
Momentum (动量）
Inertia tensor （惯性张量）
The equations

7.4.2 Bodies in collision
Colliding bodies
Particle-plane collision and kinematic response
The penalty method
Testing polyhedra
Impulse force of collision
Computing impulse forces
Friction
Resting contact

7.4.3 Dynamics of linked hierarchies
Constrained dynamics
The Featherstone equations

7.5 Cloth
7.5.1 Direct modeling of folds
7.5.2 Physically based modeling

7.6 Enforcing soft and hard constraints
7.6.1 Energy minimization
7.6.2 Space-time constraints

7.7 Chapter summary
If complex realistic motion is needed, the models used to control the motion can become complex and mathematically expensive. However, the resulting motion is oftentimes more natural looking and believable than that produced using kinematic thehniques. While modeling physics is a non-trivial task, oftentimes it is worth the investment. It should be noted that there has been much work in this area that has not been in this chapter. Some other physically based techniques are covered in later chapters that address specific animation tasks such as the animation of clothes and water.