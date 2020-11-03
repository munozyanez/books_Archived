<script>
MathJax = {
  tex: {
    inlineMath: [['$', '$'], ['\$', '\$']]
  },
  svg: {
    fontCache: 'global'
  }
};
</script>
<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js">
</script>


# Morphology

## Problem 1

![](figures/p1%20%281%29.svg)

The mechanism of the figure consists of a parallelogram transmission moving the joint of a robot.

The distance between the axis of the motor-spindle and the support of the joint remains constant at 250 mm, being the arm that appears to the left of the joint extensible to maintain that distance constant.

The parallelogram is moved by an AC motor with resolver, whose maximum torque is 0.3 N·m.

This motor-spindle assembly offers a reduction ratio of 2000 m-¹ which allows the transformation of the motor's rotation into the translation movement of the spindle, with an efficiency of 80%.

The equations of the resolver are:

 *  $V1 = V\cdot\sin(\omega t)\cdot\sin(\theta_m)$,
 *  $V2 = V\cdot\sin(\omega t)\cdot\cos(\theta _m)$,

being $\theta_m$ the angle in which the motor is located and $V\cdot(\omega t)$ the excitation voltage of the resolver moving coil with $V$=24V. The resolver initial values are set to $V1$=0V , $V2$=0V , $\theta_m$=0 , $\theta_{art}$=0.

 1. Calculate the maximum weight _Q_ that the mechanism can hold at its end.
 2. Obtain the relation between the angle turned by the motor $\theta_m$ and the angle turned by the joint $\theta _{art}$.
 3. If the motor advances in positive direction giving 150 turns with final values in the stop instant of $V1$=11.91V , $V2$=10V. What is the value of $\theta _{art}$ at the stopping point if the zero position is the one drawn?
 4. What would be the range of the joint if the maximum length of the extension arm is 600 mm?

## Solution

### Section 1

The extensible part of the arm is at its minimum length when the arm is in the initial position, so the worst case position will be the initial position shown at the figure below.

![](figures/p1_1%20%281%29.svg)

In the equilibrium, $T1$ and $T2$ are equal and opposite ($T1 + T2 = 0$) , being:

 *  $T1 = Q \cdot 1,2$ N·m
 *  $T2 = F \cdot -0,25$ N·m. (Note that distance is negative in this case).

Therefore:

$
Q \cdot 1,2 -  F \cdot 0,25 =0 ;\quad {F} = {4,8 \cdot Q}
$

On the other hand, the forces in the spindle can be easily determined by an energy balance.

In the ideal situation, the energy transmitted by the motor to the spindle should be the same as that received by the arm. That is, $E_{rot} = E_{lin}$ , and in the general case $\eta \cdot E_{rot} = E_{lin}$, being:

 *  $E_{rot} = M \cdot \theta_m$, where $\theta$ is the angle of rotation in radians.
 *  $E_{lin} = F \cdot d$ , where $d$ is the linear distance traveled by the spindle.

There are two unknowns for $Q$. One is the weight that the robot is capable of _supporting_ at its end, and the other is the weight that it is capable of _moving_.

The first one is solved by the energy balance for the ideal case, since it is a static situation, in which $E_{rot} = E_{lin}$. It is recommended as an exercise.

The second is solved by dividing the two energy equations, taking into account that $ \eta ={ 0.8 } $ :

$
\eta = {E_{lin} \over E_{rot}} ={ {F \cdot d} \over {M \cdot \theta_m} }; \quad F = {\theta \over d} \cdot M \cdot \eta
$

According to the statement, ${\theta \over d}$ = 2000 m-¹. As it is not specified, it is assumed that the transmission is expressed in rad/m.

To solve the section, we substitute the values:

$
F = {\theta \over d} \cdot M \cdot \eta = 2000 \cdot 0.3 \cdot 0.8 = F = 480 N
$

And as $F = 4.8 \cdot Q$, $Q = {F \over 4.8} = {480 \over 4.8} = 100 N \approx 10Kg$.

### Section 2

The spindle transmission has the ratio $\frac{1}{N}={d \over \theta_m} = {1\over2000}$ m/rad. Now the equivalence between $d$ and $\theta_{art}$ is calculated.

![](figures/p1_2%20%281%29.svg)

According to the figure, the trigonometric equations that relate $d$ to $\theta_{art}$ are

 *  $h\cdot\sin{\theta_{art}} = d$
 *  $h\cdot\cos{\theta_{art}} = 0,25$

Dividing these two equations, it results:

$
\tan{\theta_{art}} = {d \over 0,25} \quad ; \quad
d=0,25 \tan{\theta_{art}};
$

And replacing, it results:

$
{ {\theta_m/2000}\over{0,25}} = {\tan{\theta_{art}}} \quad\rightarrow\quad
{\theta_{art}} = {\arctan {\theta_m \over 500} }
$

### Section 3

Dividing the equations of the resolver results in:

$
{ \frac{V1}{V2}={ {V\cdot\sin(\omega t)\cdot\sin(\theta_m)}\over{
 V\cdot\sin(\omega t)\cdot\cos(\theta _m)} } }\quad;\quad
{ {V1 \over V2} ={ \tan(\theta _m) } }
$

Since only the instantaneous values of $V1$ and $V2$ are known at stop, it is not possible to know a priori if they are in phase with the reference sine wave of the resolver.

It is assumed that they are, so the values of $\sin(\theta_m)$ and $\cos(\theta_m)$ are both positive, which implies that the rotation angle must be in the first quadrant.

Substituting, the current value of $\theta _m$ results:

$
{ {V1 \over V2} ={ \tan(\theta _m) } }= {11.91 \over 10} = {1.191}\quad\rightarrow\quad
{\theta _m} = {\arctan(1.191)}= {0.87 \ rad \approx 50\deg}
$

As there are $150$ turns ($942.48$ rad) already, the value of the final angle is $943.35$ rad

Substituting this value for the above equation results in an angle of :

$
{\theta_{art}} = {\arctan {943.35 \ rad \over 500}} \quad\rightarrow\quad
{\theta_{art}} = {1.08 \ rad = 62.08\deg}
$

### Section 4

Considering that $h\cdot\cos({\theta_{art}}) = 0.25$ (see section 2), and replacing the value of h by 600 mm (0.6 m) results:

$
{\cos(\theta_{art})} = 0,42\quad\rightarrow\quad
\theta_{art} = 1,14 \ rad = 65,38\deg \approx 65\deg
$

This means that the range of the joint is ($-65$ deg,$+65$ deg).
## Problem 2

![](figures/problema2%20%281%29.png)

Given the 5 DOF robot in the figure, calculate:

 *  a) The joint 3 ($q_3$) is moved by an AC Motor - Brake - Harmonic Drive assembly, being the data of the latter: reduction ratio 120:1, efficiency of 93%.
    1. If the maximum static load to be carried by the robot is 80 Newton, what should be the maximum torque (N·m) to be supported by a brake located on the motor axis, applying a safety coefficient of 30%?
    2. If the motor is rotating at 900 rpm, at what speed is the joint rotating?
 *  b) Joint 1 ($q_1$) is moved by an AC Motor - Brake - Resolver - Harmonic Drive - Rack and Pinion Transmission assembly. The Harmonic Drive has a ratio of $175:1$ and an efficiency of 95%. In the rack and pinion drive, the effective radius of the pinion is 0.3 m and its efficiency is 75%. Being $\theta_m$ the angle in which the motor is located and the excitation voltage of the resolver moving coil with $V=24$V.

    1. If we start from $\theta_m$=0 , and the motor advances in positive direction, indicating the resolver 350 steps by zero, giving final values in the stop instant of $V1$=17.32V , $V2$=10V. What is the value of $q_1$ in the stop point?
    2. What will be the linear speed of the joint if the motor turns at 110 rpm?

## Solution

### Section a1

If the maximum load is $Q=80N$, applying a safety coefficient of $30\%$, the considered load results in $P=1.3\cdot80N=104N$.

The worst position for $q_3$ is the one shown in the figure, and corresponds to the angle $q_3=0$ deg and $q_4=90$ deg.

![](figures/p2_1.svg)

Torque in $q_3$ will be $M_3=P(d+e)$, therefore $M_3 = 104(d+e)$.

To stop the joint by means of the brake, the transmission ratio must be considered, but in brake condition, the gear input is on the side of the joint and the output on the side of the motor. Note that friction losses will help to stop the motor. Dividing the two energy equations, and taking $\eta ={ 0.93 }$, results in:

$
\eta = {E_{o} \over E_{i}} = {E_{m3} \over E_{3}} ={ {M_{m3} \cdot \theta_{m3}} \over {M_{3} \cdot \theta_{3}} } \quad;\quad M_{m3} = { {M_3 \cdot \eta} \cdot {\theta_{3} \over \theta_{m3} }  }
$

To solve, the values are replaced:

$
M_{m3} = { {104(d+e) \cdot 0.93} \cdot {1 \over 120 }  } = {0.806(d+e)} \quad  [\text N\cdot \text m]
$

### Section a2

Using gear transmission ratio $N=120$:

$
N={q_{i} \over q_{o} } = {\dot q_{m3} \over \dot q_{3} } ;\quad
{\dot q_{3}} = {\dot q_{m3}  \over N  }
$

And substituting, the result is:

$
\dot q_{3} = {900\text{[rpm]} \over 120 } = {7,5} \text{[rpm]}
$

### Section b1

Dividing the equations of the resolver results in:

$
{ {V1 \over V2} ={ \tan(\theta _m) } ={17.32 \over 10}}
$

Assuming that the sinusoidal is in positive phase, and substituting, the current value of $\theta _m$ results:

$
{\theta _m} = {\arctan(1,732)}= {1,047 \ rad \approx 60\deg}
$

Since 350 turns have been counted ($2199.11[\text{rad}]$) , the value of the final angle on the motor axis is $q_{m1}=2200.16\text{[rad]}$
The harmonic drive ratio is $175:1$,therefore $N_h=175$, so the final angle on the harmonic output shaft is $q_{h1}={2200.16/175}=12.57 \text{[rad]}$

Now, the rack-and-pinion transmission has an effective pinion radius of 0.3 [m], which means that the transmission ratio is $N_p = \frac{q_{h1}}{d_1}=\frac{1 rad}{0.3 m}= \frac{1}{0.3} \text{[rad/m]}$.

The output shaft of the harmonic drive is applied to the input shaft of the rack-pinion transmission, which means that

$
d_1= \frac{q_{h1}}{N_p}
$

Which means, considering $\frac{1}{N_p} = {0.3} \text{[m/rad]}$, a result of:

$
d_1=0.3\text{[m/rad]} \cdot 12.57[rad]=3.77[m]
$

### Section b2

Transmission ratios can be combined by multiplicationt, therefore:

$
N=N_p \cdot N_h = {175\over0,3}\text{[rad/m]} =\frac{q_{m1}}{d_1},
$

and the same ratio can be used for kinematic variables, as velocities and accelerations, therefore:

$
v_1=\frac{\dot{q}\_{m1}}{N}
$

And replacing the corresponding values, using $\dot{q}\_{m1}=1100 \cdot {2\pi}/{60} = 115.19 \text{[rad/s]} $ the result is

$
v_1={0.3\over175}[m/rad] \cdot 115.19[rad/s]=0.20[m/s]
$


