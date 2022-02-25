# Plm-complex

# Ligand prepartion

Antechamber and parameter check commands

`antechamber -i ../lig.mol2 -fi mol2 -o LIG.mol2 -fo mol2 -j 4 -at gaff -c bcc -nc 1`

`parmchk2 -i LIG.mol2 -f mol2 -o LIG.frcmod`

# Amber to Gromacs
`acpype -p com_solvated.top -x com_solvated.crd -b gmx` 

# Restraint
`echo 23 | gmx genrestr -f gmx_GMX.gro -fc 500 500 500 -n index.ndx`

# Eneregy mimisation
`gmx grompp -f inputs/em.mdp -c gmx_GMX.gro -p gmx_GMX.top -o em.tpr -v -n index.ndx`

`gmx mdrun -v -deffnm em`

# Activity:
2BJU: 0.034 micromolar (Link: https://www.jbc.org/action/showPdf?pii=S0021-9258%2820%2967439-7)
4YA8: 0.8 micromolar (Link: http://scripts.iucr.org/cgi-bin/paper?S2053230X15022049)
