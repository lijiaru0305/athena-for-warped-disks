# `disk_2d_viscous_gap`

Example Athena++ problem generator for a **2D viscous Keplerian disk with a density gap**. The setup is currently designed for a **globally isothermal equation of state**. The code includes:

- user-defined boundary conditions
- alpha-viscosity through a custom viscosity coefficient
- optional cooling source term for non-barotropic runs (WIP)
- a Gaussian-shaped radial density gap
- nearly-Keplerian disk initial conditions
  
---

## What this problem does

This problem is to test our implementation of the alpha viscosity. It initializes a Keplerian accretion disk with:

- a radial surface-density profile with a gap centered at `R_gap`
- rotation profile adjusted for radial pressure support
- ghost-zone boundary conditions for viscous accretion disks

The correct final state should have a steady power-law density profile and a constant accretion rate $\dot{M}$.

---

## Run

This setup is low-cost and can run on a personal computer:
```bash
./athena -i inputs/disk_2d_viscous_gap.athinput
```
---

## Included files

The following files are included:

- `athena`  
  Athena++ executable used to run the simulation with the chosen input file. Compiled on Quest, Northwestern’s high-performance computing cluster.

- `athinput.disk_2d_viscous_gap`  
  Athena++ input parameter file for this problem. It specifies the mesh, runtime options, hydrodynamic parameters, problem parameters, and output settings.
  
- `diagnosis.ipynb`  
  Jupyter notebook for post-processing and visualizing simulation outputs. Useful for checking the density profile and other diagnostics. **Data not included**.

- `disk_2d_viscous_gap.cpp`  
  Athena++ problem generator source file. This is the main physics setup, including the disk initial condition, density gap, viscosity prescription, and user-defined boundary conditions. This file is duplicated from `~/src/pgen/disk_2d_viscous_gap.cpp`.

- `Makefile`  
  Makefile that can be used to compile this version of Athena++ executable.


