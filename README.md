# Design-Compiler-Project-Starter
This repo holds several bash scripts with the objective of creating a certain type of structure for creating designs inside Synopsys Design Compiler projects.

The top script, "Project_creator.sh" is the executable one. This one holds several functions that are invoked inside the "main" procedure. 

The main procedure receives certain arguments, a list of arguments, specifying the name of the project to be created, and the name of the created scripts.

The front end structure is the directory where all the synthesis happens. The following images gives an outlook at how it looks.

![Alt text](img/Struct1.png?raw=true "Title")

Each subdirectory's function is stated below:

-db : Here will be outputted the resulting gate level netlist (*.v) and the *.sdf file (this one holds the delays for each cell, inside the synthetyzed design). Both files will be generated during RTL synthesis.

- libs: Hold the standart cell library, as well as its graphical representation (*.sdb).  

- reports: The reports generated will be dumped here by Design Compiler. 

- scripts: This subdirectory holds the scripts that will be run by Design Compiler. The scripts generated by the script here presented are written in *.tcl. A second script file is also generated, with the constraints. This second file is also written in tcl language. 

- source : This subdiretory holds the source RTL code (either Verilog (*.v) or VHDL (*.vhdl) code)

- work : This subdiretory holds the designs generated by Design Compiler during the elaborate step. 

![Alt text](img/Struct2.png?raw=true "Title")
 
For simulation, the present script creates a range of scripts to create the .saif file, and make power estimations based on real simulations. The present scrip also creates a script called run_sim.sh with the intention of executing the simulation. 

The power estimation procedure is based on the work of this [guy.](http://www.googoolia.com/wp/2014/06/07/estimating-power-at-rtl-using-synopsys-design-compiler/)

Part of the structure is based on [THIS](http://userwww.sfsu.edu/necrc/files/synopsys%20tutorials/ASIC%20Design%20Flow%20Tutorial.pdf) tutorial, reading this material is highly recommended, since it highlights and further explains some very important points concerning the design flow.