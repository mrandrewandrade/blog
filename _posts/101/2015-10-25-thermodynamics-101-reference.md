---
layout: post
title: "Thermodynamics 101 Reference Sheet"
tagline: "Thermo is easy if you understand the basics"
category: [101 notes, school] 
tags: [engineering, thermodynamics, thermal, science]
last_updated: 2015-10-25
---


# assumptions

First lets start with some common assumptions (refer back here when they come up):

1. Kinetic and potential energy remains about constant ($$\Delta KE, \Delta PE ~= 0$$
2. Isobaric (pressure is constant)
3. Isothermal (temperature is constant)
4. Isovolumetic (total volume (V) is constant)
5. Rigid (change in volume is zero or $$dV = 0$$)
6. Adiabatic (heat transfer is zero or $$\dot Q = 0$$
7. Reversible (\dot P_s = 0)
8. Ideal Gas more below
9. stead-state or SS (change is zero or d/dt = 0)
10. steady flow or SD ($$ U_{IN}, h_{IN, ... = constant)
11. Liquids and solids have constant volume
12. Liquids are solids are assumed incompressible


## Laws

**zero law of thermodynamics:**
if two seperate bodies are in thermo equilibrium with a third, they the first two are in equilibrium. (think of the third body as a thermometer and the first two as non conected bodies)

**first law of thermodynamics: **  
chance in energy of system = energy into system - energy out of system + energy produced by system

**concervation of mass: **
change in mass of system =  mass into system - mass out of system + mass produced by system.

Note: both the mass produced and energy produced by system is usually equal to zero.


**second law of thermodynamics: **
energy has _quality_ in addition to having a _quantity_ (more about that later)

## properties 

** primary/fundamental properties:   **
basic dimentions which describe the universe as we know it (length, mass, time, temperature, electic current, amount of light, amount of matter)

** secondary properties: **
properties derived from the fundamental properties (ie velocity = length/time)

### Mass

I am not going to go into what mass is.  It relates to gravitational attraction and
$$E = m C^2$$

Its measured in grams in the SI system.

**Note:** unity conversion ratio
There is a difference between lbm pound mass (slug) and pound force lbf in the imperial system

pound mass or slug is the mass which accelerates by 1 ft/s when the force of one pound is exerted on it    

$$ 1 lbf = 32.174 lbm * ft/s^2$$

### Force
Force (F) is mass times acceleration or pressure times area, measured in newtons.

$$ F = P \times A = m g $$

Pressure is force divided by area and is measured in Pascals or Pa.

$$1 Pa = 1 \frac{N}{m^2} = 1 \frac{kg}{m \times s^2}$$

Note: **absolute pressure** is measured in an absolute vacuum (absolute zero pressure) and **guage pressure** is relative to atmosphere.  **Vacuum pressures** are when a pressure is less than atmosphere.  Mathematically this means:

$$P_{gage} = P_{abs} - P_{atm} = \rho g h$$

$$P_{vac} = P_{atm} - P_{abs}$$

PSI is pressure measured in pounds per square inch.  PSIg is measuring guage pressure, PSIa is measuring absolute pressure.

Pressure can also be measured from the following equations:

$$P = P_{gage} + P_{atm}$$

$$\Delta P = P_2 - P_1 = - \int \rho g dz$$

There are a bunch of devices with measure pressure, just look them up if ever you have to use them.

Pressure is the same in any fluid measured at the same depth.  Read the book, it explains it.

**intensive property** independant of mass/volume

** extensive propety** property dependant on size of system

**specific property** extensive property per unit mass

**density**  mass per unit volume

$$ \rho = \frac {m}{V}$$

**weight is a force**
$$ W = mg $$ (Newtons)

Where m is mass, and g is the acceleration due to gravity


**specific weight** is density times acceleration due to gravity
$$ \gamma = \rho g $$

I am using the follwing symbol for volume:  

$$\vee$$

**specific volume** is volume per unit mass

$$ \nu = \vee / m = 1 / \rho$$

specific gravity or relative density is the ratio of the density of a substance to the density of some standard substance at a specified temperature (ususally water at 4 degress C where the density is 1000 kh/m^3)

$$SG = \frac{\rho}{\rho_{H_2 O}}$$

## State Postulate

Okay now we now that we can use properties to descripte the state of a system  The thing is we don't need to specify *all* the properties to fix a state.  This means if we decine a sufficient number of properties, then we can determine the rest. As a different example if we know the distance and time someone traveled, we can determine their average velocity.  In the same way if we have two *independant* properties, then we can fix the state if all the other properties are functions of those two properties.  Being independant means that if one property is fixed, the other is still able to be varied.  Now let us call this a fancy term called **state postulate**.  The state postulate dictates how many number of properties is necessary to fix a state.

>>The state of a simple compresssible system is completly specific by two independant, intensive properties.

A simple compressible system is when there isn't any electrical, magnetic, gravitational, motion or surface tension effects (or those are so small they are assumed to be neglitable since they require external force to make).  Now if we add an signiticant effect on our system, we now need to add an additional property (for every unique type of effect).  For example if we want to consider gravational effect, we must consider z (for height/elevation).  Since temperature and specific volume are always indpendant, we can always use them to fix the state of a simple compressible system.  Why not pressure and temperature?  For example at sea (P = 1 atm) level water boild at 100 degrees C but on a mountain water can boil at a lower temperature.

## Processes, Paths and cycles


A **process** is then a system goes from one equilibrium state to another.  The exacty series of states which a system passes through is called the **path.**  This means that work is actaully path dependant, while the total energy change is not.  If you don't understand this, try and read chapter two of the Cengel textbook, I can't really explain how I understand this (or if I really do). I would suggest to read the path dependance dependance section for thermodynamic [work](https://en.wikipedia.org/wiki/Work_(thermodynamics))or [nonholonomic systems](https://en.wikipedia.org/wiki/Nonholonomic_system) on Wikipedia, but it is pretty complex and poorly explained there :(.

### Understanding assumptions

Now here is where those assumptions come in.  When someone says a process is isothermal, it means the path which the system takes stays a fixed temperature.  That is the temperature remains constant.  Isobaric means pressure remains constant etc. etc.  The systems follows a path based on the assumption

### Cycle

A system goes through a **cycle** if it returns to its initial state, that is the start and the end states are the same.

### Steady and Uniform

Steady means no change with time, uniform means no change with location.  You can use these terms in everyday life but if a Waterloo engineering student says he/she has a steady boyfriend/girlfriend they are probably lying.

A steady-flow process is when a fluid flows through a control volume steadily.  This means they can change with position,  but not with time.  Mass flowing at 1pm should be the same as mass flowing at 3 pm.  This means the energy contents of a control volume stays constant.

## Zeroth law of thermodynamics

Now its time for a law: if two bodies are in thermal equilibrium with a third, it means they are thermal equilibrium with each other (even if they are not in contact).  It means temperature measured at one point will be the exact same if the value measured is the same at another.  This is why thermometers work.



# Work
**work** form of energy defined as force multiplied by distance.

$$ W =  \int \overrightarrow{F} \dot{}  \overrightarrow{dx} = - \int PAdx = - \int P d\vee $$


Where F is force and x is a displacement vector, P is pressure, A is area.  Area multiplied by displacement is a volume.



SI unit is joules, english system is Btu (British thermal unit)

Think of a Joule as a newton- meter

$$1 J = 1 N \times 1 m$$

Btu
energy to raise temperature of 1 lbm (slug) of water at 68 degrees F by 1 degree F.

1 Btu = 1.0551 kJ.

1 calorie
amount of energy needed to raise temperature of 1 g of water at 14.5 degress by 1 degree C.

1 cal = 4.16868


Closed system (or control mass)
fixed mass where no mass crosses system boundary

Open system (or control volume)
system is an arbitary colume in space


*first law of thermodynamics*: simple expression of conservation of energy (energy is a thermodynamics property)       

Think of it like energy balance:

Net energy transfer by heat, work and mass = change in all the energies (internal, kinetic, potetial etc.)    

$$E_{in} - E{out} = \Delta E_{system}$$

Now think of it in _rate form_:

$$\dot E_{in} - \dot E{out} = dE_{system}/dt $$

Now think energy is the heat transfer to system (Q) and work done to system (W) is also the same as the sum of the change in internal energy, kinetic energy, potential energy

$$ E = Q + W = \Delta U + \Delta KE + \Delta PE $$

where
$$\Delta U = m(u_2-u_1) $$
$$\Delta KE = \frac{1}{2}m (V_2^2 - V_1^2)$$
$$\Delta PE = mg(z_2-z_1)$$

Total work is boundary work (see below) plus other work
$$W = W_b + W_{other}$$

Now when there is a **constant-pressure process**:

$$W_b + \Delta U + \delta H$$ 


I will explain H when I am not tired tomorrow.

**Boundary work** is work done by the expansion and compression of substances.  On a PV diagram it
is the *area under the process curve*.  Here are a couple of forms of boundary work:

General:
$$W_b = - \int_{1}^{2} P dV $$

Isobaric ($$P_1 = P_2 = P_0 = constant$$) :

$$ W_b = - P_0 (V_2 - V_1)  $$

Polytropic($$PV^n$$):

$$ W_b = - \frac{P_2 V_2 - P_1 V_1}{1-n} $$ , where $$ n \ne 1 $$

Isothernal of ideal gas ($$PV = m R T_0 = constant$$):

$$W_b = P_1 V_1 ln \frac{V_2}{V_1} = mRT_0 ln \frac{V_2}{V_1} $$


# Ideal Gas

Ideal gas law:

$$Pv = RT$$
$$PV = mRT$$
$$du = C_v dT$$
$$dh = C_p dT$$
$$R = C_p - C_v$$

Real Gas:

$$Pv = ZRT$$


$$ \frac{dE}{dt}=  \dot{W} +\dot{Q}+ \dot{M_{in}} (e+pv)_{in} - \dot{M_{out}} (e+pv)_{out} $$



Questions:
$$ du = dh = C_v dT = Cp dT = \bar c dT $$
    
        {}liq = {}f(t)

