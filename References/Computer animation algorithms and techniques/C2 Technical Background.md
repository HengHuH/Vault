2022-10-18, 18:22
Status: #reference
Tags: #game #animation

---

# Technical Background

2.1 Spaces and transformations
2.1.1 The display pipeline
object space -> world space -> eye space -> Image space -> screen space

a center of interest (COI)
eye position (EYE)

w = COI - EYE, u = w x (0, 1, 0), v = u x w

camera-centric coordinate system (u, v, w)

view frustum

field of view (FOV) is used to set up the perspective projection. The perspective transformation transforms the objects's data points from eye space to image space.

2.1.2 Homogeneous coordinates and the transformation matrix

2.1.3 concatenationg transformations: multiplying transformation matrices

Note: matrix multiplication is associative but not commutative （满足结合律，不满足交换律）

2.2 Orientation representation
2.2.1 Fixed-angle representation
2.2.2 Euler angle representation
2.2.3 Angle and axis representation
2.2.4 Quaternion representation
