---
layout: post
title: "Thermodynamics 101 Reference Sheet"
tagline: "Thermo is easy if you understand the basics"
category: [101 notes, school] 
tags: [engineering, thermodynamics, thermal, science]
last_updated: 2015-10-25
---
Note: I only got to the state postulate and have notes for the rest.  Still a work in progress.

# assumptions and common terms

## Assumptions
First lets start with some common assumptions (refer back here when they come up):

1. Kinetic and potential energy remains about constant ($$\Delta KE, \Delta PE ~= 0$$)
2. Isobaric (pressure is constant)
3. Isothermal (temperature is constant)
4. Isovolumetic (total volume (V) is constant)
5. Rigid (change in volume is zero or $$dV = 0$$)
6. Adiabatic (heat transfer is zero or $$\dot Q = 0$$
7. Reversible ($$\dot P_s = 0$$)
8. Ideal Gas more below
9. stead-state or SS (change is zero or d/dt = 0)
10. steady flow or SD ($$ U_{IN}, h_{IN},$$ ... = constant)
11. Liquids and solids have constant volume
12. Liquids are solids are assumed incompressible

## Common terms

**compressed liquid** or **subcooled liquid**: fluid in liquid phase and not about to vaporize.

**saturated liquid**: liquid about to vaporize

**saturated vapour**: vapor about to condense

**saturated (liquid-vapor) mixture:** liquid and vapor phases co-existing in equilibrium.

**super heated vapor**: vapor not about to condense

**saturation temperature**: temperature at which a pure substance changes phase

**saturation pressure**: pressure at which a pure substance change phase

**critical point**: point where thje saturated liquid and saturated vapour states are the same



# Laws

**zero law of thermodynamics:**
if two seperate bodies are in thermo equilibrium with a third, they the first two are in equilibrium. (think of the third body as a thermometer and the first two as non conected bodies)

**first law of thermodynamics:**  
chance in energy of system = energy into system - energy out of system + energy produced by system

**concervation of mass:**
change in mass of system =  mass into system - mass out of system + mass produced by system.

Note: both the mass produced and energy produced by system is usually equal to zero.


**second law of thermodynamics:**
energy has _quality_ in addition to having a _quantity_ (more about that later)

# properties 

**primary/fundamental properties:**
basic dimentions which describe the universe as we know it (length, mass, time, temperature, electic current, amount of light, amount of matter)

**secondary properties:**
properties derived from the fundamental properties (ie velocity = displacement/time)

### Mass

I am not going to go into what mass is.  It relates to gravitational attraction and
$$E = m c^2$$

Its measured in grams in the SI system.

**Note:** unity conversion ratio
There is a difference between lbm pound mass (slug) and pound force lbf in the imperial system

pound mass or slug is the mass which accelerates by 1 ft/s when the force of one pound is exerted on it    

$$ 1 lbf = 32.174 lbm * ft/s^2$$

### Force
Force (F) is mass times acceleration or pressure times area, measured in newtons.

$$ F = P A = m g $$

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

## types of properties

**intensive property** independant of mass/volume (temperature, pressure, density)

**extensive propety** property dependant on size of system (mass, volume)

**specific property** extensive property per unit mass (just divide by mass)

**volume** I am using the following symbol for volume:  

$$\vee$$


**density**  mass per unit volume

$$ \rho = \frac {m}{ \vee }$$

**weight is a force**
$$ W = mg $$ (Newtons)

Where m is mass, and g is the acceleration due to gravity

**specific weight** is density times acceleration due to gravity
$$ \gamma = \rho g $$


**specific volume** is volume per unit mass

$$ \nu = \frac{\vee}{m} = \frac{1}{\rho}$$

specific gravity or relative density is the ratio of the density of a substance to the density of some standard substance at a specified temperature (ususally water at 4 degress C where the density is 1000 kh/m^3)

$$SG = \frac{\rho}{\rho_{H_2 O}}$$

## State Postulate

Okay now we now that we can use properties to descripte the state of a system  The thing is we don't need to specify *all* the properties to fix a state.  This means if we define a sufficient number of properties, then we can determine the rest. As a different example if we know the distance and time someone traveled, we can determine their average velocity.  In the same way if we have two *independant* properties, then we can fix the state if all the other properties are functions of those two properties.  Being **independant** means that if one property is fixed, the other is still able to be varied. For exmaple, if we fix the x and y axis by telling someone they are not allowed to step forwards,backwards or sideways, the z axis is independant so the person can, in theory, still jump.  Now let us call this a fancy idea the **state postulate**.  The state postulate dictates how many number of properties is necessary to fix a state.

>The state postulate says that the state of a simple compresssible system is completly specific by two independant, intensive properties.

We define a a simple compressible system as on where there isn't any other external effect acting on it.  This means there isn't any electrical, magnetic, gravitational, motion or surface tension effects (or those are so small they are assumed to be neglitable since they require external force to make).  Now if we add an signiticant effect on our system, we now need to add an additional property (for every unique type of effect).  For example if we want to consider gravational effect, we must consider z (for height/elevation).  Since temperature and specific volume are always independant, we can always use them to fix the state of a simple compressible system.  If we fix the volume of a system, it can always change temperature.  Same if we fix temperature, we can change the volume.  Why not pressure and temperature? This is because pressures changes with temperature. For example at sea (P = 1 atm) level water boild at 100 degrees C but on a mountain water can boil at a lower temperature.

# Processes, Paths and cycles

A **process** is then a system goes from one equilibrium state to another.  The exacty series of states which a system passes through is called the **path.**  


## Understanding assumptions

Now here is where those assumptions come in.  When someone says a process is isothermal, it means the path which the system takes stays a fixed temperature.  That is the temperature remains constant.  Isobaric means pressure remains constant etc. etc.  The systems follows a path based on the assumption

## Cycle

A system goes through a **cycle** if it returns to its initial state, that is the start and the end states are the same.

## Steady and Uniform

Steady means no change with time, uniform means no change with location.  You can use these terms in everyday life but if a Waterloo engineering student says he/she has a steady boyfriend/girlfriend they are probably lying.

A steady-flow process is when a fluid flows through a control volume steadily.  This means they can change with position,  but not with time.  Mass flowing at 1pm should be the same as mass flowing at 3 pm.  This means the energy contents of a control volume stays constant.

# Zeroth law of thermodynamics

Now its time for a law: if two bodies are in thermal equilibrium with a third, it means they are thermal equilibrium with each other (even if they are not in contact).  It means temperature measured at one point will be the exact same if the value measured is the same at another.  This is why thermometers work.

# Energy

We set the total energy (E) to a convenient a reference point (usually 0) since we are usually only interested in the change of energy in our system.  We denote e as energy per unit mass.

$$ e= \frac{E}{m} $$

## internal energy

Internal energy is the sum of all microscopic forms of energy (related to molecular structure and activity), and is denoted using the symbol U

## kinetic energy

$$ KE = m \frac {\vee^2}{2} $$

$$ ke = \frac{\vee^2}{2}

## Potential energy

$$ PE = mgz $$

$$ pe = gz $$

## mass and energy flow rate

Mass is a form of energy.

**Mass flow rate** amount of mass flowing through a cross section per unit time and can be related to the *volume flow rate*:

$$ \dot{m} = \rho \dot{\vee} = \rho A_c V_{avg}$$

where $$\dot{m}$$ is mass flow rate, $$\dot{\vee}$$ is volume flow rate, and $$A_c$$ is cross sectional area of the flow, and $$V_{avg}$$ is the average flow velocity (perpendicular to Ac)

Now we can relate that to energy using:
$$ \dot{E} = \dot{m} e $$

## mechanical energy (flow energy)
The mechanical energy of a flowing fluid or flow energy per unit mass is the following:

$$e_{mech} = \frac{P}{\rho} + \frac{V^2}{2} + gz$$

We can express it in rate form as:

$$ \dot{E}_{mech} = \dot{m} e_{mech} = \dot{m} (\frac{P}{\rho} + \frac{V^2}{2} + gz)$$

If the fluid assumed to be incompressible (density is constant) flow becomes

$$ \Delta e_{mech} = \frac{P_2 - P_1}{\rho} + \frac{V_2^2-V_1^2}{2} + g(z_2-z_1)$$

and

$$ \Delta \dot{E}_{mech} = \dot{m} e_{mech} = \dot{m} (\frac{P_2-P_1}{\rho} + \frac{V_2^2-V_1^2}{2} + g(z_2-z_1)$$

# Closed vs open systems

Closed system (or control mass)
fixed mass where no mass crosses system boundary

Open system (or control volume)
system is an arbitary colume in space



# Heat

Heat is a form of energy which is transferred between two systems through a temperatuer difference. Heat transfer is denoted by Q, and can be related per unit mass as q.

$$q = \frac{Q}{m} $$

It crosses the boundary of a closed system.  We assume (for simplicity) that heat always goes into the system.  Since it is a directional quantity, if the heat transfer calculated is negative, then it is going out of the system.


# Work

Work as also cross the boundary of a closed system, and since only heat and work can cross the boundary of a closed system, any form of energy crossing the boundary which is not heat, is work.  Same deal: (for simplicity) work always goes into the system.


**work** form of energy defined as force multiplied by distance.

$$ W =  \int \overrightarrow{F} \dot{}  \overrightarrow{dx} = - \int PAdx = - \int P d\vee $$


Where F is force and x is a displacement vector, P is pressure, A is area.  (note Area multiplied by displacement is a volume)


SI unit is joules, english system is Btu (British thermal unit)

Think of a Joule as a newton- meter

$$1 J = 1 N \times 1 m$$

Btu
energy to raise temperature of 1 lbm (slug) of water at 68 degrees F by 1 degree F.

1 Btu = 1.0551 kJ.

1 calorie
amount of energy needed to raise temperature of 1 g of water at 14.5 degress by 1 degree C.

1 cal = 4.16868 J

Work per unit mass is denoted by w and is expressed by:

$$ w = \frac{W}{m}$$


Total work is boundary work (see below) plus other work
$$W = W_b + W_{other}$$

**Boundary work** is work done by the expansion and compression of substances.  On a PV diagram it
is the *area under the process curve*.  Here are a couple of forms of boundary work:

General:
$$W_b = - \int_{1}^{2} P dV $$

$$\delta W_b = F dx = PA dx = P d\vee$$

Where dx is teh change in distance.



Isobaric ($$P_1 = P_2 = P_0 = constant$$) :

$$ W_b = - P_0 (V_2 - V_1)  $$

Polytropic($$PV^n$$):

$$ W_b = - \frac{P_2 V_2 - P_1 V_1}{1-n} $$ , where $$ n \ne 1 $$

Isothernal of ideal gas ($$PV = m R T_0 = constant$$):

$$W_b = P_1 V_1 ln \frac{V_2}{V_1} = mRT_0 ln \frac{V_2}{V_1} $$



## Power

power is just work done per unit time and is denoted by:

$$ \dot{W}$$


## Important things about work and heat transfer:

Work and heat transfer is actaully path dependant and their magnitudes depend on the path followed during a process.  If you don't understand this, try and read chapter three of the Cengel textbook, I can't really explain how I understand this (or if I really do). I would suggest to read the path dependance dependance section for thermodynamic [work](https://en.wikipedia.org/wiki/Work_(thermodynamics))or [nonholonomic systems](https://en.wikipedia.org/wiki/Nonholonomic_system) on Wikipedia, but it is pretty complex and poorly explained there :(.


Ok now so path functions have inexact differentials while point functions (such as properies as volume) have exact differentials.  This means that they depend on the state only and now how a system reached that state.  We use a different symbol for exact and inexact differentals.

$$ \int_{1}^{2} d \vee = \vee_2 - \vee_1 = \Delta V$$

$$\int_{1}^{2}  \delta W = W_{1 \rightarrow 2}$$

Note result of the work integral is not $$\Delta W$$ or W2-W1.  This is because work is done by following a process path and is not just measuring a magnitude.  

$$ E_2 - E_1 = W_{1 \rightarrow 2} + Q_{1 \rightarrow 2} $$

$$ dE = \delta W + \delta Q $$


There equations with determine work of various types (electrical, shaft, spring and many more). You can look them up if you need to use them.


## First law of thermodynamics

*first law of thermodynamics*: simple expression of conservation of energy (energy is a thermodynamics property)       

Think of it like energy balance:

Net energy transfer by heat, work and mass = change in all the energies (internal, kinetic, potetial etc.)    

$$E_{in} - E{out} = \Delta E_{system}$$

Now think of it in _rate form_:

$$\dot E_{in} - \dot E{out} = dE_{system}/dt $$

Now think energy is the heat transfer to system (Q) and work done to system (W) is also the same as the sum of the change in internal energy, kinetic energy, potential energy

$$ E = Q + W = \Delta U + \Delta KE + \Delta PE $$

where
$$\Delta U = m(u_2-u_1) $$,
$$\Delta KE = \frac{1}{2}m (V_2^2 - V_1^2)$$,
$$\Delta PE = mg(z_2-z_1)$$,


Now when there is a *constant-pressure process*: 

$$W_b + \Delta U + \delta H$$      
therefore:  

$$ Q -W_{other} = \Delta H + \Delta KE + \Delta PE $$     


### Mechanisms of Energy Transfer

1. Heat Transfer Q
2. Work Transfer W
3. Mass flow m (when mass leaves or enters a system it brings or takes energy with it.  Imagine removing hot water from a water heater and replacing it with cold water).

### Energy conversion efficiencies

Efficiency describes how well an energy conversion or transfer process is accomplided

$$Performance = \frac{designed output}{required input}$$

Look up the equation for the specific type of efficiency you are asked when you need it.


# Introducing Enthalpy and Entropy

Enthalpy (h) and entropy (s) are also properties of systems.  Don't worry about entropy until we reach the second law for thermodynamics, just know it exists.

Enthalpy is a property defined for simplicity and convenience. This means we can use use it often enough to give it a special name and defination:

$$h = u + P \nu $$

$$H = U + P \vee $$

where U is internal energy and u is internal energy per unit mass.  The book doesn't explain U or H yet, it just says that they exist and they can be used.

For example, if you look at table A-4 or A-5 of the Cengel book, you can find $$h_{fg} which is the difference of enthalpy of the saturated liquid and the saturated vapor.  This represents the amount of energy needed to vaporize a unit mass of a saturated liquid at a given temperature or pressure


# Quality

**Quality** x is the ratio of the mass of vapor to the total mass of the mixture:

$$x = \frac{m_{vapor}}{m_{total}}$$

where$$m_{total} = mass_{liquid} + mass_{vapor} = m_f + m_g$$

Therefore a saturated liquid has quality = 0 and a saturated vapor has quality = 1.

If a system consists of a satured mixture (defined at the very top of this page), we can get the average property by using the quality.  Note: properties are independant depending on phase. For example liquid water will have the properties of liquid water, and gaseous water (steam) will have the properties of gasous water even if in the same system.

$$\nu_{avg} = \nu_f + x \dot{} (\nu_{g} - \nu_{f})$$

we can also rearrange and solve for x

$$ x = \frac{\nu_{avg} - \nu_{f}}{\nu_{g} - \nu_{f}}$$


In the same way we can define this analysis for internal energy (u), enthalpy (h) and enthropy (s) or any general property (y)

$$u_{avg} = u_f + x \dot{} (u_{g} - u_{f})$$

$$h_{avg} = h_f + x \dot{} (h_{g} - h_{f})$$

$$s_{avg} = s_f + x \dot{} (s_{g} - s_{f})$$

$$y_{avg} = y_f + x \dot{} (y_{g} - y_{f})$$


Note, the average properties of the mixture will always be betwen the values for a saturated liquid and satured vapor:

$$y_f \leq y_{avg} \leq y_g$$





# Ideal Gas

Ideal gas equation of state:

$$P \nu  = RT$$

The other (non specific) form is:

$$P \vee = mRT$$

where R is the gas constant.  R is different for each gas as is determined by:

$$R = \frac{R_{universal}}{M}$$

Where Runiversal is the universal gas constant and M is the molar mass. 

Molar mass M is the mass of one mole.  The mass of a system is equal to its molar mass M and the total number of moles N:
$$ m = MN $$

# Specific Heats



**Specific heat** is the energy required to raise the temperature of a unit mass of a substance by one degree.  

We are interested in two types of specific heat: constant pressure $$c_p$$ and constant volume $$c_{\nu}$$.

$$c_{\nu}$$ is the energy required to raise the temperature of a unit mass of a substance by one degree when *volume is constant*.  The book says to think of it as the change in internal energy divided by the change in temperature. 

$$C_{\nu} = \frac {\partial u} {\partial T}$$    
or  
$$u_2 - u_1 = c_{\nu} (T_2-T_1)$$ (kJ/kg)


This is because the change in internal energy for an ideal gas using a process is determined by the following integral:

$$\Delta u = u_2 - u_1 = \int_{1}^{2}  C_{\nu} (T) dT $$ (kJ/kg)

Cp is energy required to raise the temperature of a unit mass of a substance by one degree when *pressure is constant*.  The books says to think of it as the change in enthalpy divided by the change in termperature.

$$C_{p} = \frac {\partial h} {\partial T}$$

$$h_2 - h_1 = c_{p} (T_2-T_1)$$ (kJ/kg)      


This is because the change in enthalpy for an ideal gas using a process is determined by the following integral:

$$\Delta h = h_2 - h_1 = \int_{1}^{2}  C_{p} (T) dT $$ (kJ/kg)

Specific heat at constant pressure is always greater than at constant volume since at constant pressuer the system is allowed to expand and energy during the expansion creates work into the system.

We can also relate the gas constant R to specific heat.
$$R = C_p - C_{\nu}$$

We can also relate Cp and Cv through a property called the **specific heat ratio** (k)

$$ k = \frac{c_p}{c_{\nu}}



I will explain this better below (after real gas and boundary work).


## Real Gas:

Near the saturated region and critial point, gasses can behave unideally, so we use Z to denote a compressibility factor:

$$P \nu = ZRT$$

More on this soon to come!


$$ \frac{dE}{dt}=  \dot{W} +\dot{Q}+ \dot{M_{in}} (e+pv)_{in} - \dot{M_{out}} (e+pv)_{out} $$


# U, S, H of Solids and Liquids

We usually assume that solids and liquids have a constant specific volume, and we called this an incompressible substance.  In this case, the specifics will be the same and just noted as c
$$c_{\nu} = c_p = c $$    

Now we can do some derivations and show that if we know c value at an average temperature, we can determine the approximate internal energy. That is:

$$\Delta u \cong c_{avg} (T_2 - T_1) $$


$$\Delta h = \Delta u + \nu \Delta P \cong c_{avg} \Delta T + \nu \Delta P $$ (kJ/kg)

We can also show that since solids are incompressible, the liquid properties remain that same at difference temperature.

$$ du = dh = C_v dT = C_p dT = \bar c dT $$
  
That is:
$$\Big\{u, v, h, s \Big\}_{liq} \cong \Big\{u(T), v(T), h(T), s(T) \Big\}_{T}$$


