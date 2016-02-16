---
layout: post
title: "Production and Operations Management 101 Reference Sheet"
category: [101 notes, school] 
tags: [engineering, manufacturing, data science, management sciences]
last_updated: 2016-01-16
---

# Learning Curve

Given Y(u) is the number of time units to produce the uth unit, then using $$Y(u) = au^{-b}

Now to describe the % decline in labour hours to produce 2n compared to hours required to produce item 2n compaures to the hours required to produce item n:

$$\frac{Y(2u)}{Y(u)} = \frac{a (2u)^{-b}}{a (u)^{-b}} = 2^{-b}$$

Since 80% is a historically determined learning curve, $$ 2^{-b} = 0.8$$:
$$ b = \frac{-ln 0.8}{ln 2} = 0.322$$

# Timing Capacity Additions

D = annual increase in demand, x = time intervals between capacity additions, r = annual discount rate (compounded continously), f(y) = cost of operating a plant of capacity y.  Now given C(x) is the total discounted cost of all capacity additions over an infinite horizon, if new plants are built even x units of time:

$$ C(x) = \frac{f(xD)}{(1-e^{-rx}}

TODO: Understand the next equations better, before writing them here.

# Inventory Control Under Known Demand

Holding or Carrying cost ($$h = Ic$$) where h is the holding cost, I is the annual interest rate, and c is the $ per unit of inventory.






