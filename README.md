# OpenFOAM tips and tricks

This repository was created to gather a collection of OpenFOAM tips, tricks and their evaluation. These experiments were performed during the author's dissertation project at the University of Edinburgh and the EU Horizon 2020 project HiDALGO, more specifically the Urban air pollution pilot. Take into account that these tips aim to get the highest execution efficiency possible and thus can sometimes sacrifice accuracy. Please, feel free to leave any comments, suggestions or corrections in the form of pull requests, issue, Telegram message ([https://t.me/MandM_Mario](https://t.me/MandM_Mario)) or email ([m.martreq@gmail.com](mailto:m.martreq@gmail.com)). 

## 1. General tips

* The `system/controlDict` file defines the execution iterations, write and time formats, among other parameters. 
  * `runTimeModifiable`, variable that defines if the program keeps checking `controlDict` for changes at the begining of each iteration. It should always be left `off` as it can potentially increase execution time in distributed executions.
  * Writting output files is another topic that can increase innecesarily the execution time, and it should be reduced to the minimum required. This can be done by tweaking `writeControl` and `writeInterval`. If no output is required, setting them to `timeStep` and a bigger value than `endTime` will reduce output to the first and last iterations. 
  * In addition to changing output exporting rate, `writeFormat` specifies the format of the output data files (`ascii` or `binary`). If the contrary is not required, output format should be left as `binary`.
  * Lastly, `writeCompression` should be left `off` unless storage is scarce. 

  
## 2. Testing tips

## 3. Promissing but not-yet-tested tips

* József Nagy suggests in [this YouTube video](https://www.youtube.com/watch?v=abcEriOI2Hs) to check a detalied overview at fvSchemes and fvSolution by Gavin Tabor that can be found in [this PDF](ftp://zw.releases.ubuntu.com/sourceforge/o/op/openfoam-extend/OpenFOAM_Workshops/OFW13_2018_Shanghai/Training/A-detailed-look-at-fvSchemes-and-fvSolution.pdf) that includes tips obtained by its author during his fifteen years of experience in OpenFOAM.

* Joel Guerrero, author of some courses/material in Wolf dynamics, has an [interesting document](http://www.arek.pajak.info.pl/wp-content/uploads/2015/03/14tipsandtricksOF.pdf) covering general OpenFOAM tips, including the use of `checkMesh` and `renumberMesh`, two computationally inexpensive tools that can assure mesh quality and improve simulation bandwith. 

## 4. Tutorials

* Wolf dynamics has a collection of tutorials that cover basic and advanced OpenFOAM functionalities in [its webpage](http://www.wolfdynamics.com/tutorials.html). The beginner tutorials go over some of OpenFOAM base examples. In addition, this website/organization offers basic and advanced training courses. 

* OpenFOAM official [tutorials](https://wiki.openfoam.com/Tutorials). 
