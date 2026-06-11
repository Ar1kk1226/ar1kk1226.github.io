---
layout: page
title: 太阳能伞
lang: zh
date: 2026-06-08
---

这是基于城市热岛效应，制作和一个太阳能伞实验，并经测试分析形成的项目报告，来看下我们是如何做的吧。

<!-- excerpt -->

先看下我们的海报

![本地图片](/images/csp/poster.jpg "海报") 

## 1 概念


## 2 试验

### 2.1 背景

### 2.2 材料:

1. 4张太阳板
2. Type C 线
3. DC watt
4. 带数据采集软件（Logger Pro)的PC机
5. 安装实时采集光照强度的手机
6. 定时器


<div style="display: flex; justify-content: space-between; align-items: center;">
  <img src="/images/csp/computer.jpg" alt="computer" style="width: 48%;"/>
  <img src="/images/csp/solarpan.jpg" alt="solar" style="width: 48%;"/>
</div>



## 3 解决方案

### 3.1 灵感

**The Inspiration:**  The cooling, large-scale shade structures at Singapore's Clarke Quay

**The Problem:**  Chengdu's extreme summer heat keeps people away from outdoor parks.

**Our Upgrade:**  A "Solar Umbrella." It provides cooling shade and harnesses the intense sunlight to generate electricity, turning a weather problem into a sustainable solution

### 3.2 核心功能

**Cooling Shade & Mist:** 
The large umbrella blocks the hot sun, while a water mist spray system makes the air feel much cooler.

**Pet-Friendly:** 
Adding a dog poop bag dispenser on the pole, it keeps the park clean and makes pet owners happy.

**Phone Charging (Day & Night):** 
Solar panels on the top generate electricity. We also added a battery, so you can charge your phone even at night or on cloudy days!

![local pic](/images/csp/corefun.jpg "Core Function") 

### 3.3 现实世界影响

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


### 3.4 升级

### 3.5 结论与反思

We found that a larger solar panel area directly increases power output, which is why we maximized the surface to ensure the charging efficiency. 
However, we overlooked how changing daily sun angles affects actual efficiency and lacked sufficient consideration for other animals like birds, even though it’s pet-friendly. Moving forward, we aim to optimize the design by updating it into a more suitable version for birds living and apply it to other parks as well.


## 4 试验设计

### 4.1 方法

- IV: The luminance (Lux)
- DV: The power delivered by panels(W)
- CV: The number of panels, Material of the panels, 

**Experimental Procedure:**
  1. Apparatus & Setup: Unfold the flexible solar array to expose all four panels completely flat on an unobstructed lawn to guarantee a uniform angle of incidence. Connect the system to a digital multimeter to measure real-time electrical power output (P, in W). Place a smartphone flat and parallel against the exposed panels to continuously monitor ambient illuminance (E, in lux).
  2. Rapid Data Cycle: Under a specific natural lighting condition, wait for multimeter stabilization, then simultaneously record the power and illuminance for the 4-panel configuration. To ensure the independent variable (light intensity) remains constant, swiftly fold one panel beneath the array (obscuring it from sunlight) and immediately record data for the 3-panel configuration. Instantly repeat this folding mechanism for a second panel to capture the 2-panel data.
  3. Variation & Control: Unfold the array back to its full 4-panel state. Wait for natural environmental shifts (e.g., cloud cover) to establish a new illuminance level, then repeat this rapid 4-3-2 folding cycle across a broad spectrum of light intensities (5,000 to 35,000 lux). Throughout all trials, ensure the exposed panels remain strictly horizontal to prevent mechanical shading.

### 4.2 数据处理

**Raw data**
![local pic](/images/csp/rawdata.png "rawdata") 

**Explanation**

![local pic](/images/csp/4panels.png "4panels") 
![local pic](/images/csp/3panels.png "3panels") 
![local pic](/images/csp/2panels.png "2panels") 


### 4.3 原因分析

Following the procedure above, we collected a number of raw data points of luminance and the corresponding power delivered. The processed dataset was then imported into Logger Pro to generate scatter plots of Illuminance (E) versus Power Output (P). For each array configuration, a line of best fit was plotted alongside the steepest (maximum) and shallowest (minimum) trend lines bounded by the experimental error bars. From the analysis of the app, the best fit line, the max&min slope, the intercept, and the R2 (coefficient of determination) can be acquired.

The absolute uncertainty of the gradient was calculated using the standard mathematical model △m=(m_max-m_min)/2 . The percentage uncertainty of the slope was then derived by dividing this absolute uncertainty by the gradient of the best-fit line (m_bestfit). The percentage uncertainties are 17.49%, 21.14%, and 13.89% for the 4, 3, and 2-panel configurations, respectively. Similarly, the absolute uncertainty of the y-intercept was determined. For R2, the values are 0.9509, 0.8524, and 0.8148 for the 4, 3, and 2-panel setups, respectively, thereby statistically quantifying the validity, variance, and reliability of our linear regression models prior to final evaluation.

### 4.4 评估和结论

Based on the graphical analysis,we conclude that ambient illuminance and electrical power output maintain a fundamentally linear relationship,a hypothesis most strongly validated by the 4-panel configuration's high coefficient of determination(R²)of 0.9509.
Although the R²values decrease for the 3-panel(0.8524)and 2-panel(0.8148)setups—indicating a larger data spread and less definitive correlation as the active area reduces—the overarching linear trend remains consistent.

The calculated percentage uncertainties for the slopes of the 4,3,and 2-panel arrays are 17.49%,21.14%,and 13.89%,respectively.These uncertainties,alongside the presence of high-illuminance outliers,
primarily stem from two specific measurement limitations:the reliance on manual human-eye estimation to average rapidly fluctuating multimeter values,and optical refractions within the smartphone camera lens,which severely distorted the lux readings under intense direct sunlight.

| **缺点** | **优势** |
| ---                                                                                                                                    | ---                                                                                                                            |
| Unstable Manual Readings: Relying on human observation to record rapidly fluctuating multimeter data introduced significant subjective error.  | Utilize a digital data logger or dedicated voltage/current sensors connected directly to computer software (such as Logger Pro) to record and average electrical output continuously over a set timeframe. |
| ---                                                                                                                                    | ---                                                                                                                            |
| Inaccurate Lux Measurement: Using a smartphone camera application to measure high-intensity sunlight caused optical refraction and reflection, heavily distorting the independent variable.  | Employ a dedicated, standalone digital lux meter equipped with a cosine-corrected diffuser to prevent internal light scattering and accurately capture direct solar radiation.|
| ---                                                                                                                                    | ---                                                                                                                            |
| Dynamic Environmental Variables: Experimenting outdoors meant that variables such as cloud cover, temperature, and sun angle were constantly shifting, contributing to the data outliers.  | Conduct baseline control trials in a laboratory setting using an artificial, adjustable light source (e.g., halogen lamps) to strictly isolate the illuminance variable before field testing.|

![local pic](/images/csp/exhib.jpg "Exhibition") 

## 参考文献

[1] Ryer, A. (1997). Light Measurement Handbook. International Light Technologies.

[2] Hecht, E. (2017). Optics (5th ed., pp. 55–58). Pearson Education.

[3] Shockley, W. (1949). Bell System Technical Journal, 28(3), 435–489.

[4] Nelson, J. (2003). The Physics of Solar Cells (pp. 140–158). Imperial College Press.

[5] Sze, S. M. & Ng, K. K. (2007). Physics of Semiconductor Devices (3rd ed., pp. 79–124). Wiley.

[6] Luque, A. & Hegedus, S. (Eds.). (2011). Handbook of Photovoltaic Science and Engineering (2nd ed., pp. 82–130). Wiley.



---

[← 返回上一级](javascript:history.back()) [🏠 返回首页](/)