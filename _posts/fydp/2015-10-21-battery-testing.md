---
layout: post
title: "Designing a Battery Testing Rig"
tagline: "Safely charge and discharge batteries while measuring temperature and voltage"
category: [FYDP, hardware] 
tags: [FTDP, engineering, hardware, electrical, battery]
last_updated: 2015-10-17
---

# Background
As [previously mentioned](http://mrandrewandrade.com/blog/2015/09/11/fydp-ess.html) my fourth year design project (FYDP) involves building an energy storage system (ESS) using repurposed electric vehicle (EV) batteries.  After individual battery cells are removed from the large high voltage EV battery, the first step the project is testing the battery cells to see if they are "healthy" and ready to use.  This means we have to charge and discharge the cells while monitoring both the voltage and the temperture.  We are planning on using a BeagleBone Black (BBB) as our microcontroller (show below), and have to pick sensors to measure voltage and temperature.

![](http://www.seeedstudio.com/document/pics/beaglebone.png)

# Project Scope

Since we are running lean, our goal is to try and get to stage of safetly changing and discharging the battery autonomously as quickly.  This means for our `minimal viable product` (MVP), we had the following goals:

1. Label every battery cell with a unique identifier, and keep log of all tests and data.
2. Be able to autonomously charge the battery.  This means be able to stop charging when either the battery reaches $$50 \degC$$ or the voltage accross the battery cell exceed $$7.2 V$$.
3. Constantly measure voltage accross the battery over time
4. Constantly measure the temperature of the battery over time
5. Be able to autonomously discharge the battery by pressenting a simple resistive load

These are a couple of stretch goals:
1. Steam data online
2. Test Multiple Cells
3. Coloumb counting

Let's start with choosing the sensors and figuring out how to take measurements.

# Instrumentation and Measurement


## Measuring Voltage

Measuring voltage using a BBB is simple: we can simply use the analog input pins on the BBB to measure voltage.  The first issue is that according the the [BBB documentation](http://beagleboard.org/support/BoneScript/analogRead/), to safetly read analog values, the input voltage to the analog to digital convert (ADC) is limited to 1.8V. This means that the input voltage must be properly limited to ensure the safe operstion.  To achieve this, a simple [voltage divider](https://learn.sparkfun.com/tutorials/voltage-dividers) can be used (by apply Ohm's Law $$V = I R$$).

<iframe title="voltage-divider" width="600" height="600" scrolling="no" frameborder="0" name="voltage-divider" class="eda_tool" src="https://upverter.com/eda/embed/#designId=79ccecb425cbbda4,actionId="></iframe>

Based on Ohm's Law, the circuit above can be simlified to:  

$$ V_{out} = V_{in} * \frac{I R_2}{I(R_1 + R_2)} = \frac{V_{in}R_2}{(R_1+R_2}




Given the spec of reading a voltage range from 0 to 30V to meet the BBB's requirement of $$1.8 V$$, $$R1 = 160K$$ ohm and $$R2 = 10K ohm$$.  The issue is that with a total resistance $$R1 + R2 = 180K ohm$$, then the total current drawn $$I_{total} = {V_total} / R_{total} = 30V / 180000 ohm = 1.66*10^-4 A$$ While this is a smaller current drawn, slowly by slowly 

30V 

## Temperature Sensors

There exist many ty








To prevent the battery from discharging as you measure the voltage, one can use 


{% highlight python %}
import pandas as pd
import numpy as np
from scipy.optimize import curve_fit
import matplotlib.pyplot as plt
#comment below if not using ipython/jupyter notebook
%matplotlib inline 

#read csv and label columns
data = pd.read_csv('100k-thermistor.csv')
data.columns = ['temperature', 'r_max', 'r_norm','r_min']

plt.plot(data.temperature,data.r_norm, label='average resistance')
plt.xlabel("Temperature (Celcius)")
plt.ylabel("Resistance (kohm)")
plt.title("Expected Resistance vs Temperature of 100K Thermistor")

{% endhighlight %}



<matplotlib.text.Text at 0x7f6434b72990>




![png](output_1_1.png)



```python

```


```python
plt.plot(data.temperature,data.r_norm, label='average resistance')
plt.plot(data.temperature,data.r_min, label='min resistance')
plt.plot(data.temperature,data.r_max, label='max resistance')
plt.xlabel("Temperature (Celcius)")
plt.ylabel("Resistance (kohm)")
```




    <matplotlib.text.Text at 0x7f6434d97650>




![png](output_3_1.png)



```python
plt.plot(data.temperature[30:130],data.r_norm[30:130], label='average resistance')
plt.plot(data.temperature[30:130],data.r_min[30:130], label='min resistance')
plt.plot(data.temperature[30:130],data.r_max[30:130], label='max resistance')
plt.xlabel("Temperature (Celcius)")
plt.ylabel("Resistance (kohm)")
```




    <matplotlib.text.Text at 0x7f6434ccda90>




![png](output_4_1.png)



```python
data['lower_error'] = data.r_norm-data.r_min
data['upper_error'] = data.r_max-data.r_norm

asymmetric_error = [data.lower_error[30:130], data.upper_error[30:130]]
plt.errorbar(data.temperature[30:130], data.r_norm[30:130], yerr=asymmetric_error, ecolor='r')
#plt.show()

```




    <Container object of 3 artists>




![png](output_5_1.png)



```python
plt.plot(data.temperature[30:130],data.r_min[30:130]-data.r_norm[30:130], label='lower error')
plt.plot(data.temperature[30:130],data.r_max[30:130]-data.r_norm[30:130], label='upper error')
plt.plot(data.temperature[30:130],data.r_norm[30:130], label='average resistance')

```




    [<matplotlib.lines.Line2D at 0x7f643500df10>]




![png](output_6_1.png)

