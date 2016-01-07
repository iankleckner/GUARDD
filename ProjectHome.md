## Contents ##


## Motivation ##
  * Protein dynamics are essential for life
  * NMR dispersion experiments can be used to quantify protein dynamics
  * Dispersion experiments are difficult to analyze
    * Under-determined – many fitting parameters compared to amount of observed data
    * Visual inspection of curve and data does not validate fit accuracy
      * Curve fit may go through data points even if parameters are inaccurate
    * Dynamics are complex
      * Global or local protein motions?
    * What is the nature of the dynamic process?
      * Unfolding? Exchange towards defined minor state? Conformational selection?
  * Currently available RD analysis software does not provide graphical interface nor advanced display options
  * Less "black box", more "hands on"


## Features of program ##
  * Graphical user interface
  * Point-and-click functionality for ease of use

<a href='http://chemistry.osu.edu/~foster.281/guardd/home/main-GUARDD-2011.07.13--01.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd/home/main-GUARDD-2011.07.13--01.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

### Accurate site-specific fits to two-state exchange model at any timescale ###
  * Global fits of data at multiple temperatures, magnetic fields and quantum coherences
  * Carver-Richards formulae describes two-state exchange at any timescale (not fast approximation)
  * Statistical comparison of two-state exchange and no-exchange models

<a href='http://chemistry.osu.edu/~foster.281/guardd//tutorial/tutorial-GUARDD-2011.06.17--11.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd//tutorial/tutorial-GUARDD-2011.06.17--11.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>


### Refinement of best fit for maximum accuracy ###
  * Grid search of initial fitting conditions helps identify global minimum of χ<sup>2</sup>
  * Produces plots of χ<sup>2</sup>-space to determine quality of fit
  * User can drive fit towards most reasonable solution
  * Ill-defined parameters can be marked to avoid mis-interpretation and maximize extraction of information

<a href='http://chemistry.osu.edu/~foster.281/guardd//tutorial/tutorial-GUARDD-2011.06.17--20.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd//tutorial/tutorial-GUARDD-2011.06.17--20.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

### Examine dynamic motion of entire molecule ###
  * Group analysis and parameter examiner displays results in novel ways
  * Can identify global motions and nature of minor excited state

<a href='http://chemistry.osu.edu/~foster.281/guardd//manual/GUARDD-Groups-2011.06.23--05.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd//manual/GUARDD-Groups-2011.06.23--05.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>


### Optimization and education with RD Simulator ###
  * Explore the nature of RD phenomena to plan future experiments and to enhance understanding of RD
  * Export simulated data for subsequent fitting and analysis

<a href='http://chemistry.osu.edu/~foster.281/guardd//home/GUARDD-SimRD-2011.06.24--06.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd//home/GUARDD-SimRD-2011.06.24--06.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>


### Access the power of Matlab ###
  * Utilize Matlab's built-in functionality to help display and interpret your results
  * Matlab Central provides a large community for documentation and user support [link](http://www.mathworks.com/matlabcentral/)

<a href='http://www.mathworks.com/'> <img src='http://chemistry.osu.edu/~foster.281/guardd//home/matlab-icon-th.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>




## Online documentation and support ##
  * Documentation can be read on the Wiki page [link](http://code.google.com/p/guardd/w/list)
  * Issues can be reported and reviewed online [link](http://code.google.com/p/guardd/issues/list)
  * Email the author and a community of users for support [link](http://groups.google.com/group/guardd)

## Download latest version ##
  * Check the download section for the latest version [link](http://code.google.com/p/guardd/downloads/list)
  * Four MATLAB requirements: [MATLAB](http://www.mathworks.com), [Optimization Toolbox](http://www.mathworks.com/products/optimization/), [Curve Fitting Toolbox](http://www.mathworks.com/products/curvefitting/), [Statistics Toolbox](http://www.mathworks.com/products/statistics/)


## Acknowledgements ##
  * Foster Lab members for debugging during development
  * Advisor Prof. Mark Foster [link](http://chemistry.osu.edu/~foster.281/)
  * The Ohio State University Biochemistry Dept. [link](http://www.biosci.ohio-state.edu/~biochem/)
  * The Ohio State University Biophysics Program [link](http://www.biosci.ohio-state.edu/~biophys/)
  * The Ohio State University [link](http://www.osu.edu/)
  * National Institutes of Health [link](http://www.nih.gov/)

## Studies using GUARDD ##
  1. Kleckner, I. R., Gollnick, P., & Foster, M. P. (2012). Mechanisms of allosteric gene regulation by NMR quantification of microsecond–millisecond protein dynamics. Journal of molecular biology, 415(2), 372-381.
  1. Chan, H. W. (2012). Investigating the enzymatic mechanisms of the inverting and retaining glycosyltransferases by NMR spectroscopy. PhD Dissertation.
  1. Coyne III, H. J., De, S., Okon, M., Green, S. M., Bhachech, N., Graves, B. J., & McIntosh, L. P. (2012). Autoinhibition of ETV6 (TEL) DNA binding: appended helices sterically block the ETS domain. Journal of molecular biology, 421(1), 67-84.
  1. Chan, P. H., Cheung, A. H., Okon, M., Chen, H. M., Withers, S. G., & McIntosh, L. P. (2013). Investigating the structural dynamics of α-1, 4-galactosyltransferase C from Neisseria meningitidis by nuclear magnetic resonance spectroscopy. Biochemistry, 52(2), 320-332.
  1. Hoang, J. N. (2013). Investigating the Folding Network of Calmodulin Using Fluorine NMR (Doctoral dissertation).
  1. Aramini, J. M., Hamilton, K., Ma, L. C., Swapna, G. V. T., Leonard, P. G., Ladbury, J. E., ... & Montelione, G. T. (2014). 19F NMR Reveals Multiple Conformations at the Dimer Interface of the Nonstructural Protein 1 Effector Domain from Influenza A Virus. Structure, 22(4), 515-525.
  1. DeKoster, G. T., Delaney, K. J., & Hall, K. B. (2014). A Compare-and-Contrast NMR Dynamics Study of Two Related RRMs: U1A and SNF. Biophysical journal, 107(1), 208-219.
  1. Horváth, G., Egyed, O., & Toke, O. (2014). Temperature Dependence of Backbone Dynamics in Human Ileal Bile Acid-Binding Protein: Implications for the Mechanism of Ligand Binding. Biochemistry, 53(31), 5186-5198.
  1. Chen, C. H., Namanja, A. T., & Chen, Y. (2014). Conformational flexibility and changes underlying activation of the SUMO-specific protease SENP1 by remote substrate binding. Nature communications, 5.
  1. Rajagopal, P., Tse, E., Borst, A. J., Delbecq, S. P., Shi, L., Southworth, D. P., & Klevit, R. E. (2015). A conserved histidine modulates HSPB5 structure to trigger chaperone activity in response to stress-related acidosis. eLife, e07304.

## Citing GUARDD ##
  * GUARDD manuscript: [http://dx.doi.org/10.1007/s10858-011-9589-y](http://dx.doi.org/10.1007/s10858-011-9589-y)

  * **Please cite your usage of GUARDD**
    1. Kleckner, I. R., & Foster, M. P. (2012). GUARDD: user-friendly MATLAB software for rigorous analysis of CPMG RD NMR data. Journal of biomolecular NMR, 52(1), 11–22. doi:10.1007/s10858-011-9589-y


## Author ##
  * (C) [Ian Kleckner](http://ianrobertkleckner.blogspot.com)
  * Mark Foster's Lab
  * The Ohio State University
  * Columbus, OH, USA