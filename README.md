#     MNXL - Validate models using restraints from Crosslinking-Mass Spectrometry
     
     Copyright 2016 MNXL Inventor and Birkbeck College University of London.
                          The MNXL Inventor is: Josh Bullock
 
     MNXL is available under Public Licence.
     This software is made available under GPL V3

     Please cite your use of MNXL in published work:
     
     J.Bullock, J. Schwab, K. Thalassinos, M. Topf (2016)
     The importance of non-accessible crosslinks and solvent accessible surface distance
     in modelling proteins with restraints from crosslinking mass spectrometry. 
     Molecular and Cellular Proteomics (15) pp.2491–2500

INSTALLATION:
Open a terminal session and a move to the directory MNXL is in.

type "setup.py install"


RUNNING MNXL:

type "mnxl" plus any of the below flags:

  -h, --help            show this help message and exit
  -data DATA            specify experimental data: -data <input_data.txt>
  -mod_xl MOD_XL [MOD_XL ...]
                        specify simulated model data: -mod_xl <model_data.txt>
  -jwalk                flag to use if starting from .pdb files and running
                        Jwalk
  -pdb PDB [PDB ...]    specify input pdbs: -mod_xl <model_data.pdb>

EXPERIMENTAL DATA INPUT:

Crosslinks should be listed in a pipe-delimited .txt file as so:

res1|chain1|res2|chain2|

eg. 34|A|56|B|

If your pdb file has no chain, insert a lowercase x

eg. 34|x|56|x|

See the example file for a sample list.

MODEL DATA INPUT:

Jwalk output files (or output from any other distance calculation program) can be 
used as long as it is formatted as follows:

Index         Model         Atom1         Atom2         SASD          Euclidean Distance
1             test.pdb      LYS-52-A-CA   LYS-129-A-CA  57.1556689427 26.1061187272
etc. 

OUTPUT:

MNXL_scores.txt gives the MNXL score as well as the number of matched, violating, and non-accessible crosslinks
