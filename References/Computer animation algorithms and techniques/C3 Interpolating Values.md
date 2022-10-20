2022-10-18, 18:24
Status: #reference
Tags: #game #animation

---

# Interpolating Values

3.1.1 The appropriate function

Interpolation versus approximation
Complexity: The complexity of the underlying interpolation equation is of concern because this translates into computational effiency.
Continutiy: Mathematically, smoothness is determined by how many of the derivatives of the curve equation are continuous.
Global versus local control

Functions:
spline 样条曲线
Catmull-Rom Spline (only positional information)
Hermite formulation (only positional information)
Parabolic blending
B-spline
Bezier

3.2 Controlling the motion of a point along a curve
3.2.1 Computing arc length
The analytic approach to computing arc length
Estimating arc length by forward differencing
Find a point that is a givendistance along a curve

3.2.2 Speed Control

3.2.3 Ease-in / ease-out
Sine interpolation
Using sinusoidal pieces for acceleration and deceleration
Single cubic polynomial ease-in/ease-out
constant acceleration: parabolic ease-in/ease-out

3.2.4 General distance-time function
3.2.5 Curve fitting to position-time pairs

3.3 Interpolation of orientations

3.3.1 Interpolating quaternions
One of the most important reasons for choosing quaternions to represent orientation is that they can be easily interpolated. Most important, the quaternion representation avoids the condition known as gimbal lock, which can trouble the other commonly used representations such as fixed angles and Euler angles.

3.4 Working with paths
3.4.1 Path following
3.4.2 Orientation along a path
Use of the Frenet frame
3.4.3 Smooting a path
Smoothing with linear interpolation of adjacent values
Smoothing with cubic interpolation of adjacent values
Smoothing with convolution kernels
Smoothing with B-spline approximation

3.4.4 Determining a path along a surface
