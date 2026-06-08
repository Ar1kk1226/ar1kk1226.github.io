---
layout: page
title: Solar-Powered Umbrella
lang: en
date: 2026-06-08
---

This project is aiming to create a solar umbrella experiment which based on the urban heat island effect. 

Let's take a look at how we did it

<!-- excerpt -->

First lookat the poster

![local pic](/images/csp/poster.jpg "poster") 

## Background
 ** Concept: Urban Heat Island Effect ** 
 The phenomenon where urban areas experience highertemperatures than surrounding regions due to heat-absorbingmaterials such as concrete.


 ** Surface Heat absorption **
 - Dark surfaces of the red rock absorb more solar radiation

 - Absorbed radiation is converted into heat

 - This increases surface temperature and warms the surrounding air

 ** Environmental Problem:**

 During summer in Chengdu,strong sunlight and hightemperatures are common.
 In Hongshi Park,many areashave limited shade,which results in prolonged exposure todirect sunlight for visitors.
 This leads to increased heatexposure and causes discomfort for users,reducing theoverall usability of public outdoor spaces.


## Experiment

** Basic Knowledge **
We want to determine under how much surface area of the solar panals could maximize the charging efficiency with the maximum illuminance

So we searched online for the calculation of the relationships between illuminace andcharging power

Iluminance E,(lux,Ix)measures brightness weighted by the human eye's photopic response,peaking at 555nm.Irradiance G(Wm-²)is the true radiant power per unit area relevant to energy conversion.
When varying cloud thickness only scales light intensity without altering spectral composition,the ratio Ev/G is constant K—hence lux and irradiance are directly proportional across all measurements.


** Research Question :**
How does illuminance,modulated by varying cloud-layer thickness,affect themaximum output power of crystalline silicon photovoltaic panels,and to whatextent does this relationship conform to the theoretical linear prediction PmaxαEv?


** Materials: **

1. Solar Panals * 4
2. Type C wires
3. DC watt meter
4. A computer with data collection software --- Logger Pro
5. A phone with software that could collect real-time illuminance
6. Timer


<div style="display: flex; justify-content: space-between; align-items: center;">
  <img src="/images/csp/computer.jpg" alt="computer" style="width: 48%;"/>
  <img src="/images/csp/solarpan.jpg" alt="solar" style="width: 48%;"/>
</div>



** Methodology: **

<div style="display: flex; justify-content: space-between; align-items: center;">
  <img src="/images/csp/diss1.jpg" alt="discussion" style="width: 48%;"/>
  <img src="/images/csp/diss2.jpg" alt="discussion" style="width: 48%;"/>
</div>

<br>
![local pic](/images/csp/diss3.jpg "diss3") 


##  Data Processing

** Raw data **
![local pic](/images/csp/rawdata.png "rawdata") 

** Explanation **

![local pic](/images/csp/4panels.png "4panels") 
![local pic](/images/csp/3panels.png "3panels") 
![local pic](/images/csp/2panels.png "2panels") 

## Evaluation/Conclusion

Based on the graphical analysis,we conclude that ambient illuminance and electrical power output maintain a fundamentally linear relationship,
a hypothesis most strongly validated by the 4-panel configuration's high coefficient of determination(R²)of 0.9509.
Although the R²values decrease for the 3-panel(0.8524)and 2-panel(0.8148)setups—indicating a larger data spread and less definitive correlation as the active area reduces—the overarching linear trend remains consistent.
The calculated percentage uncertainties for the slopes of the 4,3,and 2-panel arrays are 17.49%,21.14%,and 13.89%,respectively.These uncertainties,alongside the presence of high-illuminance outliers,
primarily stem from two specific measurement limitations:the reliance on manual human-eye estimation to average rapidly fluctuating multimeter values,and optical refractions within the smartphone camera lens,which severely distorted the lux readings under intense direct sunlight.



---

[← Back](javascript:history.back()) [🏠 Home](/)