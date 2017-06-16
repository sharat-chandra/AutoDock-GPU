This is the documentation for users: installation, required OS/GPU driverversions, at least one usage example with sample input files, etc.

# Installation
OCLADock is known to work in the following environment:

* Architecture: Intel x86_64
* Operating System: CentOS 6.7 & 6.8 / Ubuntu 16.04
 
# Requirements
* CPU:
	* Intel SDK for OpenCL v1.2
	* Intel OpenCL Runtime v16.1

* GPU
	* AMD APP SDK v3.0
	* AMDGPU-PRO v16.50

Other environments/configurations likely work as well, but are untested.

# Usage

## Basic
```zsh
./bin/ocladock_<type>_<N>wi -ffile <protein>.maps.fld -lfile <ligand>.pdbqt -nrun <nruns>
```
Mandatory arguments:
* Protein file: `-ffile <protein>.maps.fld`
* Ligand file:  `-lfile <ligand>.pdbqt`

## Example
```zsh
./bin/ocladock_gpu_64wi -ffile ./input_data/1stp/derived/1stp_protein.maps.fld -lfile ./input_data/1stp/derived/1stp_ligand.pdbqt -nrun 10
```
By default the output log file is written in the root folder: [docking.dlg](docking.dlg)

## Supported arguments
For a complete list of available arguments and their default values, check: [getparameters.cpp](host/src/getparameters.cpp)

| Argument | Description                  | Default value |
|----------|------------------------------|---------------|
| -nrun    | # Docking runs               | 1             |
| -nev     | # Energy evaluations         | 2500000       |
| -ngen    | # Generations                | 27000         |
| -lsit    | # Local-search iterations (max.) | 300       |
| -psize   | Population size              | 150           |
| -mrat    | Mutation rate                | 2 (%)         |
| -crat    | Crossover rate               | 80 (%)        |
| -lsrat   | Local-search rate            | 6 (%)         |
| -trat    | Tournament rate              | 60 (%)        |
| -resname | Name for docking output log  | "docking"     |