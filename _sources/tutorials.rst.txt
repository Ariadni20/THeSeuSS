=========
Tutorials
=========

Calculation of the IR and Raman spectra for a water molecule (non-periodic system)
==================================================================================

The following ``THeSeuSS`` input file calculates the IR and Raman spectra for a water molecule at the DFT level (using ``FHIaims``):::

    cell_geometry_optimization True
    submission True
    files_preparation True
    spectra_calculation True
    code aims
    functional pbe
    eev 1E-5
    rho 1E-7
    etot 1E-6
    forces 1E-4
    sc_iter_limit 300
    geometry 1E-5
    energy 1E-5
    steps 400
    species tight
    output_file aims.out
    dispersion False
    broadening lorentzian
    fwhm 10.0
    commands module load intel; export OMP_NUM_THREADS=1; export MKL_NUM_THREADS=1; export MKL_DYNAMIC=FALSE; ulimit -s unlimited; /software/aims.scalapack.mpi.x > aims.out


The following ``THeSeuSS`` input file calculates the IR and Raman spectra for a water molecule at the DFTB level (using ``DFTB+``):::

    cell_geometry_optimization True
    submission True
    files_preparation True
    spectra_calculation True
    code dftb+
    output_file output
    dispersion False
    max_force_component 1E-05
    max_steps 4000
    SCC_tolerance 1E-7
    max_SCC_iterations 100
    broadening lorentzian
    fwhm 10.0
    commands dftb+ > output
