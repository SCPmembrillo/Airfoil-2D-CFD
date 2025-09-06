## Geometry and Domain
The geometry of the NACA 2412 airfoil is imported from Airfoil Tools, where a rectangular domain of 20 m × 10 m is created, as shown below.
<div align="center">
  <img src="images/domain" alt="images/domain" width="700"/>
</div>

The domain is subdivided into internal, intermediate, and external regions.
## Mesh
###  Y-Plus Wall Distance Estimation
y+ is a dimensionless number that represents the distance of the first mesh cell from the wall, normalized by the flow’s viscosity and shear stress.

<div align="center">
  <img src="images/cf.svg" alt="images/cf.svg" width="150"/>
</div>
