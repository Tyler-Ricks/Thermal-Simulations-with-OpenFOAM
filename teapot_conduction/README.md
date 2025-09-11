# Teapot Conduction

## Case details:

**OpenFOAM version used:** v2012
**Solvers used:** laplacianFoam 
**Other tools used:** snappyHexMesh for creating a voxel mesh around a teapot .stl that the solver can work on

## Case Description:

This is a simulation of a hot teapot region getting cooled by room temperature air outside. It is not at all a very physically accurate simulation, as the test was for getting a teapot into OpenFOAM

## How to Run:

To run this simulation, 
1) Download the .zip file from the case, and extract them into the run directory in your openFoam installation. 
2) Open a terminal, and navigate to the case. **make sure to source the environment:**
    **linux or WSL:** 
    ```bash
    source ~/<path_to_OpenFoam>/etc/bashrc
3) From the root directory of the case, run **blockMeshDict**
4) After this executes, run **snappyHexMesh -overwrite**
5) After it finishes, run **laplacianFoam** to run the simulation
6) To view the simulation, open Paraview, then hit file>open. Find this case directory, and open the case.foam file
7) Click the dropdown that says "Solid Color", then select "T" to display the temperature. click the play button to watch

## Directory explanation

**./0** - Contains files for the initial conditions of the simulation. T describes temperature

**./constant** - Contains files and directories for the initial mesh, the blockMesh, and the snappyHexMesh

**./system** - Contains files that control how mesh generation, snappyhexMesh generation, and simulation happens. The file names are mostly self explanatory, except for controlDict, which controls the simulation details

