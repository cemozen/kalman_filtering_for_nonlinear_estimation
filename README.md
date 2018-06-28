# kalman_filtering_for_nonlinear_estimation
## The Kalman Filter

The Kalman filter is an algorithm that uses the past measurements of the state of a system (also taking into account statistical noise and other inaccuracies) to predict the future state of the system. Its first use was on the Apollo missions to the Moon, but today Kalman filtering is extensively used in a vast array of applications in fields ranging from robotics to econometrics.   

The Kalman filter was originally invented to model linear systems. However, extensions of the method to deal with nonlinear systems have also been developed, such as the extended Kalman filter (EKF) and the unscented Kalman filter (UKF).

In the **unscented Kalman filter (UKF)**, the state distribution is approximated by Gaussian random variables (GRVs)  as in the extended Kalman filter (EKF). However the two methods differ in the way GRVs are propagated through the system dynamics: While the EKF propagates GRVs analytically through a first-order linearization of the non-linear system, the UKF uses a deterministic sampling approach, in which a minimal set of sample points (so-called *sigma points*) that capture the true mean and covariance of the GRV is propagated through the *true* nonlinear system. While the posterior mean and the covariance of the EKF achieves only first-order accuracy (Taylor expansion), which often yields sub-optimal performance, the UKF accuracy is in the 2nd order; thus, the UKF presents a superior alternative to the EKF. Remarkably, this performance advantage does not come at an extra computational cost. 

## Problem Definition
In this notebook, I use the Kalman filter approach (UKF) as a design tool to construct a dynamical system with a desired type of behavior. Qualitatively, (attractive) dynamical systems can exhibit three distinct types of dynamical behavior in the limit $t \rightarrow \infty$: *fixed points*, *oscillations* and *chaos*.
Accordingly a dynamical system with unknown parameters, can be designed (i.e. its parameters can be inferred) so that it displays a desired dynamical behavior. In such a problem, the UKF method is used in the context of *parameter estimation*. 
