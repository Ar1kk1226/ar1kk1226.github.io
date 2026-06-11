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

## 1 Concept
 **Concept: Urban Heat Island Effect** 
 The phenomenon where urban areas experience highertemperatures than surrounding regions due to heat-absorbingmaterials such as concrete.


 **Surface Heat absorption**
 - Dark surfaces of the red rock absorb more solar radiation

 - Absorbed radiation is converted into heat

 - This increases surface temperature and warms the surrounding air

 **Environmental Problem**

 During summer in Chengdu,strong sunlight and hightemperatures are common.
 In Hongshi Park,many areashave limited shade,which results in prolonged exposure todirect sunlight for visitors.
 This leads to increased heatexposure and causes discomfort for users,reducing theoverall usability of public outdoor spaces.


## 2 Experiment

### 2.1 Background
We want to determine under how much surface area of the solar panals could maximize the charging efficiency with the maximum illuminance

So we searched online for the calculation of the relationships between illuminace andcharging power：
G = K • Ev [1] ⟹ G ∝ Ev [2]
Iph = G • Aeff • EQE • (q• λeff / hc) [3]⟹ Iph ∝ G[4]

Illuminance Ev (lux, lx) measures brightness weighted by the human eye's photopic response, peaking at 555 nm. Irradiance G (W m⁻²) is the true radiant power per unit area relevant to energy conversion. When varying cloud thickness only scales light intensity without altering spectral composition, the ratio Ev/G is constant K — hence lux and irradiance are directly proportional across all measurements.

Photons striking the p-n junction excite electron-hole pairs via the internal photoelectric effect, generating photocurrent Iph. All other terms are constants for a given panel under fixed-spectrum light: Aeff = effective cell area, EQE ≈ 0.85 = fraction of photons converted, q = elementary charge (1.60 × 10⁻¹⁹ C), λeff = mean photon wavelength, h = Planck's constant, c = speed of light. Therefore Iph ∝ G ∝ Ev — a strict linear relationship.

Voc [3]= (nkT/q) • ln(Iph / I0) [5]

Pmax [3]= FF • Voc • Isc ⟹ Pmax = k′ • Ev + b [6]

Voc is the cell voltage when no current flows. n = ideality factor (~1.3 for Si), k = Boltzmann's constant (1.38 × 10⁻²³ J K⁻¹), T = temperature (K), I0 = reverse saturation current (~10⁻¹⁰ A). Although Voc depends logarithmically on Iph, over the experimental lux range (5,000–35,000 lx, a 7× variation), the change is only ~51 mV — less than 9% of the baseline ~0.6 V for silicon. Voc is therefore treated as approximately constant.

Fill factor FF (≈ 0.80 for monocrystalline Si) measures the "squareness" of the I–V curve; short-circuit current Isc ≈ Iph ∝ Ev. Since FF and Voc are both approximately constant, Pmax ∝ Isc ∝ Ev, predicting a linear power–illuminance relationship. The constant k′ = FF • Voc • Aeff • EQE • qλ/hc; the intercept b reflects the activation threshold. So, this theoretical function should reflect the actual relationships between Pmax and Ev.



**Research Question**
How does illuminance, modulated by varying cloud-layer thickness, affect the maximum output power of crystalline silicon photovoltaic panels, and to what extent does this relationship conform to the theoretical linear prediction Pmax ∝ Ev?
(as shown in the theoretical function above):
Pmax = k′ • Ev + b 


### 2.2 Materials:

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


## 3 Solution

### 3.1 Inspiration

**The Inspiration:**  The cooling, large-scale shade structures at Singapore's Clarke Quay

**The Problem:**  Chengdu's extreme summer heat keeps people away from outdoor parks.

**Our Upgrade:**  A "Solar Umbrella." It provides cooling shade and harnesses the intense sunlight to generate electricity, turning a weather problem into a sustainable solution

### 3.2 Core Functions

**Cooling Shade & Mist:** 
The large umbrella blocks the hot sun, while a water mist spray system makes the air feel much cooler.

**Pet-Friendly:** 
Adding a dog poop bag dispenser on the pole, it keeps the park clean and makes pet owners happy.

**Phone Charging (Day & Night):** 
Solar panels on the top generate electricity. We also added a battery, so you can charge your phone even at night or on cloudy days!

![local pic](/images/csp/corefun.jpg "Core Function") 

### 3.3 Real World Impact

Why Here: 
The strong direct sunlight makes these areas too hot to use, but they are perfect for solar power collection.
Effect: 
Provides cooling shade where people can comfortably relax, play, and charge their devices.

<div style="display: flex; justify-content: space-between; align-items: center;">
  <img src="/images/csp/diss1.jpg" alt="discussion" style="width: 48%;"/>
  <img src="/images/csp/diss2.jpg" alt="discussion" style="width: 48%;"/>
</div>

<br>
![local pic](/images/csp/diss3.jpg "diss3") 


### 3.4 Existing Upgrades

Why Here:
These structures provide basic shade but waste solar potential and lack active cooling features. 
Effect: 
Upgrading facilities with solar panels and cooling mist allows people to enjoy the cooler shade and charge their devices at the same time, without taking up extra land.

### 3.5 Conclusion&Reflection

We found that a larger solar panel area directly increases power output, which is why we maximized the surface to ensure the charging efficiency. 
However, we overlooked how changing daily sun angles affects actual efficiency and lacked sufficient consideration for other animals like birds, even though it’s pet-friendly. Moving forward, we aim to optimize the design by updating it into a more suitable version for birds living and apply it to other parks as well.


## 4 Experiment Design

### 4.1 Methodology

- IV: The luminance (Lux)
- DV: The power delivered by panels(W)
- CV: The number of panels, Material of the panels, 

**Experimental Procedure:**
  1. Apparatus & Setup: Unfold the flexible solar array to expose all four panels completely flat on an unobstructed lawn to guarantee a uniform angle of incidence. Connect the system to a digital multimeter to measure real-time electrical power output (P, in W). Place a smartphone flat and parallel against the exposed panels to continuously monitor ambient illuminance (E, in lux).
  2. Rapid Data Cycle: Under a specific natural lighting condition, wait for multimeter stabilization, then simultaneously record the power and illuminance for the 4-panel configuration. To ensure the independent variable (light intensity) remains constant, swiftly fold one panel beneath the array (obscuring it from sunlight) and immediately record data for the 3-panel configuration. Instantly repeat this folding mechanism for a second panel to capture the 2-panel data.
  3. Variation & Control: Unfold the array back to its full 4-panel state. Wait for natural environmental shifts (e.g., cloud cover) to establish a new illuminance level, then repeat this rapid 4-3-2 folding cycle across a broad spectrum of light intensities (5,000 to 35,000 lux). Throughout all trials, ensure the exposed panels remain strictly horizontal to prevent mechanical shading.

### 4.2 Data Processing

**Raw data**
![local pic](/images/csp/rawdata.png "rawdata") 

**Explanation**

![local pic](/images/csp/4panels.png "4panels") 
![local pic](/images/csp/3panels.png "3panels") 
![local pic](/images/csp/2panels.png "2panels") 


### 4.3 Explanation

Following the procedure above, we collected a number of raw data points of luminance and the corresponding power delivered. The processed dataset was then imported into Logger Pro to generate scatter plots of Illuminance (E) versus Power Output (P). For each array configuration, a line of best fit was plotted alongside the steepest (maximum) and shallowest (minimum) trend lines bounded by the experimental error bars. From the analysis of the app, the best fit line, the max&min slope, the intercept, and the R2 (coefficient of determination) can be acquired.

The absolute uncertainty of the gradient was calculated using the standard mathematical model △m=(m_max-m_min)/2 . The percentage uncertainty of the slope was then derived by dividing this absolute uncertainty by the gradient of the best-fit line (m_bestfit). The percentage uncertainties are 17.49%, 21.14%, and 13.89% for the 4, 3, and 2-panel configurations, respectively. Similarly, the absolute uncertainty of the y-intercept was determined. For R2, the values are 0.9509, 0.8524, and 0.8148 for the 4, 3, and 2-panel setups, respectively, thereby statistically quantifying the validity, variance, and reliability of our linear regression models prior to final evaluation.

### 4.4 Evaluation&Conclusion

Based on the graphical analysis,we conclude that ambient illuminance and electrical power output maintain a fundamentally linear relationship,a hypothesis most strongly validated by the 4-panel configuration's high coefficient of determination(R²)of 0.9509.
Although the R²values decrease for the 3-panel(0.8524)and 2-panel(0.8148)setups—indicating a larger data spread and less definitive correlation as the active area reduces—the overarching linear trend remains consistent.

The calculated percentage uncertainties for the slopes of the 4,3,and 2-panel arrays are 17.49%,21.14%,and 13.89%,respectively.These uncertainties,alongside the presence of high-illuminance outliers,
primarily stem from two specific measurement limitations:the reliance on manual human-eye estimation to average rapidly fluctuating multimeter values,and optical refractions within the smartphone camera lens,which severely distorted the lux readings under intense direct sunlight.

| **WEAKNESS** | **IMPROVEMENT** |
| ---                                                                                                                                    | ---                                                                                                                            |
| Unstable Manual Readings: Relying on human observation to record rapidly fluctuating multimeter data introduced significant subjective error.  | Utilize a digital data logger or dedicated voltage/current sensors connected directly to computer software (such as Logger Pro) to record and average electrical output continuously over a set timeframe. |
| ---                                                                                                                                    | ---                                                                                                                            |
| Inaccurate Lux Measurement: Using a smartphone camera application to measure high-intensity sunlight caused optical refraction and reflection, heavily distorting the independent variable.  | Employ a dedicated, standalone digital lux meter equipped with a cosine-corrected diffuser to prevent internal light scattering and accurately capture direct solar radiation.|
| ---                                                                                                                                    | ---                                                                                                                            |
| Dynamic Environmental Variables: Experimenting outdoors meant that variables such as cloud cover, temperature, and sun angle were constantly shifting, contributing to the data outliers.  | Conduct baseline control trials in a laboratory setting using an artificial, adjustable light source (e.g., halogen lamps) to strictly isolate the illuminance variable before field testing.|

![local pic](/images/csp/exhib.jpg "Exhibition") 

## Bibliography
[1] Ryer, A. (1997). Light Measurement Handbook. International Light Technologies.

[2] Hecht, E. (2017). Optics (5th ed., pp. 55–58). Pearson Education.

[3] Shockley, W. (1949). Bell System Technical Journal, 28(3), 435–489.

[4] Nelson, J. (2003). The Physics of Solar Cells (pp. 140–158). Imperial College Press.

[5] Sze, S. M. & Ng, K. K. (2007). Physics of Semiconductor Devices (3rd ed., pp. 79–124). Wiley.

[6] Luque, A. & Hegedus, S. (Eds.). (2011). Handbook of Photovoltaic Science and Engineering (2nd ed., pp. 82–130). Wiley.


---

[← Back](javascript:history.back()) [🏠 Home](/)