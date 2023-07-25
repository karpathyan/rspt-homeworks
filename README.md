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
# Date 26/July/2023
- Working on https://github.com/karpathyan/day1-basics
- Error in Step 10 Generate DOS:
    - Created a `green.inp` file with the followwing text:
       
```bash
matsubara
1024  60  60  10   ! nmats head body tail

convergency
1d-6 1d-5  0  0    ! ndelta sigma_acc maxiter maxsolveriter

energymesh
1001 -1.0 1.0 0.01

projection
2                  ! 1: MT, 2: ORT

spectrum
Dos Pdos

cluster
1 0              ! ntot udef [nsites]
1 2 1 1 0        ! t l e site basis[cubic harm] U J or F0 F2 F4 (F6)
```
   - This results in Error: 
```bash
Rank 0, STOP in green: readcluster: Invalid state: (e.g. missing orbital or standard ORT with several tails) 1 2 1 1 0                                                                                            er=    1
application called MPI_Abort(MPI_COMM_WORLD, 1) - process 0
[unset]: write_line error; fd=-1 buf=:cmd=abort exitcode=1
:
system msg for write_line failure : Bad file descriptor
```
