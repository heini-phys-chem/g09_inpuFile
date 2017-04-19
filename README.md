# g09_inputFile
A bash script that generates g09 input files (only TS and IRC calculations available)

## Tutorial
The script will ask you to define several input parameters:
```
Chk file (<file.chk>):
```
enter the name of the check point file.
```
nprocshared (integer):
```
number of cores used in calculation (has to be an integer)
```
mem (in GB, integer):
```
memory used per core (has to be an integer)
```
method (g09 syntax, with basis set):
```
the method you want to use (g09 syntax with basis set) eg.
- PM6
- B3LYP 6-31G*
- ...

```
calculation (<ts> or <irc>):
```
specify the type of calculation you want to use. So far only OPT=TS and IRC are available.
The line in the input file will look like:
- OPT=(TS,CalcAll,NoEigenTest)
- IRC=(CalcAll,MaxPoints=300) geom=check

For the IRC calculation you don't need a coordinate file (informations are in the check point file). For the TS calculation you need to specify an .xyz file.
```
enter coord file <path/to/coordFile.xyz>
```

As a last step you have to define the charge of the molecule and its spin multiplicity

## Example input files
For IRC calculations:
```
Chk=test.chk 
%nprocshared=8 
%mem=2GB 
#n PM6 irc=(CalcAll,maxpoints=300) geom=check

titel

0 1
```
For TS calculations:
```
%Chk=test.chk
%nprocshared=8
%mem=2GB
#n B3LYP 6-31G* OPT=(ts,CalcAll,NoEigenTest)

 titel
 
 0 1
 C -0.63915 0.25896 0.07123
 C -0.86034 -1.13733 -0.45706
 H -3.48896 0.06908 1.69981
 .
 .
 .
 
```
