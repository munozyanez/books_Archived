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

## Problema resuelto 1

![](.gitbook/assets/p1%20%281%29.svg)

The mechanism of the figure consists of a parallelogram transmission moving the joint of a robot.

The distance between the axis of the motor-spindle and the support of the joint remains constant at 250 mm, being the arm that appears to the left of the joint extensible to maintain that distance constant.

The parallelogram is moved by an AC motor with resolver, whose maximum torque is 0.3 N·m.

This motor-spindle assembly offers a reduction ratio of 2000 m-¹ which allows the transformation of the motor's rotation into the translation movement of the spindle, with an efficiency of 80%.

The equations of the resolver are:

* $V1 = V\cdot\sin(\omega t)\cdot\sin(\theta_m)$,
* $V2 = V\cdot\sin(\omega t)\cdot\cos(\theta _m)$,

being $\theta_m$ the angle in which the motor is located and $V\cdot(\omega t)$ the excitation voltage of the resolver moving coil with $V$=24V. The resolver initial values are set to $V1$=0V , $V2$=0V , $\theta_m$=0 , $\theta_{art}$=0.

1. Calculate the maximum weight _Q_ that the mechanism can hold at its end.
2. Obtain the relation between the angle turned by the motor $\theta_m$ and the angle turned by the joint $\theta _{art}$.
3. If the motor advances in positive direction giving 150 turns with final values in the stop instant of $V1$=11.91V , $V2$=10V. What is the value of $\theta _{art}$ at the stopping point if the zero position is the one drawn?
4. What would be the range of the joint if the maximum length of the extension arm is 600 mm?

## Solution

### Section 1

The extension arm is at its minimum length when the arm is in the initial position, so the most unfavorable position will be the initial position.

![](.gitbook/assets/p1_1%20%281%29.svg)

In the equilibrium, $T1$ and $T2$ are equal and opposite ($T1 = -T2$) , being:

* $T1 = Q \cdot 1,2$
* $T2 = F \cdot -0,25$ N·m

Dividing the above equations, it is obtained:

$
-1 = {Q \over F} \cdot {1,2 \over -0,25} ;\quad {F} = {4,8 \cdot Q}
$

On the other hand, the balance of forces in the spindle can be easily done by an energy balance.

In the ideal situation, the energy transmitted by the motor to the spindle should be the same as that received by the arm. That is, $E_{rot} = E_{lin}$ , and in the general case $\eta \cdot E_{rot} = E_{lin}$, being:

* $E_{rot} = M \cdot \theta_m$, where $\theta$ is the angle of rotation in radians.
* $E_{lin} = F \cdot d$ , where $d$ is the linear distance traveled by the spindle.

There are two unknowns for $Q$. One is the weight that the robot is capable of _supporting_ at its end, and the other is the weight that it is capable of _moving_.

The first one is solved by the energy balance for the ideal case, since it is a static situation, in which $E_{rot} = E_{lin}$. It is left as an exercise.

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

### Apartado 2

The spindle transmission has the ratio ${d \over \theta_m} = {1\over2000}$ m/rad. Now the relationship between $d$ and $\theta_{art}$ is calculated.

![](.gitbook/assets/p1_2%20%281%29.svg)

According to the figure, the trigonometric equations that relate $d$ to $\theta_{art}$ are

* $h\cdot\sin{\theta_{art}} = d$
* $h\cdot\cos{\theta_{art}} = 0,25$

Dividing these two equations, it results:

$
\tan{\theta_{art}} = {d \over 0,25} \quad ; \quad
d=0,25 \tan{\theta_{art}};
$

Y sustituyendo, resulta:

$
{ {\theta_m/2000}\over{0,25}} = {\tan{\theta_{art}}} \quad\rightarrow\quad
{\theta_{art}} = {\arctan {\theta_m \over 500} }
$

### Apartado 3

Dividing the equations of the resolver results in:

$
{ { {V1 = V\cdot\sin(\omega t)\cdot\sin(\theta_m)}\over{
V2 }={ V\cdot\sin(\omega t)\cdot\cos(\theta _m)} } }\quad;\quad
{ {V1 \over V2} ={ \tan(\theta _m) } }
$

Since only the instantaneous values of $V1$ and $V2$ are known at stop, it is not possible to know a priori if they are in phase with the reference sine wave of the resolver.

It is assumed that they are, so the values of $\sin(\theta_m)$ and $\cos(\theta_m)$ are both positive, which implies that the rotation angle must be in the first quadrant.

Substituting, the current value of $\theta _m$ results:

$
{ {V1 \over V2} ={ \tan(\theta _m) } }= {11.91 \over 10} = {1.191}\quad\rightarrow\quad
{\theta _m} = {\arctan(1.191)}= {0.87 \ rad \approx 50\deg}
$

As there are $150$ turns ($942.48$ rad) above, the value of the final angle is $943.35$ rad

Substituting this value for the above equation results in an angle of :

$
{\theta_{art}} = {\arctan {943.35 \ rad \over 500}} \quad\rightarrow\quad
{\theta_{art}} = {1.08 \ rad = 62.08\deg}
$

### Apartado 4

Taking into account that $h\cdot\cos({\theta_{art}}) = 0.25$ (see section 2), and replacing the value of h by 600 mm (0.6 m) results:

$
{\cos(\theta_{art})} = 0,42\quad\rightarrow\quad
\theta_{art} = 1,14 \ rad = 65,38\deg \approx 65\deg
$

This means that the range of the joint is ($-65$ deg,$+65$ deg).
## Problem 2

![](.gitbook/assets/problema2%20%281%29.png)

Given the 5 DOF robot in the figure, calculate:

* a) The joint 3 ($q_3$) is moved by an AC Motor - Brake - Harmonic Drive assembly, being the data of the latter: reduction ratio 120:1, efficiency of 93%.
    1. If the maximum static load to be carried by the robot is 80 Newton, what should be the maximum torque (N·m) to be supported by a brake located on the motor axis, applying a safety coefficient of 30%?
    2. If the motor is rotating at 900 rpm, at what speed is the joint rotating?
* b) Joint 1 ($q_1$) is moved by an AC Motor - Brake - Resolver - Harmonic Drive - Rack and Pinion Transmission assembly. The Harmonic Drive has a ratio of $175:1$ and an efficiency of 95%. In the rack and pinion drive, the effective radius of the pinion is 0.3 m and its efficiency is 75%. Being $\theta_m$ the angle in which the motor is located and the excitation voltage of the resolver moving coil with $V=24$V.

    1. If we start from $\theta_m$=0 , and the motor advances in positive direction, indicating the resolver 350 steps by zero, giving final values in the stop instant of $V1$=17.32V , $V2$=10V. What is the value of $q_1$ in the stop point?
    2. What will be the linear speed of the joint if the motor turns at 110 rpm?

## Solution

### Section a1

If the maximum load is $Q=80N$, applying a safety coefficient of $30\%$, the considered load results in $P=1.3\cdot80N=104N$.

The worst position for $q_3$ is the one shown in the figure, and corresponds to the angle $q_3=0$ deg and $q_4=90$ deg.

![](.gitbook/assets/p2_1.svg)

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

Since 350 turns have been counted $2199.11[\text{rad}]$ , the value of the final angle on the motor axis is $q_{m1}=2200.16[rad]$
The harmonic drive ratio is $175:1$, so the final angle on the harmonic output shaft is $q_{h1}={2200.16/175}=12.57 [rad]$

Now, the rack-and-pinion transmission has an effective pinion radius of 0.3 [m], which means that the transmission ratio is $R_p=0.3 [m/rad]$.

The output shaft of the harmonic drive is applied to the input shaft of the rack-pinion transmission, which means that

$
q_1=R_p \cdot q_{h1}
$

Which means:

$
q_1=0.3\text{[m/rad]} \cdot 12.57[rad]=3.77[m]
$

### Apartado b2

In a similar way to the previous section a2, it can be said that

$
v_1=R_p R_h v_{m1}=R v_{m1}
$

And substituting the corresponding values, the result is

$
v_1={0,3\over175}[m/rad] \cdot 115,19[rad/s]=0,20[m/s]
$

## Problema resuelto 3

![](.gitbook/assets/p3.svg)

Para el robot de 2 GDL $$\theta_1$ y $\theta_2$$ de la figura anterior, diseñar los actuadores y sensores. Estos están compuestos, en cada eje, por un motor DC con encoder en su eje y un engranaje. Calcular:

1. Las reducciones que tienen que tener los reductores, si se conoce que:
   * La velocidad máxima de los motores. $\dot\theta_{mi}=6000 \text{[rpm]}$.
   * Al mover cada motor por separado $estando el otro parado$, la velocidad máxima de la trayectoria en el extremo del robot. $V_{max}=3000 \text{[mm/seg]}$.
2. La resolución que tienen que tener los encoders de los ejes si se desea una precisión total de posicionamiento en el extremo de 0,01 \[mm\] $los reductores son de juego cero$.
3. El máximo peso que puede levantar el robot en su extremo en las condiciones mas desfavorables, si se conoce que:
   * El par motor nominal $continuo$ de cada motor es de $T_1=T_2=1$N·m.
   * El coeficiente de aprovechamiento de los reductores es de $\eta=80\%$.
   * Los motores no tienen frenos.

## Solución

### Apartado 1

Para ambas articulaciones, se debe cumplir que:

$
\dot\theta_{mi}*R_i=\dot\theta_i
$

Por otra parte, la velocidad lineal en el extremo opuesto a la articulación se calcula mediante la fórmula de movimiento circular del sólido rígido $$V_p=\dot\theta_i*d$$, siendo $d$ la distancia entre el centro de rotación y el punto $p$ dentro del sólido.

Combinando las dos ecuaciones, se obtiene lo siguiente:

$
V_p=\dot\theta_{mi}*R_i*d
$

Hay que prestar atención al hecho de que $d$ se refiere a la distancia del punto$$i$$ al eje de rotación, por tanto, una rotación en q1 genera velocidades lineales en todos los puntos del robot, y en particular $V_1$ y $V_2$.

El caso más desfavorable para $\theta_1$, coincide con el valor máximo de $d$, y esto ocurre con $\theta_2=0 \rightarrow d=1,2+2=3,2\text{[m]}$, y la velocidad en el extremo del robot, $V_2$. Particularizando la ecuación para este caso sería:

$
{V_2}={\dot\theta_{m1}*R_1*3,2}
$

Sustituyendo valores, y teniendo en cuenta que $V_2\le V_{max}$ y que $\dot\theta_{m1}=6000 \text{[rpm]}=628,32 \text{[rad/s]}$ resulta:

$
{V_2}={628,32\text{[rad/s]}*R_1*3,2\text{[m]}}\le{3 \text{[m/s]}}
$

$
{R_1}\le{ {3\text{[m/s]}}\over{628,32\text{[rad/s]}*3,2\text{[m]}} }={ {1}\over{670,21} }
$

$
{R_1}={ {1}\over{700} }
$

Para $\theta_2$, la distancia del punto más alejado es $d=2\text{[m]}$, y la velocidad en el extremo sigue siendo $V_2$. Particularizando la ecuación para este caso sería:

$
{V_2}={\dot\theta_{m2}*R_2*2}
$

Sustituyendo valores, y teniendo en cuenta que $V_2\le V_{max}$ y que $\dot\theta_{m2}=6000 \text{[rpm]}=628,32 \text{[rad/s]}$ resulta:

$
{V_2}={628,32\text{[rad/s]}*R_2*2\text{[m]}}\le{3 \text{[m/s]}}
$

$
{R_2}\le{ {3\text{[m/s]}}\over{628,32\text{[rad/s]}*2\text{[m]}} }={ {1}\over{418,88} }
$

$
{R_2}={ {1}\over{500} }
$

### Apartado 2

El desplazamiento $X$ se calcula mediante la fórmula de movimiento circular del sólido rígido $$X_p=\theta_i*d$$, siendo $d$ la distancia entre el centro de rotación y el punto $p$ dentro del sólido. Teniendo en cuenta la reducción y el límite de desplazamiento resulta:

$
{X_p}={ \theta_{mi}*R_i*d }\le{ X_{min} }
$

Esto implica que:

$
{ \theta_{mi} }\le{ {X_{min}}\over{R_i*d} }
$

La situación más desfavorable es la que provoca un desplazamiento mayor en el extremo $$X_2$$. Igual que en el apartado anterior, las distancias mas desfavorables son $d=3,2\text{[m]}$ para $\theta_1$ y $d=2\text{[m]}$ para $\theta_2$.

Particularizando para $\theta_{m1}$, $$d=3,2\text{[m]}; {R_1}={1/700}$$

$
{ \theta_{m1} }\le
{ {0,01\text{[mm]}}\over{(1/700)*3,2}\text{[m]} }=
{ {0,01}\over{(1/700)*3,2} }\cdot{ {\text{[m]}}\over{1000\text{[m]}} }=
2,19\times10^{-03}\text{[rad]}
$

Particularizando para $\theta_{m2}$, $$d=2\text{[m]}; {R_2}={1/500}$$

$
{ \theta_{m2} }\le
{ {0,01\text{[mm]}}\over{(1/500)*2}\text{[m]} }=
{ {0,01}\over{(1/500)*2} }\cdot{ {\text{[m]}}\over{1000\text{[m]}} }=
2,50\times10^{-03}\text{[rad]}
$

El menor de los dos valores $ $2,19\times10^{-03}\mathrm{[rad]}$ $ corresponde a la precisión mínima del encoder.

Como hay 6,28 \[rad\] en cada vuelta completa y el menor de los valores es $\theta_{m1}= 2,19\times10^{-03}\text{[rad]}$:

$
P_e=\frac{6,28\mathrm{[rad/vuelta]}}{2,19\times10^{-03}\mathrm{[rad]}}=2872,31\mathrm{[pulsos/vuelta]}
$

Se puede comprobar ahora, que para un ángulo de $\theta_{m1}= 2,19\times10^{-03}\mathrm{[rad]}$, el desplazamiento es:

$
{X_p}={ 2,19\times10^{-03}\mathrm{[rad]}*\frac{1}{700}*3,2\mathrm{[m]}}={0,01\mathrm{[mm]}}\le{ X_{min} }
$

Hay que tener en cuenta, que el desplazamiento calculado corresponde al movimiento circular del manipulador. Como se puede apreciar en la siguiente figura, éste desplazamiento es mayor que el movimiento lineal.

![](.gitbook/assets/p3_2.svg)

En concreto se corresponde con el siguiente cálculo:

$
{X_p}={ \sin(\theta_{mi}*R_i)*d }\le{ X_{min} }
$

Y sustituyendo valores, resulta:

$
{X_p}={ \sin(2,19\times10^{-03}\mathrm{[rad]}*\frac{1}{700})*3,2\mathrm{[m]}}={0,01\mathrm{[mm]}}\le{ X_{min} }
$

### Apartado 3

Para mover la articulación mediante el motor, se aplican la reducción y el rendimiento de la transimsión. Dividiendo las dos ecuaciones de energía, y teniendo en cuenta que $\eta ={ E \over E_m }={ 0,80 }$ resulta que:

$
\eta = {E_{1} \over E_{m1}}=
{ {M_1*\theta_{1}} \over { M_{m1}*\theta_{m1}} } \quad;\quad 
M_{1} = { {M_{m1}*\eta}*{\theta_{m1} \over \theta_{1}} }
$

Para resolver, se sustituyen los valores:

$
M_{1} = { {1\mathrm{[N \cdot m]}*0,80}*\frac{700}{1} }=
{560,00\mathrm{[N \cdot m]}}
$

Haciendo el cálculo mecánico, que se deja como ejercicio, se demuestra que la posición mas desfavorable es la que se muestra en la siguiente figura:

![](.gitbook/assets/p3_1.svg)

Por tanto la máxima carga que puede mover el robot en la posición mas desfavorable se calcula como sigue:

$
T_1={ P*d } \Rightarrow P=T_1/d
$

Y sustituyendo:

$
P=\frac {560,00\mathrm{[N \cdot m]}} {3,2\mathrm{[m]}}=
{175,00\mathrm{[N]} \rightarrow 17,84\mathrm{[Kg]}}
$

## Problema resuelto 4

![](.gitbook/assets/problema8.png)

El robot de la figura se mueve mediante un conjunto motor-encoder-reductor. El motor es de tipo AC, cuyo par máximo es de 1 \[N·m\], y la velocidad máxima es de 10000 rpm. El reductor es del tipo Harmonic Drive con relación d reducción de 150:1 y rendimiento del 90%.El encoder tiene 100 cuentas por vuelta. La distancia entre el eje del motor y el extremo del robot $l$ es de 1 \[m\].  
Se pide:

* a) Calcular el peso máximo $Q$ que puede llevar el robot en su extremo.
* b) Calcular la resolución lineal del movimiento en el extremo del robot.
* c) Si el motor gira a su velocidad máxima, ¿a qué velocidad angular $en \[grados/s\]$ está girando la articulación?

## Solución

### Apartado a

El par solicitado en el caso más desfavorable, es:

$
T_1=Q*l
$

Que debe ser igual y de sentido contrario al par ejercido por la articulación.  
Por lo tanto:

$
{ Q = T_1/l }
$

Haciendo un balance de energía en la articulación:

$
\eta = {E_{1} \over E_{m1}} ={ {T_1*\theta_1} \over {T_{1m}*\theta_{1m}} }; \quad 
T_1 = {\theta_{1m} \over \theta_{1}} * T_{1m} * \eta
$

Y sustituyendo los valores, resulta:

$
T_1 = { {150 \over 1}* 1\mathrm{[N \cdot m]} * 0,90} = 135 \mathrm{[N \cdot m]}
$

Teniendo en cuenta lo anterior:

$
{ Q = T_1/l } = 
{135 \mathrm{[N \cdot m]} / 1 \mathrm{[m]}}=
135 \mathrm{[N]}
$

### Apartado b

La resolución lineal del robot se corresponde con el desplazamiento **lineal** mínimo en el manipulador en la situación más desfavorable. En este caso, no hay una posición mas desfavorable, así que culaquier posición vale para el cálculo. Se escogerá la cofiguración de $\theta=0$.

En la siguiente figura se aprecia por qué el desplazamiento lineal en el manipulador se calcula de la siguiente manera:

$
{X_p}={ \sin(\theta_{1})*L }
$

![](.gitbook/assets/p8_1%20%281%29.svg)

En el caso de la articulación, se sabe que la articulación tiene una reductora de 150:1.  
El encoder tiene 100 cuentas por vuelta. Como no se sabe si estas cuentas son pulsos o cambios en el sistema de medida, se asume que son cambios en el sensor. Esto significa que se puede multiplicar por cuatro mediante cuadratura de la señal, luego $P_e=4*100=400\mathrm{[pulsos/vuelta]}$

Entonces, el ángulo mínimo de giro para el motor, será:

$
\theta_{m1p}={6,28\mathrm{[rad]}/400\mathrm{[pulsos]} }= { 0,0157 \mathrm{[rad/pulso]} }
$

Como ocurre que $\theta_{1p}=R_1*\theta_{m1p}$, se puede afirmar que:

$
{X_p}={ \sin(R_1*\theta_{m1p})*L }
$

Y después de sustituir valores, resulta:

$
{X_p}={ \sin(\frac{1}{150}*0,0157 \mathrm{[rad/pulso]})*1\mathrm{[m]} }=
{ 0,0001\mathrm{[m]}=0,1\mathrm{[mm]} }
$

Se deja como ejercicio calcular el desplazamiento para movimiento circular y compararlo con el desplazamiento lineal del manipulador.

### Apartado c

Conociendo la relación de transmisión del engranaje, se puede afirmar que:

$
{ \frac{\dot\theta_{1}}{\dot\theta_{m1}} }={ R_1 }={ \frac{1}{150} };\quad
{ \dot\theta_{1} }={ \frac{\dot\theta_{m1}}{150} }
$

Por otro lado, se sabe que

$
{\dot\theta_{m1max}}=10000\mathrm{[rpm]} = 
{ 10000\mathrm{[vuelta/min]}*\frac{360\mathrm{[\deg/vuelta]}}{60\mathrm{[s/min]}} }=
{60000\mathrm{[\deg/s]}}
$

Entonces, sustituyendo, se tiene que:

$
{ \dot\theta_{1} }={ \frac{60000\mathrm{[\deg/s]}}{150} }=
{400\mathrm{[\deg/s]}}
$

Fin del capítulo.

