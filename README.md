# g09_inpuFile
A bash script that generates g09 input files (only TS and IRC calculations available)

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
- OPT=(ts,CalcAll,NoEigenTest)
- irc=(CalcAll,maxpoints=300) geom=check

For the IRC calculation you don't need a coordinate file (informations are in the check point file). For the TS calculation you need to specify an .xyz file.
```
enter coord file <path/to/coordFile.xyz>
```

As a last step you have to define the charge of the molecule and its spin multiplicity
