
# Branched Actin Network Simulation under Uniaxial Deformation

This folder contains a LAMMPS simulation script for modeling a branched actin network under uniaxial deformation. The simulation applies a small deformation along the z-axis and incrementally increases the strain over multiple steps, achieving a specified maximum strain amplitude. This setup allows for analysis of the structural response and relaxation behavior of the network under controlled deformation rates.

## Files

- **`in.boundary`**: LAMMPS input script that contains the simulation setup and deformation protocol.

## Usage

The simulation is run using LAMMPS with the following command:

```bash
lmp_mpi -v comprate XXX -in in.boundary
```

- **`comprate`**: A user-defined variable that sets the deformation rate. Replace `XXX` with a numeric value, typically `5000`, to control the strain rate of the deformation.

### Input and Process

1. **Initial Configuration**: The code reads an initial configuration file containing the starting structure of the branched actin network.
2. **Deformation and Relaxation Loop**:
   - An infinitesimal affine deformation is applied along the z-axis.
   - The system is then relaxed using viscous dynamics to allow the network to respond to the applied strain.
   - After each relaxation, the strain is incrementally increased.
3. **Looping**: This cycle continues until the desired maximum strain amplitude is reached.

## Key Parameters

- **Deformation Rate (`comprate`)**: Determines the speed of uniaxial deformation. This is specified by the `comprate` variable passed to LAMMPS and allows for adjustments to the simulation speed based on the required analysis.

## Requirements

- **LAMMPS**: The simulation requires a version of LAMMPS that supports `lmp_mpi` and input variables. Ensure LAMMPS is properly installed and configured in your environment.

## Example Command

To run the simulation with a deformation rate of 5000, use:

```bash
lmp_mpi -v comprate 5000 -in in.boundary
```

## Output

The simulation outputs files that track the deformation and relaxation state of the actin network at each strain step, enabling post-processing and analysis of the network's mechanical response under uniaxial deformation.

---

This README provides a summary of the contents and usage of this simulation code for modeling the deformation of a branched actin network. Adjust parameters as necessary for different simulation scenarios.
