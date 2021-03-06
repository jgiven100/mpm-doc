# Linear Elastic

The linear elastic model is the simpliest model for homogeneous isotropic materials. Relevant equations are presented briefly below.

## Elastic Modulus

The bulk, shear, and constrained moduli ($K$, $G$, and $M$, respectively) are defined as follows, 

$$ K = \frac{E}{3 (1 - 2\nu)}, $$

$$ G = \frac{E}{2(1 + \nu)}, $$

$$ M = \frac{E(1 - \nu)}{(1 + \nu)(1 - 2 \nu)} , $$

where $E$ is the Young's modulus and $\nu$ is the Poisson's ratio.

## Wave Velocities

The shear and pressue wave velocities ($v_s$ and $v_p$, respectively) are defined [1] as follows,

$$ v_s = \sqrt{\frac{M}{\rho}}, $$

$$ v_p = \sqrt{\frac{G}{\rho}}, $$

where $\rho$ is the density. Both wave velocities are automatically computed and stored as JSON material properties when the linear elastic model is used. $v_s$ and $v_p$ are accessible via `property["swave_velocity"]` and `property["pwave_velocity"]`, respectively. 

## Input Parameters

An example input JSON is provided for a 2D linear elastic model.

```
  "materials": [
    {
      "id" : 0,
      "type" : "LinearElastic2D",
      "density" : 2000,
      "youngs_modulus" : 10000000.0,
      "poisson_ratio" : 0.3
    }
  ]
```
  * "id" is the material ID, used for multiple material models in a simulation
  * "type" is the material type ("LinearElastic2D" for 2D plain strain condition, "LinearElastic3D" for 3D),
  * "density" is the density of the material,
  * "youngs_modulus" is the constant elastic parameter Young's modulus $E$,
  * "poisson_ratio" is the constant elastic parameter Poisson's ratio $\nu$.


## References

[1] Al-Kafaji, I. K. J. (2013). Formulation of a Dynamic Material Point Method (MPM) for Geomechanical Problems. PhD Thesis. University of Stuttgart. 
