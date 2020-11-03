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


## Problem solved 4


![](figures/problema8.png)

The robot in the figure is actuated by a motor-encoder-reducer assembly. The motor is AC type, whose maximum torque is 1 [Nm], and the maximum speed is 10,000 [rpm]. The gear is a Harmonic Drive type with a reduction ratio of 150:1 and efficiency of 90%. The encoder has 100 lines. The distance between the motor shaft and the end of the robot $l$ is 1 [m].

  * a) Calculate the maximum weight $Q$ that the robot can hold in its end effector.
  * b) Calculate the linear resolution of the movement in the robot's end effector in [mm].
  * c) If the motor runs at maximum velocity, what is the join angular velocity in [deg/s]?
  * d) Find a new encoder for a resolution of 0.01 [mm] in the end effector.

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

### Section b

The linear resolution of the robot corresponds to the minimum  displacement in the manipulator in the most unfavorable situation. In this case, there is not a position better or worse, so any position is valid for the calculation. The setting of $\theta=0$ will be chosen.

The following figure shows why the linear displacement in the manipulator is calculated as follows:

$
{X_p}={ \sin(\theta_{1}) \cdot L }
$

![](figures/p8_1.svg)

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



