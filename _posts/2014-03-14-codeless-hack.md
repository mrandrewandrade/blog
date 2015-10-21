---
layout: post
title: "How I won $5000 at a Facebook hackathon without a single line of code"
tagline: "OCP Hackathon Winner: The Codeless Hack"
description: "OCP Hackathon Winner: The Codeless Hack"
category: [hardware] 
tags: [arduino, battery, open compute, hardware, Facebook, opencompte.org, openhardware]
last_updated: 2015-21-11
---

_This a cross post from the_ [_Open Compute Project_](http://www.opencompute.org/) [_official blog_](http://www.opencompute.org/blog/ocp-hackathon-winner-the-codeless-hack/)      

_Our second blog post about the OCP Summit's hardware hackathon comes from Derek Jouppi_and_ [_Andrew Andrade_](http://ca.linkedin.com/pub/andrew-andrade/3b/a9b/6b9) _who are interns at Facebook and won the OCP Summit Hackathon with a new design for the [Open Rack](http://www.opencompute.org/wiki/Open_Rack) V2's Battery Backup Unit._    

Derek and I decided to take part in the hardware hackathon at the Open Compute Summit on a whim. We'd heard about the hackathon and were intrigued enough to stop by, but didn't plan on joining in. Once we were there, however, we realized that the opportunity was too much to pass up, and we jumped in without the team size and equipment that many other groups had.     

What we did have was an idea. We wanted to build something that was highly impactful, that could be contributed immediately to Open Compute, and that we hoped would be a shippable prototype within 24 hours. Given our criteria, we decided we wanted to do a hack for the newly released Battery Backup Unit (BBU) on the Open Rack V2 design, since this is the area that Derek was most familiar with.     

The problem with the BBU is that if it is not functional, debugging a failed unit is extremely difficult and time consuming. You have to use a nest of wires, probes, DMM, and/or oscilloscope to find the solution – and it's definitely not a great solution. Instead, we envisioned a coupler that would take in the output from the scope, process the signals and intelligently display what the error was. Using a simple ATMEGA microcontroller, and LED display and a few other components, we could make a compact and intelligent tool for technicians working in data centers. It was simple enough we could design and build a working prototype in only 24 hours, and yet it had high impact as it could directly contribute to running a better data center. It seemed like a perfect project for our two-man team.      

Thanks to one of the hackathon's organizers, John Kenevey, we were able to run back to Menlo Park to grab the supplies we needed: two Arduinos, bread breadboards, LED's, wires, DMM, and an assortment of other parts we thought might be useful.      

![](preparing-to-win-hackathon.png)  
**Derek Jouppi and I begin to assemble the equipment we need for our hack.**   

Then we got to work. Since the display BBU's were inaccessible, I quickly began to write Arduino code to simulate a failing BBU. I also wrote some code that acted as a DAC to take in the signals from the BBU. Meanwhile, Derek got to work doing a pin out drawing and sketching the initial schematic. We worked for a few hours before bringing our design to an Open Rack prototype to investigate how we could implement it. That's when we realized our solution was all wrong.    

Our monitoring system that sat on all the racks didn't make sense. There was not enough room in the V2 rack to hold a coupler, and a microcontroller solution would be too expensive and not scalable in the large data center.

With only a few hours left in the hackathon, we decided we needed to pivot to simplicity. We'd been working furiously to design a complex solution, when what we really needed was to take the Open Compute approach: remove anything in the data center that didn't contribute to efficiency. In this case, we decided we wanted to create a simple, minimal device to solve the problem of bringing visibility to failing BBU's.    

We realized that, given the mapping of the pin outs, one solution would be to connect the signals to the status LED's, which would give instant visualization to the problems with the BBU. While it would take manual diagnostics to determine issues, the cost of the device would be significantly lower, and it would be much easier to operate. For added functionality we included an output header. This could be used in the future to connect to a microcontroller if a more automated method had to be deployed. Finally, since the BBU relied on a power supply to charge, we included a power header that could be used to connect to the power supply.    


**The debug card that resulted from our hack could easily attach as a component to the back of a Battery Backup Unit as shown is this rendering and** [**video**](https://www.facebook.com/photo.php?v=10153813042370623&set=vb.520255622&type=3&theater) **.**   

Our hack had become a codeless debug tool that would enable techs to quickly and efficiently debug issues with battery back up units in their datacenters.

After drafting out a quick design on paper, we quickly iterated our design on breadboards attempting to gain the designed functionality. We borrowed an actual failing BBU from the demo and after some iteration, we were able to come up with a very simple, "bare bones" design for the debug card.



**Schematic of the debug card we made using Upverter's schematic layout tool.**

For our circuit layout we used Upverter, a start-up that focuses on online board design CAD software. We drew up a quick schematic by sourcing our components online and imported their drawings on Upverter's schematic tool. We then used the tool to create a bill of materials that included the component prices and the cost to spin the board.

We then created a PCB layout for the board. To parallelize our efforts, we performed a quick mock-up on MS Paint of the layout of the board. Derek finished up the PCB layout on Upverter while I did a quick rending of our final product using mechanical CAD software.

When we demonstrated our project for the judges, we were proud to watch as the BBU powered up and our LED's lit up a split second later, indicating the status of the unit. Our simple solution had made it easy and inexpensive to know if the BBU was functional at any given time. This vital information will make it easier to be sure that any power loss won't result in a loss of functionality.


We were incredibly excited by what we'd built, and we couldn't help but note the community spirit of Open Compute that had gotten us there. Throughout the hack, we frequently traded tools with other teams and asked other participants for their input as we worked. Everyone lived and breathed the open source philosophy – that sharing knowledge and experience will result in better hacks overall. It seems to us that this desire to collaborate is what Open Compute is all about, and in that vein, we plan to release the specifications for our BBU hack to the open source community in the next few weeks.

