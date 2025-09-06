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
- Determine number of layers, `N`, as:
