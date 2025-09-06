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
  <img src="images/y+.svg" alt="images/y+.svg" width="150"/>
</div>

The following steps are used to calculate the wall distance:

- Determine the friction velocity, \(u_\tau\), as:  
- Determine the wall shear stress, \(\tau_w\), as:  
- Approximate the friction coefficient, \(C_f\), using the flat-plate correlation for turbulent flow:
<div align="center">
  <img src="images/cf.svg" alt="images/cf.svg" width="150"/>
</div>

### Inflation Layers
