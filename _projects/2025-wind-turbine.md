---
layout: project
title: Design and Testing of a Small-Scale Horizontal Axis Wind Turbine
technologies: [MATLAB, Fusion 360, LabView]
# image: /assets/images/wind_turbine.png
---
PROJECT OVERVIEW

Our objective was to design a small-scale horizontal-axis wind turbine that extracts maximum power from oncoming wind, while conforming to several constraints related to geometry, material, and operating conditions. 

DESIGN PROCCESS

To do this, we chose some design parameters based on literature research and basic hand calculations. Then, we wrote several MATLAB scripts to model the wind turbine using Blade-Element Momentum theory (BEM). The model splits up each blade into descretized segments, calculates wind conditions, forces, and stresses, and integrates along the blade to calculate freespin RPM, max stress, and maximum power output.

![General Design Process]({{ "assets/images/design_flowchart.png" | relative_url }})

TESTING SUMMARY

Our testing began by assembling the turbine (attaching blades, mounting the hub, reinstalling the nose cone) and confirming LabView was correctly set up, with pressure transducer calibrated and with successful data collection verified. In total, five wind speeds were tested: 4.1 m/s, 4.8 m/s, 4.9 m/s, 5.3 m/s, and 5.8 m/s. For each wind speed, we collected the RPM, torque, and power at different torque brake voltages to create various power curves. We were especially careful not to exceed the max rated torque brake voltage or the max RPM the torque brake could take.

<p style="text-align:center;">
  <img src="{{ 'assets/images/final_design.png' | relative_url }}" 
       alt="Final Blade Design" 
       style="width:100%; height:auto;">
</p>

The data follows expected trends; a higher wind speed results in more power extraction and higher RPMs. Between 2100-2400 RPM the data flattens out, likely due to the blade’s rotation rate leading to the blade experiencing its resonant frequency, slowing it down. This is found in all power curves that spin at this range, indicating it is experiencing resonance. Further comparing the model predictions to the experimental results, the model consistently overpredicted the max power extracted. This is likely due to the assumptions built into the model that ignore tip effect, which neglects additional drag and friction forces on the blades that slowed them down.

<p style="text-align:center;">
  <img src="{{ 'assets/images/power_curves.png' | relative_url }}" 
       alt="Collected Power Curves" 
       style="width:100%; height:auto;">
</p>

Overall, our blade design was effective at extracting power in a wind tunnel, achieving a maximum measured output of 1.8W. This result demonstrates that our blade design methodology, which optimizes lift-to-drag ratio, taper, and twist, was effective at producing a functional turbine blade. However, the model inaccurately predicted optimal operating RPM and maximum power output. The model underpredicted operating RPM, selecting a design RPM of 1050 RPM compared to an experimentally determined optimum of 1770 RPM, and overpredicted maximum power, estimating 6.5 W versus the measured 1.8 W at a wind speed of 5.8 m/s. Future work should focus on improving model fidelity to better align predicted and experimental performance. Key improvements include more accurate calculation of axial and tangential induction factors, incorporation of losses from tip effects, and accounting for frictional losses and stress concentrations at the hub connection. 

PERSONAL CONTRIBUTIONS
I helped out a lot with MATLAB modelling, but with special focus on working with the provided Weibull distribution of wind velocities to obtain a target wind speed that would extract maximum average power. I also worked on integrating this probability distribution with our results to calculate a predicted average power over the entire distribution based on our four data points. I additionally helped out with all writeups and our final presentation and report.

