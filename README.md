# rspt-homeworks
# my_rspt_notes
- Download the cif file
- Generate the rspt input files using cif2cell

   `cif2cell -f my_file.cif -p rspt --rspt-new --rspt-spinpol --rspt-mtradii=3 --setup-all --k-resolution=0.1`
  ## Explanation about the rspt.inp file
  - Lattice vectors are given by each column ( usually it is each row)
  - atoms: all the atoms
  -  spinpol: enable spin polarization
  -  
