## OPLSIDPSFF force field for GROMACS

### Introduction
This is the description of the concept and the usage of **OPLSIDPSFF** force field

Recently, we developed a residue-specific force field based on OPLS-AA/L force field with  
modified dihedral energy correlation map (CMAP) to simulate intrinsically disordered proteins (IDPs).  
You can use this force field in your research according to the following information.

### Usage
1. Enter the `OPLSIDPSFF` directory and you will find the force field files  
  
    *$ cd OPLSIDPSFF/*  
    *$ ls*  
	**OPLSIDPSFF.ff**  **test**  
 
2. Copy the force field `OPLSIDPSFF.ff` to your Gromacs force field directory  
  
	*$ cp -r OPLSIDPSFF.ff/ $GROMACS/share/gromacs/top*  
  
	[Note： $GROMACS is the directory where you install the Gromacs software.]  
	If you are neither a root user nor sudoer, and you have no permission to copy this folder  
	to $GROMACS/share/gromacs/top, you can put them into the place where you prepare  
	the .top and .gro files for simulation instead.  
  
	Example:  
    *$ cp -r OPLSIDPSFF.ff/ test/*  
    *$ cd test/*  
	  *$ gmx pdb2gmx -f test.pdb -o test.gro -water tip3p -p test.top -i test.itp -ignh*  
    ...  
    Select the Force Field:  
    From current directory:  
	  1: OPLS-AA-IDPs all-atom force field (2018 aminoacid dihedrals)  
    From $GROMACS/share/gromacs/top  
    2: AMBER03 force field (Duan et al., J. Comp. Chem. 24, 1999-2012, 2003)  
    3: AMBER03 protein, nucleic AMBER94 (Duan et al., J. Comp. Chem. 24, 1999-2012, 2003)  
    ...  
    [You can choose our force field by inputting "1" and then click "Enter"]  

### Reference  
When you publish or report results using CHARMM36IDPSFF force field, please cite the following papers  

- S. Yang, H. Liu, Y. Zhang, H. Lu, and H. F. Chen. Residue-Specific Force Field Improving the Sample of
  Intrinsically Disordered Proteins and Folded Proteins, *J. Chem. Inf. Model.*, 2019, **59**, 11, 4793–4805.
  
