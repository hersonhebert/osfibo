# FIBOS
## Description
The FIBOS package was developed with the objective of enabling the use of the Occluded Surface methodology, created by Patrick Fleming, in environments other than Fortran. Additionally, we added a new way of generating dots, which allows for better symmetry between the atoms of protein molecules.
## Functionalities
The package allows for the calculation of occluded areas between atoms of a molecule, using an input PDB file. For this, two methodologies can be used: OS or FIBOS. In both, contact area data is generated, and consequently, the file containing information regarding the calculation results based on the selected methodology.
## Requirements
Firstly, it is necessary to have devtools installed in Rstudio:

install.packages(“devtools”)

Note: Please note that the package requires some additional libraries such as:
  * bio3d
  * dplyr
  * readr
  * stringr
  * tidyr

## How use
### Installing the Package

library(devtools)

install_github(“https://github.com/hersonhebert/fibos”)
### Using the Package:

The package consists of two functions: occluded_surface and read_OS. We will separately discuss the use of each of them.

* occluded_surface(path_pdb, online, method)

It is the function responsible for calculating the occluded areas between atoms and generating the "prot.srf" file. It is important to note that the file reading is not done automatically. For this, the read_prot function should be used, passing the file as a parameter.

The three parameters present in the function declaration are important as they define its functionality. The description of each parameter is as follows:

+ path_pdb: It is the name/path of the PDB file that represents a protein. To obtain the file online, it is only necessary to write the name of the file in question. If it is saved locally, the value of this variable is the path of that file.

+ online: This is a logical parameter that will define whether the PDB file will be obtained online or from locally saved files. The following rule applies to determine the values to be passed:

+ method: This is the method to be chosen for the calculation of occluded areas between atoms. After the selection of the method, the "prot.srf" file is generated to be read later. The following values can be passed as parameters to this function:

*** Traditional OS: 1
*** Fibonacci OS (FIBOS): 2

* read_OS(prot)

Responsible for reading the data file on the occlusion of areas of the atoms of the used protein. This function has only one parameter to be passed, which is prot.

*prot: Name/path of the "prot.srf" file that was generated by calling the occluded_surface function.

## Authors
## Status
In Progress.
