# Drag Reduction in Underwater Vehicles: Ventilated Cavitation

This project dives into unsteady turbulent flow dynamics within ventilated super cavities surrounding underwater vehicle. 
CFD Code:
- ANSYS Fluent 2020 R1

Following are the fluid flow characterixtics:
- Unsteady, Compressible
- Three phase flow ( Volume-of-Fluid (VOF) multiphase simulation)
- Turbulent flow (Reynolds-Averaged Navier-Stokes (RANS))
- Supercavitated flow


## Validation with Experimental Data

The objective is to validate our numerical scheme against the experimental results of Sun [1], and simulation results of Xu [2] Sun performed experiments in a water tunnel with high-speed cameras measuring the flow characteristics at different time intervals. Figure 1 shows the underwater vehicle, with a 1 mm ventilation slot and two points to measure the pressure variation. A 3D geometry is used, and flow characteristics are observed across a 3D domain. 
We define cavitation number and Reynolds number as

$$\sigma=\frac{P_{\infty}-P_c}{\frac{1}{2} \rho_l V_{\infty}^2}$$

$$
Re = \frac{\rho U L}{\mu}
$$

where:
- $P_{\text{v}}$ : Vapor pressure of the liquid.
- $P_{\infty}$ : Free stream pressure.
- $\rho$ : Density of the fluid.
- $U$ : Velocity of the object.
- $\mu$ : molecular viscosity

### Flow Parameters
The following are flow parameters

| **Parameter**            | **Value**         | **Description**                                                                 |
|--------------------------|-------------------|---------------------------------------------------------------------------------|
| Cavitation Number        | 2.0              | Achieved as suggested by Xu [14].                                              |
| Vapor Pressure           | 2300 Pa          | Vapor pressure used in the simulation.                                         |
| Free Stream Velocity     | 8.07 m/s         | Velocity of the fluid in the free stream.                                      |
| Free Stream Pressure     | 68400 Pa         | Calculated free stream pressure based on the given conditions.                 |
| Reynolds Number          | 312000           | Indicates a highly turbulent flow regime under the simulation conditions.       |

### Mesh 

| **Parameter**             | **Value/Details**                                                         | **Description**                                                                                      |
|---------------------------|---------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------|
| Computational Domain Size | 980 mm × 260 mm × 260 mm                                                 | A 3D computational domain as used by Xu and Sun [2, 1].                                             |
| Projectile Diameter       | 40 mm                                                                    | Diameter of the projectile modeled within the computational domain.                                 |
| Air Inlet Length          | 1 mm                                                                     | The length of the air inlet for ventilated cavitation.                                              |
| Mesh Cells                | 0.59 million                                                            | Generated using the **CutCell method**, excelling at handling complex geometries.                   |
| Meshing Method            | CutCell Method                                                          | Ensures accurate representation of complex geometries without requiring a conforming mesh.          |
| y+ Value                  | 50                                                                       | Wall function grid is set to achieve this value, ensuring proper boundary layer representation.     |


Vapour fraction of air is plotted as iso-surface contour with volume fraction values of 0.4-0.8 for air. Since the cavitation number of 2 is much greater, we do not expect a large cavitation from the water to vapour phase. Figure 9 presents the comparison of present simulations with water tunnel experiments of Sun [1], and simulation results using LES model by Xu [2]. Initially vapour is observed for τ= 2-3. However, as the solution continues, the air phase dominates, and the pressure is not less enough to cavitate the water phase to vapour. Therefore, after τ = 3, we observe no vapour phase. Figure 9 is a comprehensive representation for ventilated cavitation using RANS model. At τ = 14.12, we observe partial cavitation in the water tunnel experiment. A small partial cavitation can also be seen at the τ = 14.12. A further partial cavitation is observed at τ = 24.21. However, small-scale cavities may not be visible in the RANS model nor in LES experiment. 

The pressure variation of points 1 and 2 as shown in Figure 6 are plotted against τ in Figure 10  from dimensionless time τ= 0 to τ= 40

The results are mech better than the LES simulation by Xu [2]. The reason being using a better time step approach. Reducing the time step further results in better and accurate result. However, initially, the flow is fluctuating from τ = 0-2. This can be accounted for a high turbulence between vapour and air phase. K-w-SST model has a limitation to model the eddies to a certain limit. It can be considered a limiting case of RANS model, but can be reduced by using lower time step, and a better mesh.

## Final result

We observe a remarkable 27% reduction in drag because of Ventilated Cavitation. Moreover, a 10% decrease in the cavitation number leads to a significant 100% drag reduction.

NOTE: The I have only provided the case setup for experimental validation of this setup. The Reference geometry is extracted from [2]



## References

1. Sun, T., et al., Numerical modeling and simulation of the shedding mechanism and vortex structures at  the development stage of ventilated partial cavitating flows. European Journal of Mechanics-B/Fluids, 2019. 76: p. 223-232.
2. Xu, C., X. Zhao, and B.C. Khoo, Numerical investigation of ventilated cavitating flow from high to low 
cavitation numbers. Ocean Engineering, 2022. 266: p. 112782
