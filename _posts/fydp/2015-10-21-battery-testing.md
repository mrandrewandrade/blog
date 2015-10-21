---
layout: post
title: "Battery Testing Setup for Fourth Year Design Project"
tagline: "Build a test rig to charge and discharge batteries while measuring temperature and voltage"
description: "Growing and Scaling high performance teams"
category: [FYDP, hardware] 
tags: [FTDP, engineering, hardware, electrical]
last_updated: 2015-10-17
---

As part of my fourth year design project (FYDP), we are building an energy storage system (ESS) using repurposed electric vehicle (EV) batteries.  After individual battery cells are removed from the large high voltage EV battery, the first step the project is testing the battery cells to see if they are "healthy" and ready to use.  This means we have to charge and discharge the cells while monitoring both the voltage and the temperture.  We are planning on using a BeagleBone Black (BBB) as our microcontroller, and had to pick sensors to measure voltage and temperature.

Measuring voltage is simple: we can simply use the analog input pins on the BBB to measure voltage.  The first issue is that the input voltage is limited to 1.8V.  To overcome this issue a simple [voltage divider](https://learn.sparkfun.com/tutorials/voltage-dividers) can be used (by apply Ohm's Law).

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

