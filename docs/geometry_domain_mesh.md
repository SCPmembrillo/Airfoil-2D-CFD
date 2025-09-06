## Geometry and Domain
The geometry of the NACA 2412 airfoil is imported from Airfoil Tools, where a rectangular domain of 20 m × 10 m is created, as shown below.
<div align="center">
  <img src="images/domain" alt="images/domain" width="700"/>
</div>

The domain is subdivided into internal, intermediate, and external regions.
## Mesh
###  Y-Plus Wall Distance Estimation
`y+` is a dimensionless parameter that quantifies the distance of the first mesh cell from the wall, normalized by the flow's viscosity and friction velocity.

<div align="center">
  <img src="images/y+.svg" alt="images/y+.svg" width="126"/>
</div>

The following steps are used to calculate the wall distance:

- Determine the friction velocity, `u`, as:
<div align="center">
  <img src="images/u_tau.svg" alt="images/u_tau.svg" width="125"/>
</div>

- Determine the wall shear stress, `tau`, as:  
<div align="center">
  <img src="images/tau_w.svg" alt="images/tau_w.svg" width="200"/>
</div>

- Approximate the friction coefficient,`Cf`, using the flat-plate correlation for turbulent flow:
<div align="center">
  <img src="images/cf.svg" alt="images/cf.svg" width="150"/>
</div>

### Inflation Layers
Inflation layers are a commonly used technique to capture the boundary layer accurately in CFD simulations. 

The following steps are used to calculate the number of inflation layers:

- Determine the boundary layer thickness, `sigma`, as:
<div align="center">
  <img src="images/sigma_99.svg" alt="images/sigma_99.svg" width="200"/>
</div>

- Determine number of layers, `N`, as:
<div align="center">
  <img src="images/N.svg" alt="images/N.svg" width="250"/>
</div>

The simulations are performed under standard sea-level conditions, i.e., `ρ` = 1.225 kg/m^3 and `μ`= 1.789 × 10^-5 Pa·s. The airfoil chord length is 1 m and the growth rate `G` is 1.2

<div align="center">
  
**Table 1. Inflation layer calculations**  

| Reynolds Number | Number of Layers | First Layer Thickness (m) |
|-----------------|------------------|---------------------------|
| 500,000         | 18               | 0.00020844                |
| 1,000,000       | 24               | 0.00005986                |
| 1,500,000       | 27               | 0.00002885                |

</div>
<div align="center">
  <img src="images/inflation_1" alt="images/inflation_1" width="700"/>
</div>
<div align="center">
  <img src="images/inflation_2" alt="images/inflation_2" width="700"/>
</div>

<div align="center">
  
**Table 2. Mesh quality for Re = 500,000**

| Angle of Attack | Aspect Ratio (Max) | Skewness (Max / Avg)     | Orthogonal Quality (Min) |
|-----------------|--------------------|--------------------------|---------------------------|
| 0°              | 5.475              | 0.90347 (0.070089)       | 0.3312                    |
| 10°             | 10.102             | 0.97883 (0.068314)       | 0.19469                   |
| 15°             | 6.5408             | 0.93664 (0.068965)       | 0.28537                   |

**Table 3. Mesh quality for Re = 1,000,000**

| Angle of Attack | Aspect Ratio (Max) | Skewness (Max / Avg)     | Orthogonal Quality (Min) |
|-----------------|--------------------|--------------------------|---------------------------|
| 0°              | 24.314             | 0.92078 (0.068657)       | 0.30484                   |
| 10°             | 19.200             | 0.96760 (0.068364)       | 0.21422                   |
| 15°             | 19.118             | 0.94843 (0.068434)       | 0.25967                   |

**Table 4. Mesh quality for Re = 1,500,000**

| Angle of Attack | Aspect Ratio (Max) | Skewness (Max / Avg)     | Orthogonal Quality (Min) |
|-----------------|--------------------|--------------------------|---------------------------|
| 0°              | 24.024             | 0.98533 (0.077146)       | 0.17152                   |
| 10°             | 20.525             | 0.97187 (0.077209)       | 0.18401                   |
| 15°             | 20.379             | 0.98431 (0.077565)       | 0.16664                   |
</div>
