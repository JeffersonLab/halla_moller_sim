# Jefferson Lab Hall A Moller Polarimeter Simulation

Simulation of the Thomas Jefferson National Accelerator Facility's Hall A Moller Polarimeter. 

## General Information

### MolPol Installation

Packages required to build this program:

Geant 4.10 or better
cmake v. 2.6 or better
root 5.31 or better

_Additional packages may be required for your system or particular options selected during Geant4 or Root installations._

Program can be cloned from github with _git clone_ command from command line.

After being downloaded you can enter the *halla_molpol_sim* and do the following.

Create a build directory, use cmake & make to build the Geant4 application.

*mkdir build*
*cd build*
*cmake* <path to MolPol>
*make*

Compiling the application this way should automatically copy the macros folder. You can start with the macro example named _runexmaple.mac_.

To run in batch mode perform the following:

*./MolPol runexample.mac* 

### Run With Visualization 
***

To run with visualization, simply execute the MolPol program.

_./MolPol_

This will bring up the Qt/OGL Display.

From here, as standard with G4 you can execute a macro with

_control/execute yourMacro_

**Note: You shouldn't run with an excessive amount of events in visualization mode. It would be advisable to use custom MolPol macro options such as _krypteffect_ and _onlymollers_ to cut down on the number of rays which need to be drawn.** 

## MolPol Macro Usage

### List of MolPol Macros
***
The following is a table of the current MolPol macros. --_dericking 02/05/2020_

| Command      |        Type         |        Description |
|:-------------|:--------------------|:-------------------|
| **GENERAL**  | | |
|/MolPol/gen   | String              | moller: moller scatter generator; LUND: generates from LUND file; beam: single beam | 
|/MolPol/filename | String           | output file name for results 
|**GENERATOR EFFECTS** | | |
|/MolPol/calculateLevchuk |  Boolean | Introduce Levchuk Effect: true or false |
|/MolPol/targetPolPct | Double no unit | Target polarization. Currently 0.08012
|/MolPol/radCorrections | Boolean | Calculate all four (4) radiative corrections in moller diagram
|/MolPol/remollMS | Boolean | Use REMOLL scattering model within target pre-generative.
|/MolPol/seed | Integer | The seed for the simulation.
| **STEPPING ACTION OPTIONS** | | | 
| /MolPol/Step/krypteffect | Boolean | Stepping action, treat all materials besides target and dipoel exit windows as kryptonite.
| /MolPol/Step/onlymollers | Boolean | Kill any particles that aren't the original two mollers.
| **GENERATED PHASE SPACE** | | |
| /MolPol/thcommin  | Dbl w/ Unit | Center of mass theta minimum for moller generation. | 
| /MolPol/thcommax   | Dbl w/ Unit | Center of mass theta maximum for moller generation. | 
| /MolPol/phimin   | Dbl w/ Unit | Phi minimum for moller generation. | 
| /MolPol/phimax  | Dbl w/ Unit | Phi maximum for moller generation. | 
| **BEAM INFORMATION** | | | 
| /MolPol/fx   | Dbl w/ Unit | X origin of beam in the global coordinate system. | 
| /MolPol/fy    | Dbl w/ Unit | Y origin of beam in the global coordinate system. | 
| /MolPol/fz  | Dbl w/ Unit | Z origin of beam in the global coordinate system. | 
| /MolPol/xsmear   | Dbl w/ Unit | X Sigma of gaussian smear in beam profile. | 
| /MolPol/ysmear   | Dbl w/ Unit | Y Sigma of gaussian smear in beam profile. | 
| /MolPol/beamRotZX   | Dbl w/ Unit | Small angle beam-kick from Z->X in radians or degrees. | 
| /MolPol/beamRotZY   Dbl w/ Unit |  | 
| /MolPol/beamE  |  Dbl w/ Unit |  | 
| **GEOMETRY MODIFIABLES** | | | 
| /MolPol/Geo/jawWidth  | Double w/ Unit | Total Pb jaw opening width | 
| /MolPol/Geo/targetPosition  | Double w/ Unit | Target position on the beamline | 
| /MolPol/Geo/targetThickness | Double w/ Unit | Target thickness, can be modified to near zero (0) but not zero. | 
| **FIELD INFORMATION** | | |
| /field/MagSourceMode   | Int | Souce Mode, 1: Using ideal pole tips | 
| /field/setQ1T | Double No Unit | Pole tip of Q1 in teslas. | 
| /field/setQ2T  | Double No Unit | Pole tip of Q2 in teslas.  | 
| /field/setQ3T  | Double No Unit | Pole tip of Q3 in teslas.  | 
| /field/setQ4T  | Double No Unit |  Pole tip of Q4 in teslas. | 
| /field/setQ5T    | Double No Unit | Pole tip of dipole in teslas.  | 
| /field/setQ6T   | Double No Unit |  Field strength for superconducting helmholt coils | 
| /field/update |  | Update/Initialize Moller magnet fields.| 
| **MAGNET OFFSETS** | | | 
| /field/setQ1XOffset  | Double w/ Unit | Offset for Q1 field in X direction. | 
| /field/setQ1YOffset  | Double w/ Unit | Offset for Q1 field in Y direction. | 
| /field/setQ2XOffset  | Double w/ Unit | Offset for Q2 field in X direction. | 
| /field/setQ2YOffset  | Double w/ Unit | Offset for Q2 field in Y direction. | 
| /field/setQ3XOffset  | Double w/ Unit | Offset for Q3 field in X direction. | 
| /field/setQ3YOffset  | Double w/ Unit | Offset for Q3 field in Y direction. | 
| /field/setQ4XOffset  | Double w/ Unit | Offset for Q4 field in X direction. | 
| /field/setQ4YOffset  | Double w/ Unit | Offset for Q4 field in Y direction. | 
| /field/setQ6XOffset  | Double w/ Unit | Offset for Helmholtz field in X direction. |
| /field/setQ6YOffset  | Double w/ Unit | Offset for Helmholtz field in Y direction. |
| /field/setQ6XRot     | Double w/ Unit | Offset for Helmholtz field in Y direction. |
| /field/setQ6YRot     | Double w/ Unit | Offset for Helmholtz field in Y direction. |

