# Drag Reduction in Underwater Vehicles: Ventilated Cavitation

This project dives into unsteady turbulent flow dynamics within ventilated super cavities surrounding underwater vehicle. 

Following are the fluid flow characterixtics:
- Unsteady, Compressible
- Three phase flow ( Volume-of-Fluid (VOF) multiphase simulation)
- Turbulent flow (Reynolds-Averaged Navier-Stokes (RANS))
- Supercavitated flow


## Final result

The image explains the evolution of the cavity around the projectile

![image](https://github.com/user-attachments/assets/ffc2e59c-e532-4a21-bdab-208892d579af)

https://github.com/user-attachments/assets/f51adce3-11e9-426d-900f-5546f757a74e

Here we have a comparison of Ventilated and a Non ventilated flow

![image](https://github.com/user-attachments/assets/7d16e227-bab7-4885-b875-ffc8aab49b08)

https://github.com/user-attachments/assets/f690b741-daad-420d-9e4d-ce7fb05b3d34



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
| Cavitation Number        | 2.0              | Achieved as suggested by Xu [2].                                              |
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


The final Mesh is here:

![image](https://github.com/user-attachments/assets/3b225384-44c7-4513-b31f-698889fdaf1f)

## CFD Code:
- ANSYS Fluent 2020 R1

## References

1. Sun, T., et al., Numerical modeling and simulation of the shedding mechanism and vortex structures at  the development stage of ventilated partial cavitating flows. European Journal of Mechanics-B/Fluids, 2019. 76: p. 223-232.
2. Xu, C., X. Zhao, and B.C. Khoo, Numerical investigation of ventilated cavitating flow from high to low 
cavitation numbers. Ocean Engineering, 2022. 266: p. 112782
