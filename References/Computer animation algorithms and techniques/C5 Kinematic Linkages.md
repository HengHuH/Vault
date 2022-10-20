2022-10-18, 18:27
Status: #reference
Tags: #game_dev #animation

---

# Kinematic Linkages

5.1 Hierarchical modeling
Articulated
The joints of xxx allow motion in one direction and are said to have one degree of freedom (DOF)
Revolute joint
Prismatic joint
Structures in which more than one DOF are coincident are called Complex joints.
The planar joint
The ball-and-socket joint.

5.1.1 Data structure for hierarchical modeling
Human figures and animals are conveniently modeled as hierarchical linkages. Suck linkages can be represented by a tree structure of nodes connected by arcs.

5.1.2 Local coordinate frames

5.2 Forward kinematics

5.3 Inverse kinematics
5.3.1 Solving a simple system by analysis
For sufficiently simple mechanisms, the joint values of a final desired position can be determined analytically by inspecting the geometry of the linkage.
三角解析，限于一或两节

5.3.2 The Jacobian

5.3.3 Numeric solutions to IK
Solution using the inverse Jacobian
Adding more control
Alternative Jacobian
Avoiding the inverse: using the transpose of the Jacobian
Proceduralyy determining the angles: cyclic coordinate descent

5.4 Chapter summary
Hierarchical models are extremely useful for enforcing certain relationships among the elements so that the animator can concentrate on just the DOF remaining. Forward kinematics give the animator explicit contorl over each DOF but can become cumbersome whent the animation is trying to attain a specific position or orientation of an element at the end of a hierarchical chain. IK, using the inverse or pseudoinverse of the Jacobian, allows the animator to concentrate only on the conditions at the end of such a chain but might produce undesirable configurations. Additional control expressions can be added to the pseudoinverse Jacobian solution to express a preference for solutions of a certain character. However, thoese are al kinematic techniques. Often, more realistic motion is desired and physically based simulations are needed.
