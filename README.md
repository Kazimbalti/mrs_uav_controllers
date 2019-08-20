# MRS Controllers

* *SO3 controller*
  * non-linear state feedback capable of precise reference tracking and fast manouvres
  * pros: Precise control, fast response, fast convergence
  * cons: Sensitive to measurement noise, requires feasible and smooth reference
  * _Lee, 2010, "Geometric tracking control of a quadrotor UAV on SE(3)"_
* *MPC controller*
  * nonlinear attitude and thrust control + Linear MPC for acceleration feedforward
  * pros: Robust control, immune to measurement noise and reference infeasibilities
  * cons: Slow convergence, only for slow speeds (< 2 m/s), may have large control errors while tracking motion
* Acceleration controller
  * based on the MPC controller
  * nonlinear attitude and thrust control + Linear MPC for acceleration feedforward for vertical control
    * vertical reference can be desired position or velocity
  * physics-based desired acceleration for horizontal control (feed-forward from the reference)
  * pros: Robust control, immune to measurement noise and reference infeasibilities
  * cons: Slow convergence, only for slow speeds (< 2 m/s), may have large control errors
* Attitude controller
  * the attitude part of the SO(3), used mainly for gain tuning with a gamepad
* NSF controller
  * obsolete nonlinear state feedback, performance-wise similar to the SO(3)
  * should not be used in practice
  * is kept around for educational and testing purposes
* Failsafe controller
  * feed-forward landing routing used to land without the used of a state estimator
