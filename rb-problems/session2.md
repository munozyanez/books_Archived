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


## Problem 3

![](figures/p3.svg)

Consider the 2 DOF $\theta_1$ and $\theta_2$ in the figure, design the actuators and sensors. These are composed, in each axis, by a DC motor with encoder in its axis and a gear. Calculate:

1. The reductions that the reducers must have, if it is known that:
     * The maximum speed of the motors. $\dot\theta_{mi}=6000 \text{[rpm]}$.
     * When moving each motor separately being the other stopped, the maximum speed of the path at the end of the robot. $V_{max}=3000 \text{[mm/sec]}$.
2. The resolution that have to have the encoders of the axes if you want a total positioning accuracy at the end of 0.01 \[mm\] the gears are zero backlash.
3. The maximum weight that can lift the robot in its end in the conditions but unfavorable, if it is known that:
     * The nominal torque $continuous$ of each motor is $T_1=T_2=1$N·m.
     * The coefficient of use of the reducers is of $\eta=80\%$.
     * The motors have no brakes.

## Solution

### Section 1

For both joints, it must be fulfilled that

$
\dot\theta_{mi}N_i=\dot\theta_i
$

On the other hand, the linear velocity at the opposite end of the joint is calculated by the formula of circular motion of the rigid solid $V_p=\dot\theta_i \cdot d $, being $d$ the distance between the center of rotation and the point $p$ inside the solid.

Combining the two equations, the following is obtained:

$
V_p=\dot\theta_{mi}N_i \cdot d
$

Pay attention to the fact that $d$ refers to the distance from the point $i$ to the rotation axis, so a rotation in q1 generates linear velocities in all points of the robot, and in particular $V_1$ and $V_2$.

The worst case for $\theta_1$, coincides with the maximum value of $d$, and this occurs with $\theta_2=0 \rightarrow d=1.2+2=3.2\text{[m]}$, and the speed at the end of the robot, $V_2$. Particularizing the equation for this case would be:

$
{V_2}={\dot\theta_{m1}R_1 \cdot 3,2}
$

Substituting values, and taking into account that $V_2\le V_{max}$ and that $\dot\theta_{m1}=6000 \text{[rpm]}=628.32 \text{[rad/s]}$ results:

$
{V_2}={628,32\text{[rad/s]}R_1\cdot3,2\text{[m]}}\le{3 \text{[m/s]}}
$

$
{R_1}\le{ {3\text{[m/s]}}\over{628,32\text{[rad/s]}3,2\text{[m]}} }={ {1}\over{670,21} }
$

$
{R_1}={ {1}\over{700} }
$

For $\theta_2$, the distance from the farthest point is $d=2\text{[m]}$, and the speed at the end is still $V_2$. Particularizing the equation for this case would be

$
{V_2}={\dot\theta_{m2}R_2 \cdot 2}
$

Substituting values, and taking into account that $V_2\le V_{max}$ and that $\dot\theta_{m2}=6000 \text{[rpm]}=628.32 \text{[rad/s]}$ results:

$
{V_2}={628,32\text{[rad/s]}R_2 \cdot 2\text{[m]}}\le{3 \text{[m/s]}}
$

$
{R_2}\le{ {3\text{[m/s]}}\over{628,32\text{[rad/s]} \cdot 2\text{[m]}} }={ {1}\over{418,88} }
$

$
{R_2}={ {1}\over{500} }
$



### Section 3

To move the joint by means of the motor, the reduction and the performance of the transmission are applied. Dividing the two energy equations, and taking into account that $\eta ={ E \over E_m }={ 0.80 }$ results that:

$
\eta = {E_{1} \over E_{m1}}=
{ {M_1 \cdot \theta_{1}} \over { M_{m1} \cdot \theta_{m1}} } \quad;\quad
M_{1} = { {M_{m1} \cdot \eta} \cdot {\theta_{m1} \over \theta_{1}} }
$

To solve, the values are replaced:

$
M_{1} = { {1\mathrm{[N \cdot m]} \cdot 0,80} \cdot \frac{700}{1} }=
{560,00\mathrm{[N \cdot m]}}
$

Doing the mechanical calculation, it is demonstrated that the worst case position is the one shown in the following figure:

![](figures/p3_1.svg)

Therefore the maximum load that the robot can move in the most unfavorable position is calculated as follows:

$
T_1={ P \cdot d } \Rightarrow P=T_1/d
$

And replacing:

$
P=\frac {560,00\mathrm{[N \cdot m]}} {3,2\mathrm{[m]}}=
{175,00\mathrm{[N]} \rightarrow 17,84\mathrm{[Kg]}}
$

## Problem solved 4

![](figures/problema8.png)

The robot in the figure is moved by a motor-encoder-reducer assembly. The motor is AC type, whose maximum torque is 1 \[Nm\], and the maximum speed is 10,000 rpm. The gear is of the Harmonic Drive type with a reduction ratio of 150:1 and efficiency of 90%. The encoder has 100 beads per turn. The distance between the motor shaft and the end of the robot $l$ is 1 ? It is ordered:

     * a) Calculate the maximum weight $Q$ that can take the robot in its end.
     * b) Calculate the linear resolution of the movement in the end of the robot.
     * c) If the motor turns to its maximum speed, to what angular speed [deg/s] is turning the joint?

## Solution

### Section a

The pair requested in the worst case is:

$
T_1=Q \cdot l
$

It must be equal and opposite to the torque exerted by the joint.
Therefore:

$
{ Q = T_1/l }
$

Making an energy balance in the joint:

$
\eta = {E_{1} \over E_{m1}} ={ {T_1 \cdot \theta_1} \over {T_{1m} \cdot \theta_{1m}} }; \quad
T_1 = {\theta_{1m} \over \theta_{1}}  \cdot  T_{1m}  \cdot  \eta
$

And replacing the values, it turns out:

$
T_1 = { {150 \over 1} \cdot  1\mathrm{[N \cdot m]}  \cdot  0,90} = 135 \mathrm{[N \cdot m]}
$

Considering the above:
$
{ Q = T_1/l } =
{135 \mathrm{[N \cdot m]} / 1 \mathrm{[m]}}=
135 \mathrm{[N]}
$

### Apartado b

The linear resolution of the robot corresponds to the minimum  displacement in the manipulator in the most unfavorable situation. In this case, there is not a position better or worse, so any position is valid for the calculation. The setting of $\theta=0$ will be chosen.

The following figure shows why the linear displacement in the manipulator is calculated as follows:

$
{X_p}={ \sin(\theta_{1}) \cdot L }
$

![](figures/p8_1%20%281%29.svg)

In the case of the joint, the joint is known to have a 150:1 reduction ratio.
The encoder has 100 beads per turn. Since it is not known whether these counts are pulses or changes in the measurement system, it is assumed that they are changes in the sensor. This means that they can be multiplied by four by quadrature of the signal, then $P_e=4 \cdot 100=400\mathrm{[pulses/turn]}$

Then, the minimum turning angle for the engine will be:

$
\theta_{m1p}={6,28\mathrm{[rad]}/400\mathrm{[pulse]} }= { 0,0157 \mathrm{[rad/pulse]} }
$

As it happens that $\theta_{1p}=R_1 \cdot \theta_{m1p}$, it can be said that

$
{X_p}={ \sin(R_1 \cdot \theta_{m1p}) \cdot L }
$

And after replacing values, it results:

$
{X_p}={ \sin(\frac{1}{150} \cdot 0,0157 \mathrm{[rad/pulse]}) \cdot 1\mathrm{[m]} }=
{ 0,0001\mathrm{[m]}=0,1\mathrm{[mm]} }
$

It is proposed as an additional exercise to calculate the displacement for circular movement and compare it with the linear displacement of the manipulator.

### Section c

Knowing the transmission ratio of the gear, it can be said that:

$
{ \frac{\dot\theta_{1}}{\dot\theta_{m1}} }={ R_1 }={ \frac{1}{150} };\quad
{ \dot\theta_{1} }={ \frac{\dot\theta_{m1}}{150} }
$

On the other hand, it is known that

$
{\dot\theta_{m1max}}=10000\mathrm{[rpm]} = 
{ 10000\mathrm{[rev/min]} \cdot \frac{360\mathrm{[\deg/rev]}}{60\mathrm{[s/min]}} }=
{60000\mathrm{[\deg/s]}}
$

Then, replacing, you have to:
$
{ \dot\theta_{1} }={ \frac{60000\mathrm{[\deg/s]}}{150} }=
{400\mathrm{[\deg/s]}}
$



