---
layout: post
title: "Generalized Solution to Multi-Echelon Inventory Decisions"
category: [technology, tools, manufacturing, supply chain] 
tags: [Technology, Optimization, Non-convex optimization, manufacturing, supply chain, production engineering ]
last_updated: 2016-02-16
---

This post outlines the generalized solution to Multi-Echelon Inventory Decisions by finding the lower, upper and average bound for an optimal solution.  It then outlines a genetic algorithm approach to finding the optimal solution.  The generalized solution procedure is applied to the [Multi-Echelon Inventory 
Decisions at Jefferson 
Plumbing Supplies
To Store or Not to Store?](http://ptgmedia.pearsoncmg.com/images/9780133757880/samplepages/0133757889.pdf) Case Study


Introduction:
=============

Alex, a NASCAR enthusiast, is the Inventory Manager of Jefferson
Plumbing Supplies, and he faces an interesting quandary. He has been
notified by one of his suppliers that there is an upcoming increase to
their minimum order quantity. The following case study summary presents
a description, a system model, and a summary and conclusion for the
problem Alex faces.

Problem:
========

Jefferson Plumbing has know demand of 100 units annually, from loyal
customers, of a specialty faucet that is ordered from a long time
supplier. Alex received a letter from the supplier informing him that
they would be increasing their minimum order quantity. The new minimum
order quantity is triple what would normally be ordered. Due to their
storefront’s city location, inventory holding costs for the faucet are
expensive. Jefferson Plumbing Supplies has a warehouse with a cheaper
annual holding cost, and Alex would like to determine the optimum costs
previous to, and after the policy change.

Options:
--------

1\. convince the company to maintain relations to drop the minimum order
amount

2\. not stock the item -&gt; lost revenue and customers

3\. order and store in the store

4\. order and store in the storage facility (multi-echelon system)

5\. find alternative storage

Given that option 1, 2, and 5 are not feasible there is option 3 (the
base case) and option 4.

Variables
---------

Holding cost h <span>\[</span>\$ unit/time<span>\]</span>\
Stockout Penalty p <span>\[</span>\$/unit/time <span>\]</span>\
Fixed Cost k <span>\[</span>\$/order <span>\]</span>\
Purchase cost c <span>\[</span>\$/ unit <span>\]</span>\
Demand λ <span>\[</span>units/time <span>\]</span>\
Order quantity Q <span>\[</span>units <span>\]</span>\
Optimal order quantity Q\* <span>\[</span>units<span>\]</span>\
Re-order interval u <span>\[</span> time<span>\]</span>\
Average Annual Cost C(Q) <span>\[</span>\$/year<span>\]</span>\
Optimal order quantity C\* =C(Q\*) <span>\[</span>units<span>\]</span>\

Assumptions:
------------

Assumption given in case study:\
1. Continuous deterministic demand of λ = 100 units/year

2\. The cost of not having inventory is very high (lost of profit and
lost of customers and future profit)

3\. Minimum order quantity $$Q_{min} = 130$$ units, previous order quantity
was about 130/3 units 4. No capacity limits 5. Must always have positive
inventory (no backorders) based on assumption 2

Assumptions taken to relax problem:\
1. No lead time

2\. Purchase cost c is ignored in optimization as it remains constant

3\. The holding cost includes the cost of held capital (no interest rate)

Givens:
-------

Purchase Fixed ording cost $$k_p = \$100/order$$

Warehouse ordering cost $$k_w = \$50/order$$

Store holding cost $$h_s = \$10/unit/year$$

Warehouse hoding cost $$h_w =  \$1/unit/year$$



System model:
=============

Base Case: Deterministic Economic Order Quantity Model
------------------------------------------------------

In the base case, the system can be modeled as a simple single order
system where the quantity is stored at the retail store.

Manufacturer -&gt; Retailer

Using a basic economic order quantity (EOQ) model and the assumptions
previously made, the yearly cost of the base case would be:

$$C(Q) = \frac{k_p \lambda}{Q} + \frac{h_s Q}{2}$$

Given the first order condition:

$$\frac{\partial C} {\partial Q}  =  - \frac{k_p \lambda}{Q^2} + \frac{h_s}{2} = 0$$

Given this is a local minimum, the optimal quantity would be:

$$Q^* = \sqrt{\frac{2 k_p \lambda}{h_s}} = 44.72135955 = 45 units$$

With the optimal annual cost would be:

$$C^* =  C(Q^*) = \sqrt{2 \lambda k_p h_s}  \cong \$447.21$$

Since the minimum order quantity $$Q_{min} \ge 130$$ as stated in the
problem and the actual optimal annual cost would be:

$$C(Q_{min}) = \frac{k_p \lambda}{Q_{min}} + \frac{h_s Q_{min}}{2} \cong \$726$$

The annual cost is convex optimum, therefore the smallest minimum order
quantity would be optimal in this model.

Two stage deterministic multi-echelon serial system
---------------------------------------------------

An alternative system model would be two stage: after an order is placed
from the manufacturer it would be stored at a lower cost in the
warehouse and be shipped to the retailer. In shematic form:

Manufacturer -&gt; Warehouse -&gt; Retailer

Each stage functions like an EOQ system and determines the optimal order
quantity and period. Solution will have a zero inventory ordering
(ordering will occur when inventory is zero) assuming no lead time.


Since the minimum order quantity is greater than yearly demand,
therefore there will only be a maximum of 1 order within a year from the
manufacturer. The initial assumption will be made that it is cheaper to
store inventory at the warehouse and order parts when required. This
assumption will be later verified by comparing the total cost to the
base case.

We are going to introduce the reorder interval $$ \textbf{u} = Q /
\lambda $$, and can be thought of as a vector for each stage (j) of the
ordering process. In our case, $$u_w$$ is the ordering period made **at**
the warehouse **from the store** and $$u_p$$ is the ordering period **at
the production factory** from the warehouse.

The averaged annual cost function (to be minimized) of the most ideal
function would be the following:

$$C (\textbf{u}) =  \sum_{j} \left(\frac{k_j}{u_j}+ \frac{h_j \lambda u_j}{2}\right) = \frac{k_w}{u_w}+ \frac{(h_s -h_w)\lambda u_w}{2} + \frac{k_p}{u_p}+ \frac{h_w \lambda u_p}{2}$$

Such that:

$$u_j = \theta_j u_{j+1},$$

$$u_j \ge 0,$$

$$\theta_j  \in \mathbb{Z}^+ =  \{1, 2, 3, ...\}$$

There is also the added constraint due to the minimum quantity order for
$u_p$

$$u_p \ge \frac{Q_{min}}{\lambda} = \frac{13}{10}$$

Solving this optimization problem for the optimum reorder interval
$$\textbf{u*}$$ leads to a non-convex mixed integer non-linear
programming. Since the constrained solution is non-convex, it does not
have a guaranteed optimal solution except in limit. For this reason, a
generalized approach to finding the lower, upper and mean average annual
cost must be used.





Generalized Solution:
---------------------

The generalized solution to an non-convex, mixed interger non-linear
programming optimization problem is to get an upper bound by solving a
relaxed problem (non-interger constraint) which represents the worst
cast scenario.

The relaxed optimization problem is the following:

$$C (\textbf{u}) =  \sum_{j} \left(\frac{k_j}{u_j}+ \frac{h_j \lambda u_j}{2}\right) = \frac{k_w}{u_w}+ \frac{h_s \lambda u_w}{2} + \frac{k_p}{u_p}+ \frac{h_w \lambda u_p}{2}$$

Such that:

$$u_j \ge u_{j+1}$$ $$u_j \ge 0$$
$$u_p \ge \frac{Q_{min}}{\lambda} = \frac{13}{10}$$

This can be solved using multi-variate calculus or [numerically]

Using calculus, the partial derivative of the cost function with respect
to $$u_p$$ can be taken as:

$$\frac{\partial}{\partial u_p}(\frac{k_w}{u_w}+ \frac{h_s \lambda u_w}{2} + \frac{k_p}{u_p}+\frac{h_w \lambda u_p}{2})= \frac{\lambda  h_w}{2}- \frac{k_p}{u_p^2}$$

Now solving for $u_p$

$$u_p^*  = ±\frac{\sqrt{\frac{2k_p}{h_w}} }{\sqrt{\lambda}} = \sqrt{2} \ge \frac{13}{10}$$

Similarly, the partial derivative of the cost function with respect to
$$u_w$$ can be taken as:

$$\frac{\partial}{\partial u_w}(\frac{k_w}{u_w}+ \frac{h_s \lambda u_w}{2} + \frac{k_p}{u_p}+ \frac{h_w \lambda u_p}{2})= \frac{h_s \lambda}{2}-\frac{k_w}{u_w^2}$$

Now solving for $u_w$

$$u_w^* = ±  \frac{\sqrt{2 k_w}}{\sqrt{h_s \lambda}} = \frac{\sqrt{10}}{10}$$

The upper bound of the overall cost function can now be calculated as:

$$C_* = C(\textbf{u*}) \ge 100(\sqrt{2} + \sqrt{10}) \cong 457.649122254$$

In this case, about every 1.414 years the warehouse would order:

$$Q_p^* = u_p \lambda = 100 \sqrt{2} \cong 141.421 = 142 units$$

The retail store would order:

$$Q_w^* = u_w \lambda = 100 \sqrt{10} \cong 31.522 =  32 units$$

This would result in the overall cost to be:

$$C(\textbf{Q}) = \frac{129979}{284} \cong \$457.67$$

Using the same approach using the un-relaxed cost function (and assuming
incorrectly an optimal solution), the optimal order quantities becomes:

$$Q_p^* = u_p \lambda = 100 \sqrt{2} \cong 141.421 = 142 units$$

The retail store would order:

$$Q_w^* = u_w \lambda = 100/3 \cong  33.33 =  34 units$$

This results in the following approximate ideal average annual cost
$$C(\textbf{Q})_{ideal} \cong $$ [\$441.81](http://www.wolframalpha.com/input/?i=%2850%29%2F%28x%29+%2B+%289+*+100+*+x%29%2F%282%29+%2B+%28100%29%2F%28y%29%2B+%281+*+100+*+y%29%2F%282%29%2C+x+%3D+0.34%2C+y+%3D+1.42) This lower bound would be
better estimated by evaluating the cost of storing the remaining
inventory in the warehouse. For example, after the first order cycle of
142 parts from the supplier and first three shipments to the store,
there will be 14 parts remaining. At a cost of \$1 per year per item,
this also adds a \$14 cost over the three cycles. In the next cycle
(order the minimum quantity of 130 units), there will be 16 left over.
This continues by units of 2 (over 30 cycles) until 30 units and then
finally there will be no remain parts and the cycle starts again. This
means over 30 order cycles from the store to the warehouse, we would
face a mean unit period cost of 198 units \* \$1 /30 or \$6.6 per order
cycle. This means the actual lower bound of the solution is around
448.41. The difference between the upper and ideal lower bound of the
solution is around \$16.19 or the price of a beer and a Speedway Big Hog
Chedder Dog at a Nascar event and the approximate average annual cost
would sit closer to \$448.41. Since the optimal order quantity from the
warehouse is $$Q_w* = 34$$ units,
$$\theta_{theoretical}^* = Q_w^* / Q_p^* \cong 4.176470588 $$ and
$$\theta_{actual}^* = 4$$. Since the difference between
$$\theta_{theoretical}^*$$ and $$\theta_{actual}^*$$ is small, the actual
solution would be much closer to the lower bound.

Constrained Optimization Solution
======================

To improve upon the generalized approach and attempt to find the true
optimal solution, the optimization problem can be solved using a
non-linear programming tool such as Goal Seek in Excel, as demonstrated in this [spreadsheet](http://mrandrewandrade.com/blog/images/case-study.xls). Alternatively,
the lower bound of the optimal solution can be estimated [numerically](http://www.wolframalpha.com/input/?i=minimize+%2850%29%2F%28x%29+%2B+%2810+*+100+*+x%29%2F%282%29+%2B+%28100%29%2F%28y%29%2B+%281+*+100+*+y%29%2F%282%29+such+that+x%3E+0+%2C+y+%3E+13%2F10)

or using calculus. Then $\theta_j$ can be calculated and rounded to find
the order quantities (as shown in the generalized solution).

The results from both methods are in agreement and the result in
$Q_w^* = 34$, $Q_p^*= 136$ and an overall average annual cost of about
\$441.59 which is \$5.62 dollars cheaper than before the policy change.

Summary and Conclusion {#summary}
======================

Optimum Cost before policy change
---------------------------------

The optimum annual cost before the policy change in the problem is
\$447.21/year

Optimum Cost Ordering and Storing to Retail Store Alone
-------------------------------------------------------

Given the assumptions in this problem, using the optimum solution of a
basic EOQ model results in an optimum ordering 130 units (when stock
reaches zero), results in an actual optimal annual cost of around \$726

This means that this would cost the store about \$277.79 more if they
choose to order, ship and store to the retail store.

Optimum Cost Using a Warehouse
------------------------------

Given the assumptions in this problem, the approximate optimum solution
of the two stage deterministic multi-echelon serial system provides an
annual cost of around \$447.21. This means that the policy change would
cost the store at most about \$5.61 less if they order 144 parts to the
warehouse and 136 parts from the warehouse to the retail store. Alex
Halek wwould be able to rest at ease and possibly use those savings
towards the purchase of a delicious Speedway Big Hog Cheddar Dog at next
year’s Spring Cup.




