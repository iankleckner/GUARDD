## Contents ##


## Goals ##
  * Background on CPMG RD method
  * Details on GUARDD data organization, features, and reference materials


## Theoretical and technical details ##

### Scientific questions addressed by RD NMR ###

  * **Question**: Is this molecule flexible in the μs-ms time window?
    * **Answer**: via R<sub>ex</sub> from visual inspection of single RD NMR experiment

  * **Question**: If so, what is the nature of this exchange process?
    * **Note**: Typically, exchange processes are considered as at least one site of a single molecule which occupies at least two distinct local structures (AKA states or configurations), denoted A and B [link](Manual#Two-state_exchange_model.md)

  * **Question**: What is the chemical environment (e.g., structure) of this alternate configuration?
    * **Answer**: via chemical shift difference Δω obtained from at least one RD NMR experiment [link](Manual#Two-state_exchange_model.md)

  * **Question**: On average, how often is this alternate configuration sampled?
    * **Answer**:  via total exchange rate k<sub>ex</sub> from at least one RD NMR experiment [link](Manual#Two-state_exchange_model.md)

  * **Question**: What is the relative population of this alternate configuration?
    * **Answer**: via population P<sub>A</sub> from at least one RD NMR experiment [link](Manual#Two-state_exchange_model.md)

  * **Question**: How much activation energy is required to access this alternate configuration?
    * **Answer**: via activation energies E(A→B) and E(B→A) from several RD experiments (Arrhenius analysis) [link](Manual#Arrhenius:_Determining_activation_energy.md)

  * **Question**: What is the relative energy, enthalpy and entropy of this alternate configuration?
    * **Answer**: via energy ΔG (via P<sub>A</sub>), enthalpy ΔH, entropy ΔS from several RD experiments (van't Hoff analysis) [link](Manual#vant_Hoff:_Determining_enthalpy.md)

  * **Question**: Is the alternate configuration a well-defined fold? Is it unfolded?
    * **Answer**: via chemical shift difference Δω, enthalpy ΔH, entropy ΔS from several RD experiments (See Kleckner & Foster, 2011 [here](Manual#References.md))

  * **Question**: Are motions in this molecule unified, coupled or independent?
    * **Answer**: via exchange rates k<sub>A</sub> and k<sub>B</sub>, enthalpy ΔH, entropy ΔS and activation energies E(A→B) and E(B→A) for several sites from several RD experiments (See Kleckner & Foster, 2011 [here](Manual#References.md))


### Chemical exchange phenomenon ###
  * **Goal**: _Present the NMR phenomenon that enables characterization of μs-ms dynamics_

<a href='http://chemistry.osu.edu/~foster.281/guardd//manual/figure-chemical_exchange/figure-chem_exchange_NMR-GUARDD.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd//manual/figure-chemical_exchange/figure-chem_exchange_NMR-GUARDD.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

_Adapted from Kleckner and Foster, 2011_

  * Certain dynamic processes in the μs-ms time window lead to characteristic broadening of the NMR signal
  * This "exchange broadening" can obscure the observables and in some cases render the NMR signal undetectable
  * However, this contains valuable information on the underlying dynamic process
  * The relaxation dispersion (RD) NMR experiment can access this information by use of a spin-echo pulse train

### The RD experiment refocuses chemical exchange broadening R<sub>ex</sub> ###
  * **Goal**: _Present the NMR experiment that quantitatively characterizes μs-ms dynamics_

<a href='http://chemistry.osu.edu/~foster.281/guardd//manual/figure-CPMG_RD/figure-CPMG_RD--experiment.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd//manual/figure-CPMG_RD/figure-CPMG_RD--experiment.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

_From Kleckner and Foster, 2011_

  * Carr-Purcell Meiboom-Gill Relaxation Dispersion (CPMG RD) uses spin-echo pulse trains to suppress relaxation due to exchange processes on the µs-ms timescale.
  * **(a)** The number of spin-echo pulses applied during the fixed relaxation time directly determines the CPMG frequency via ν<sub>CPMG</sub> = 1 / (4τ).
    * The applied CPMG pulse train is shown above each relaxation delay (ν<sub>CPMG</sub> = 100, 500 and 1100 Hz).
    * These pulses reduce the signal relaxation rate during the relaxation delay by refocusing exchange broadening (i.e., reducing R<sub>ex</sub>).
  * **(b)** The observed signal intensity remaining at the end of the TCPMG relaxation delay is used to obtain an effective relaxation rate , where I<sub>0</sub> is the signal intensity in the absence of the relaxation delay (i.e., when TCPMG = 0).
  * **(c)** The dispersion Curve reports on dynamics by plotting relaxation rate as a function of refocusing frequency.

## Two-state exchange model ##
  * **Goal**: _Present the simplest and most commonly used model to describe μs-ms dynamics_

<a href='http://chemistry.osu.edu/~foster.281/guardd//manual/figure-RD_Parameters/figure-rd_parameters.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd//manual/figure-RD_Parameters/figure-rd_parameters.png' alt='[UNLOADED IMAGE]' width='300'> </img> </a>

  * **(a)**A single NMR probe (e.g., Ala 12N<sup>H</sup>) is considered to alternate between local structures designated A and B, which have distinct NMR chemical shifts in 1H and/or AX dimensions.
    * Although two signals are shown here, the “minor” B state is not detected directly because its NMR signal is too weak and/or too broad. However, the A↔B exchange yields a quantitative effect on the measured RD Curve of signal A.

**The two-state exchange model requires 4-5 parameters to describe a single RD Curve**
  * **Structural parameters (1 or 2 per NMR probe)**
    1. |Δω<sub>H</sub>| (rad/s): Magnitude of <sup>1</sup>H chemical shift difference between A and B states (for MQ Curves only)
    1. |Δω<sub>X</sub>| (rad/s): Magnitude of <sup>A</sup>X chemical shift difference between A and B states (AX = <sup>13</sup>C or <sup>15</sup>N)
  * **Kinetic parameters (2 per temperature per NMR probe)**
    * Parameters used in fitting equations
      1. k<sub>ex</sub> (/s): Total exchange rate between state A and B; k<sub>ex</sub> = k<sub>A</sub> + k<sub>B</sub>
      1. P<sub>A</sub> (-): Population fraction of state A; P<sub>A</sub> = k<sub>B</sub> / (k<sub>A</sub>+k<sub>B</sub>) with P<sub>A</sub> + P<sub>B</sub> = 1
    * Alternate physical parameterization, which requires knowledge of both k<sub>ex</sub> and P<sub>A</sub>
      1. k<sub>A</sub> (/s): Average frequency (not velocity!) of transition from state A to state B
      1. k<sub>B</sub> (/s): Average frequency (not velocity!) of transition from state B to state A
  * **Relaxation parameter (1 per Curve per NMR probe)**
    1. R<sub>2</sub><sup>0</sup> (Hz): Relaxation rate of the A state in the absence of exchange
  * **(b)** The MQ Curve shown here is simulated using |ΔωH| = 8 Hz, |ΔωX| = 201 Hz, k<sub>ex</sub> = 1000 /s, P<sub>A</sub> = 90%, and  = 10 Hz.


## Assigning parameters for fitting ##
  * **Goal**: _Fitting requries five parameters per Curve, but often parameters can be shared when Curves are aggregated into Curvesets, which are aggregated into Groups_
    * Details on Curves, Curvesets, and Groups are [here](Manual#Organizing_Data.md)

<a href='http://chemistry.osu.edu/~foster.281/guardd//manual/data_management-example/figure-data_management-example.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd//manual/data_management-example/figure-data_management-example.png' alt='[UNLOADED IMAGE]' width='300'> </img> </a>

_(Figure above) (a) Hierarchical data structures used in GUARDD, (b) example data structure [shown here](Manual#Example_parameter_assignment.md)_

  * Each **Curve** is designated a unique **R<sub>2</sub><sup>0</sup>**
    * R<sub>2</sub><sup>0</sup> = Transverse relaxation rate in the absence of exchange (Hz)
    * **Assume**: Relaxation rates of states A and B are equal (R<sub>2A</sub><sup>0</sup> = R<sub>2B</sub><sup>0</sup>)

  * One or more Curves are aggregated into a **Curveset**, which designate the same chemical shift differences **|Δω<sub>H</sub>| and |Δω<sub>X</sub>|**
    * **Assume**: |Δω<sub>H</sub>| (ppm) and |Δω<sub>X</sub>| (ppm) are independent of temperature
      * Therefore, each unique temperature yields an independent measure of |Δω<sub>H</sub>| and/or |Δω<sub>X</sub>|
    * **NMR**: Resonance frequency scales with magnetic field strength
      * Therefore, each unique B<sub>0</sub> field yields an independent measure of |Δω<sub>X</sub>|
      * See calculations [here](Manual#Converting_ppm_to_rad/s.md)
    * **NMR**: An experiment may be designed to detect a particular quantum coherence
      * Therefore, each unique quantum coherence yields an independent measure of |Δω<sub>H</sub>| and/or |Δω<sub>X</sub>|
      * Single Quantum (SQ) experiments are sensitive to only |Δω<sub>H</sub>| or |Δω<sub>X</sub>|
      * Multiple Quantum (MQ) experiments are sensitive to the sum |Δω<sub>H</sub> + Δω<sub>X</sub>|
      * See Korzhnev, et al. (2005) for more information: [Quantum Coherences in dispersion](Manual#References.md)

  * One or more Curvesets are aggregated into a **Group**, which designates the kinetic parameters **(P<sub>A</sub> and k<sub>ex</sub> at each temperature)**
    * **Physics**: Kinetic parameters are determined by experimental conditions
      * E.g., temperature, buffer, sometimes concentration but NOT magnetic field strength
      * Therefore, each repeat condition (same or different B<sub>0</sub>) yields an independent measure of P<sub>A</sub> and k<sub>ex</sub>
    * There are at least **two methods** to specify P<sub>A</sub> and k<sub>ex</sub> at each temperature
    * Method A - No constraint on rate analysis
      * Define P<sub>A</sub> and k<sub>ex</sub> at each temperature explicitly
    * Method B - Constrain rate analysis via ΔH and E<sub>AB</sub>
      * Define P<sub>A</sub> and k<sub>ex</sub> at a single temperature, T<sub>0</sub>
      * Define ΔH for temperature-dependence of P<sub>A</sub> (vant Hoff)
      * Define E<sub>AB</sub> for temperature-dependence of k<sub>A</sub> and, using ΔH, k<sub>B</sub> and therefore k<sub>ex</sub> = k<sub>A</sub>+k<sub>B</sub> (Arrhenius)
    * See calculations [here](Manual#Arrhenius:_Determining_activation_energy.md)

### Example parameter assignment ###
  * **Goal**: _Check the command window output for itemization of each parameter in a given Group_
    * Use the debugging output option `OUTPUT_DEBUG_UPDATE_FIT_PARAMS` (in [Settings window](Manual#Settings.md), on by default)

<a href='http://chemistry.osu.edu/~foster.281/guardd//manual/data_management-example/figure-data_management-example.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd//manual/data_management-example/figure-data_management-example.png' alt='[UNLOADED IMAGE]' width='300'> </img> </a>

_(Figure above) (a) Hierarchical data structures used in GUARDD, (b) example data structure discussed below_

  * **Goal**: Show two ways (A or B) to itemize temperature-depenence of P<sub>A</sub> and k<sub>ex</sub>
  * **Example: Method A - No constraint on rate analysis**
    * Define P<sub>A</sub> and k<sub>ex</sub> at each temperature

  * **Notation**
    * CS = Curveset number (1 or 2)
    * C = Curve number within the Curveset (1, 2, or 3)
    * CTOT = Total Curve number within the Group (1, 2, 3, 4, 5, or 6)
```
FUNCTION: Group.updateFitParams
Working on CS=1, Ile 10\delta_1
	Working on C=1 (CTOT=1), 800-MQ-25C
		Itemizing parameter 1 (dwH @ CS1, C1)
		Itemizing parameter 2 (dwX @ CS1, C1)
		Itemizing parameter 3 (PA @ 298K) *PA0*
		Itemizing parameter 4 (kex @ 298K) *kex0*
		Itemizing parameter 5 (R20 @ CS1, C1)
	Working on C=2 (CTOT=2), 600-MQ-25C
		Linking dwH to parameter 1, scaled by 0.750091x
		Linking dwX to parameter 2, scaled by 0.750091x
		Linking PA to parameter 3, scaled by 1.000000x
		Linking kex to parameter 4, scaled by 1.000000x
		Itemizing parameter 6 (R20 @ CS1, C2)
	Working on C=3 (CTOT=3), 800-MQ-37C
		Linking dwH to parameter 1, scaled by 1.000000x
		Linking dwX to parameter 2, scaled by 1.000000x
		Itemizing parameter 7 (PA @ 310K) *PA0*
		Itemizing parameter 8 (kex @ 310K) *kex0*
		Itemizing parameter 9 (R20 @ CS1, C3)
Working on CS=2, Leu 22\delta_1
	Working on C=1 (CTOT=4), 800-MQ-25C
		Itemizing parameter 10 (dwH @ CS2, C1)
		Itemizing parameter 11 (dwX @ CS2, C1)
		Linking PA to parameter 3, scaled by 1.000000x
		Linking kex to parameter 4, scaled by 1.000000x
		Itemizing parameter 12 (R20 @ CS2, C1)
	Working on C=2 (CTOT=5), 600-MQ-25C
		Linking dwH to parameter 10, scaled by 0.750091x
		Linking dwX to parameter 11, scaled by 0.750091x
		Linking PA to parameter 3, scaled by 1.000000x
		Linking kex to parameter 4, scaled by 1.000000x
		Itemizing parameter 13 (R20 @ CS2, C2)
	Working on C=3 (CTOT=6), 800-MQ-37C
		Linking dwH to parameter 10, scaled by 1.000000x
		Linking dwX to parameter 11, scaled by 1.000000x
		Linking PA to parameter 7, scaled by 1.000000x
		Linking kex to parameter 8, scaled by 1.000000x
		Itemizing parameter 14 (R20 @ CS2, C3)
```


  * **Example: Method B - Constrain rate analysis via ΔH and E<sub>AB</sub>**
    * Define P<sub>A</sub> and k<sub>ex</sub> at a single temperature, T<sub>0</sub>
    * Define ΔH for temperature-dependence of P<sub>A</sub> (vant Hoff)
    * Define E<sub>AB</sub> for temperature-dependence of k<sub>A</sub> and, using ΔH, k<sub>B</sub> and therefore k<sub>ex</sub> = k<sub>A</sub>+k<sub>B</sub> (Arrhenius)
    * **Note**: this uses ΔH and E<sub>AB</sub> instead of P<sub>A</sub>(37C) and k<sub>ex</sub>(37C)

```
FUNCTION: Group.updateFitParams
		Number of temperatures 2 > 1
		Itemizing parameter 1 (dH)
		Itemizing parameter 2 (Eab)
Working on CS=1, Ile 10\delta_1
	Working on C=1 (CTOT=1), 800-MQ-25C
		Itemizing parameter 3 (dwH @ CS1, C1)
		Itemizing parameter 4 (dwX @ CS1, C1)
		Itemizing parameter 5 (PA @ 298K) *PA0*
		Itemizing parameter 6 (kex @ 298K) *kex0*
		Itemizing parameter 7 (R20 @ CS1, C1)
	Working on C=2 (CTOT=2), 600-MQ-25C
		Linking dwH to parameter 3, scaled by 0.750091x
		Linking dwX to parameter 4, scaled by 0.750091x
		Linking PA to parameter 5, scaled by 1.000000x
		Linking kex to parameter 6, scaled by 1.000000x
		Itemizing parameter 8 (R20 @ CS1, C2)
	Working on C=3 (CTOT=3), 800-MQ-37C
		Linking dwH to parameter 3, scaled by 1.000000x
		Linking dwX to parameter 4, scaled by 1.000000x
		Linking PA @ 310K to PA0 @ T0=298K (param 5) via Temp (310K), dH (param 1), and Eab (param 2)
		Linking kex @ 310K to kex0 @ T0=298K (param 6) via Temp (310K), dH (param 1), and Eab (param 2)
		Itemizing parameter 9 (R20 @ CS1, C3)
Working on CS=2, Leu 22\delta_1
	Working on C=1 (CTOT=4), 800-MQ-25C
		Itemizing parameter 10 (dwH @ CS2, C1)
		Itemizing parameter 11 (dwX @ CS2, C1)
		Linking PA to parameter 5, scaled by 1.000000x
		Linking kex to parameter 6, scaled by 1.000000x
		Itemizing parameter 12 (R20 @ CS2, C1)
	Working on C=2 (CTOT=5), 600-MQ-25C
		Linking dwH to parameter 10, scaled by 0.750091x
		Linking dwX to parameter 11, scaled by 0.750091x
		Linking PA to parameter 5, scaled by 1.000000x
		Linking kex to parameter 6, scaled by 1.000000x
		Itemizing parameter 13 (R20 @ CS2, C2)
	Working on C=3 (CTOT=6), 800-MQ-37C
		Linking dwH to parameter 10, scaled by 1.000000x
		Linking dwX to parameter 11, scaled by 1.000000x
		Linking PA to parameter 5, scaled by 1.000000x
		Linking kex to parameter 6, scaled by 1.000000x
		Itemizing parameter 14 (R20 @ CS2, C3)
```

## Organizing data ##
  * **Goal**: _Organize data in hierarchical manner to provide framework for fitting procedures_

<a href='http://chemistry.osu.edu/~foster.281/guardd//manual/data_management-large/figure-data_management-large.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd//manual/data_management-large/figure-data_management-large.png' alt='[UNLOADED IMAGE]' width='300'> </img> </a>

_(Figure above) Datasets contain Curves, which are linked to by Curvesets within Groups_

### Dataset ###
  * **Goal**: _Store a CPMG NMR dataset and the experimental conditions during acquisition_

  * Properties
    * **name**: _Name of dataset (e.g., 'MQ 800MHz 25C')_
    * **AX\_String**: _<sup>13</sup>C or <sup>15</sup>N_
    * **B<sub>0</sub>**: _Magnetic field strength (<sup>1</sup>H MHz)_
    * **Temp**: _Temperature (K)_
    * **TCPMG**: _Total CPMG time in pulse sequence_
    * **SQX**: _True=Single Quantum dataset (Δω<sub>H</sub> fixed to zero), False=Multiple Quantum dataset (Δω<sub>H</sub> may be non-zero)_

  * Data for each dispersion Curve
    * Intensity values and errors
    * R2eff values and errors
    * ν<sub>CPMG</sub> values
    * Pointers to [Curves](Manual#Curve.md) which also hold this information

  * Key functions in code: **`Dataset.m`**
    * **`addData`**, Add a single RD Curve to the dataset
    * **`calculateR2eff`**
    * **`calculateErrorsUsingDuplicates`**
    * **`enforceMinimumError`**
    * **`readNlin`**


### Curve ###
  * **Goal**: _Store an NMR dispersion Curve (R<sub>2</sub><sup>Eff</sup>(ν<sub>CPMG</sub>)) and the experimental conditions during acquisition, which correspond to its parent [Dataset](Manual#Dataset.md)_

  * Properties
    * **name**: _Name of the Curve (e.g., 'Leu 12\delta\_2')_
    * **index**: _Residue number_
    * **atom**: _Name of atom (N, H\alpha, C\delta\_1, etc.)_
    * **residue**: _Name of residue (Ile, Leu, Arg, etc.)_

  * Properties from its parent [Dataset](Manual#Dataset.md) (copied to each Curve for convenience)
    * **AX\_String**: _<sup>13</sup>C or <sup>15</sup>N_
    * **B<sub>0</sub>**: _Magnetic field strength (<sup>1</sup>H MHz)_
    * **Temp**: _Temperature (K)_
    * **TCPMG**: _Total CPMG time in pulse sequence_
    * **SQX**: _True=Single Quantum dataset (Δω<sub>H</sub> fixed to zero), False=Multiple Quantum dataset (Δω<sub>H</sub> may be non-zero)_

  * Data from its parent [Dataset](Manual#Dataset.md)  (copied to each Curve for convenieice)
    * **Nobs**: _Number of observations_
    * **vcpmg**: _Array of vcpmg values (Hz)_
    * **R2eff**: _Array of R2eff values (Hz)_
    * **eR2eff**: _Array of errors in R2eff (Hz)_

  * Each Curve is unique, but can have multiple _appearances_, each of which points to the same source data
    * Multiple _appearances_ can occur in different [Curvesets](Manual#Curveset.md)
    * Any changes to a Curve will alter every apperance of that Curve (e.g., in all Curvesets that point to it)

  * Key functions in code: **`Curve.m`**
    * Basic input/output

### Curveset ###
  * **Goal**: _Store a **set** of [Curves](Manual#Curve.md) (each from the same NMR probe/assignment) which all share a single pair of chemical shift differences (Δω<sub>H</sub> and Δω<sub>X</sub>)_

  * Properties
    * **name**: _Name of Curveset_
    * **index**: _Residue number_
    * **atom**: _Name of atom (N, H\alpha, C\delta\_1, etc.)_
    * **residue**: _Name of residue (Ile, Leu, Arg, etc.)_

  * Curvesets contain _pointers_ to Curves (selected from Datasets)
    * **Nc**: _Number of Curves in the Curveset_
    * Pointers to [Curves](Manual#Curve.md) which hold the actual data and experimental conditions

  * Each Curveset only appears **once** (unlike Curves)

  * Key functions in code: **`Curveset.m`**
    * Basic input/output

### Group ###
  * **Goal**: _Store a **Group** of [Curvesets](Manual#Curveset.md) (each from different NMR probes/assignments) which all share a single set of exchange kinetics (P<sub>A</sub> and k<sub>ex</sub> at each temperature), and store any [Fit Results](Manual#Fit_Result.md) for this Group_

  * Properties
    * **name**: _Name of Group_
    * **index**: _Index of the Group (for sorting; this may correspond to residue number)_

  * Storage of fitting results
    * **exhibitsExchange**: _This Group exhibits exchange (true/false)_
    * **bestFitIsOK**: _The best fit to this Group is OK (true/false)_
    * **Nf**: _Number of fit results_
    * **fitResults\_Grid**: _Array of FitResults for the grid search_
    * **fitResults**: _Array of FitResults for arbitrary fits (ex and no-ex)_
    * **fitResult\_NoEx**: _Fit result to no exchange model_
    * **fitResult\_Best**: _Best fit result out of all fits (ex and no-ex)_

  * Groups contain _pointers_ to [Curvesets](Manual#Curveset.md), each of which only appears once
  * Each Group points to a parent [Session](Manual#Session.md) which contains settings, etc.

  * Key functions in code: **`Group.m`**
    * **`delinearizePFmincon`**, De-linearize parameter array to matrix form for fitting
    * **`getData`**, Return data point (NATURAL UNITS) for the desired parameter, temperature, B<sub>0</sub>, and Quantum Coherence
    * **`gridSearch`**, Perform grid search to fit RD data with variety of initial conditions, and return updated fit\_results
    * **`updateFitParams`**, Identify the independent parameters and dependent scaling factors for the Group fit


### Fit Result ###
  * **Goal**: _Pefrorm a single fit to a Group of RD data, and store the results_

  * Storage of a single fit result
    * Name of fit result
    * Use of Arrhenius relation to constrain rate analysis
    * Initial conditions for fit parameters
    * Final values for fit parameters
    * Errors in fit parameters (from Monte Carlo)
    * Designation if each parameter is OK or not
    * [RateAnalysis](Manual#Rate_Analysis.md) structure for temperature-dependence

  * Key functions in code: **`FitResult.m`**
    * **`analyzeMe`**, Analyze the fitResult (usually called after fitMe()
    * **`calculateErrors`**, Estimate error in dispersion fit using Monte Carlo bootstrapping
    * **`fitMe`**, Fit the Group either to NOEXCHANGE or EXCHANGE model
    * **`setParamIsOK`**, Set the param\_isOK for the parameter name
    * **`simMe`**, Simulate the fit (no optimization)
    * **`setInitial_Kinetics_UnconstrainedRates`**, Set initial fitting conditions
    * **`setInitial_Kinetics_ConstrainedRates`**, Set initial fitting conditions
    * **`setInitial_Shifts`**, Set initial fitting conditions for Δω<sub>H</sub>, Δω<sub>X</sub>, and [R20](https://code.google.com/p/guardd/source/detail?r=20)

### Rate Analysis ###
  * **Goal**: _Store the results of a temperature-dependent analysis of the P<sub>A</sub> and k<sub>ex</sub>_

  * Storage of temperature-dependent parameters
    * All Arrhenius parameters
    * arrhenius\_isOK
    * All vant Hoff parameters
    * vantHoff\_isOK

  * Key functions in code: **`RateAnalyis.m`**
    * **`analyzeMe`**, Update kinetic quantities using P<sub>A</sub>(T) and k<sub>ex</sub>(T)
    * **`getArrheniusPlotA`**, Return X and Y vectors for the Arrhenius plots A (ln(kA) vs. 1/T (or ln(kB) vs 1/T))
    * **`getVantHoffPlot`**, Return X and Y vectors for van't Hoff plot (ln(K) vs 1/T)

### Session ###
  * **Goal**: _Store the program data and settings_

  * Store all [Datasets](Manual#Dataset.md)
  * Store all [Groups](Manual#Group.md)

  * Key functions in code: **`FitResult.m`**
    * **`generateGroups`**, Generate minimal set of NEW Groups to partition Curves via NMR probe (index/atom)
    * **`generateCurvesetsForGroup`**, Generate minimal set of NEW Curvesets to partition Curves via NMR probe (index/atom)
    * **`getPlotLabels`**, Return plot title and axis label for a given parameter name
    * **`getPlotSymbolAndColor`**,  Return plot symbol character ('o', 's', etc.) and colorRGB vector
    * **`loadDatasets`**, Load 1+ datasets using script file
    * **`sortGroups`**, Sort the Groups by index and name
    * **`convertUnits`**, Convert the parameter units for arbitrary parameter for natural or display units
    * **`getParamRequirements`**, Does the parameter need a particular Temp and/or B<sub>0</sub>?

## General use ##

### Acquire and prepare data ###
  * Acquire CPMG RD NMR spectra
    * Multiple temperatures, B<sub>0</sub> fields, SQ and/or MQ dispersion for either <sup>13</sup>C or <sup>15</sup>N sites
  * Extract peak intensities wtih NMRPipe [download](http://guardd.googlecode.com/files/Processing-RD--2008.07.07.zip)

### Analyze data using GUARDD ###

<a href='http://chemistry.osu.edu/~foster.281/guardd//manual/figure-flowchart-fitting/figure-flowchart-fitting.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd//manual/figure-flowchart-fitting/figure-flowchart-fitting.png' alt='[UNLOADED IMAGE]' width='300'> </img> </a>

  1. Load the data and execute the grid search on exchanging Groups
  1. For each Group, the grid search fit is selected, otherwise an individual fit is performed
  1. In YES to exchange, the current best fit is evaluated via χ<sup>2</sup> maps and rate analyses
    * If NO exchange, the `NoEx` fit is marked for subsequent analysis
  1. If fitted values can be optimized, the user supplies new initial conditions and re-evaluates the fit at (3)
  1. If fitted values cannot be optimized, the user designates which ones are valid/invalid, if any
  1. It is important that invalid parameters be designated as such, lest they be analyzed/displayed in subsequent output
  1. The user should enter text to describe the fitting result
    * Especially if there is work to do (e.g., new Grid Search, multi-Curveset fitting, remove noisy data)
  1. Once fits are optimized, errors are calculated using Monte Carlo bootstrapping and results are viewed
  1. New Groups can be generated to test global motions and/or to refine fit results


## GUARDD Graphical Interface ##

<a href='http://chemistry.osu.edu/~foster.281/guardd//manual/main-GUARDD-2011.07.13--01.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd//manual/main-GUARDD-2011.07.13--01.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

### GUARDD Input menu ###

#### Clear session ####
  * Clears the session, as if the program was just opened

#### Load session ####
  * Clears the current session
  * Loads a previously saved GUARDD session (a ".mat" MATLAB variables file)
  * This may take a relatively long time to load
    * 1 Mb file takes ~0.5 min
    * 10 Mb file takes ~5 min
  * Read about the Session file [here](FileFormats#Input/Output:_GUARDD_Session_file.md)

#### Settings ####
  * **Goal**: Change program settings here

<a href='http://chemistry.osu.edu/~foster.281/guardd//manual/manual-GUARDD-2011.06.16--settings.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd//manual/manual-GUARDD-2011.06.16--settings.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

  * Take special note of OUTPUT\_DEBUG flags, which are helpful to see program logic during execution
  * The items on this list are set in the code via `Session.param_info`

#### Data Manger ####
  * **Goal**: _Manage datasets, Curves, Curvesets, and Groups for analysis (input and basic output)_

<a href='http://chemistry.osu.edu/~foster.281/guardd//tutorial/tutorial-GUARDD-2011.06.17--04.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd//tutorial/tutorial-GUARDD-2011.06.17--04.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

<u>Menu items</u>*****Input...*****Script...*** Loads a script file [here](FileFormats#Input:_Script_file_to_load_data.md)
    ***Sequence file...*** Load a sequence file [here](FileFormats#Input:_Sequence_file.md)
  ***Dataset...*****Sort Curves (this dataset)**→ Curves sorted by `index` and `atom` are easier to browse
    ***Sort Curves (all datasets)*****Group...*****Sort Groups**→ Groups sorted by `index` and `name` are easier to browse
      * Code: `Session.sortGroups()`
    ***Generate from all data**→ Generate minimal set of NEW Groups to partition Curves via NMR probe (`index` and `atom`)
      * Each new Group contains one new Curveset containing all the Curves for that NMR probe
      * Code: `Session.generateGroups()`
    ***Generate from subsets of data**→ Same as above, except using Curves from only part of the dataset
      * This launches the**<u>Create Groups</u> dialog [here](Manual#Create_Groups.md)
      * Code: `Session.generateGroups()`
  * **Curveset...**
    * **Sort Curvesets (this Group)...** → Curvesets sorted by `index` and `name` are easier to browse
    * **Generate from all data...** → For the selected Group, generate minimal set of NEW Curvesets to partition Curves via NMR probe (`index` and `atom`)
      * This is the easiset way to generate a large Group (e.g., all Curves reporting same dynamic process)
      * From here, certain Curvesets and Curves can be removed, if desired
    * **Copy to Group...** → Copy the selected Curveset to another Group
      * This launches the <u>Select Group</u> dialog [here](Manual#Select_Group.md)
  * **Curve...**
    * (Nothing yet)
  * **Output...**
    * **Datasets...**
      * Writes a Dataset file [here](FileFormats#Output:_Datasets.md)
    * **Groups...**
      * Writes a Groups file [here](FileFormats#Output:_Groups.md)

<u>Panels and buttons</u>*** Each table contains editable information on the object
  ***Button: Save**→ Save changes made to the table
  ***Button: Revert**→ Discard changes made to the table
  ***Panel: Datasets*** Displays all the loaded datasets
    ***Button: Add dataset**→ Adds an empty Dataset to the list
      * This can be edited and Curves can be loaded manually using nlin.tab file [here](FileFormats#Input:_NMRPipe_nlin.tab_and_taufile.txt.md)
      * This is NOT the preferred method to load data (use script file instead, [here](FileFormats#Input:_Script_file_to_load_data.md))
    ***Button: Remove dataset**→ Removes the selected dataset from the list
  ***Panel: Curves in selected dataset*** Lists all the Curves and displays their properties
    ***Note**: Changing Curve properties here will propagate to all apperances of that Curve
    ***Button: Load Curve(s)**→ This is NOT the preferred method to load data (use script file instead, [here](FileFormats#Input:_Script_file_to_load_data.md))
    ***Button: Remove Curve**→ Removes the selected Curve from the Dataset (and ALL appearances of that Curve)
  ***Panel: Groups for fitting*** Lists all the Groups in the Session
    ***Button: New**→ Add an empty Group
      * Useful for creating custom Groups with desired Curvesets and Curves
    ***Button: Remove**→ Remove the selected Group
    ***Duplicate Group**→ Copy the Group and all Curvesets within
      * Useful for creating custom Groups (e.g., copy then add/remove Curvesets)
  ***Panel: Curvesets in selected Group*** Displays all the Curvesets in the selected Group
    ***Button: New**→ Add an empty Curveset to the selected Group
    ***Button: Remove**→ Remove the selected Curveset from the selected Group
    ***Button: Copy to Group**→ Copy the selected Curveset to another Group
      * This launches the**<u>Select Group</u> dialog [here](Manual#Select_Group.md)
  * **Panel: Curves in selected Curveset**
    * Displays all the Curves which are pointed to by the selected Curveset
    * **Note**: Changing Curve properties here will propagate to all apperances of that Curve
    * **Button: Add Curve** → Add the Curve that is selected from the Dataset (on the left)
    * **Button: Remove Curve** → Remove the appearance of this Curve from the Curveset (does NOT delete Curve from the dataset)

##### Create Groups #####
  * **Goal**: _Create a set of Groups using a subset of the data_
    * Helpful when only part of a large dataset is desired

<a href='http://chemistry.osu.edu/~foster.281/guardd//tutorial/tutorial-GUARDD-2011.06.17--03.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd//tutorial/tutorial-GUARDD-2011.06.17--03.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

  * Tutorial: Advanced Group creation [here](Tutorial#Create_a_multi-curveset,_multi-temperature_group.md)

##### Select Group #####
  * **Goal**: _Select a Group so that the selected Curveset can be copied to it_

<a href='http://chemistry.osu.edu/~foster.281/guardd//tutorial/tutorial-GUARDD-2011.06.17--13.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd//tutorial/tutorial-GUARDD-2011.06.17--13.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

  * Tutorial: Advanced Group creation  [here](Tutorial#Create_a_multi-curveset,_multi-temperature_group.md)

##### Tutorial Tasks #####
  * Tutorial: Load data [here](Tutorial#Load_data.md)
  * Tutorial: Basic Group creation [here](Tutorial#Create_groups_for_fitting.md)
  * Tutorial: Advanced Group creation (copy) [here](Tutorial#Create_a_multi-curveset,_multi-temperature_group.md)


#### RD Simulator ####
  * **Goal**: _Explore the nature of RD pheneomnea and create simulated Group data for planning experiments and edification_

<a href='http://chemistry.osu.edu/~foster.281/guardd//tutorial/tutorial-GUARDD-2011.06.17--Sim-03.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd//tutorial/tutorial-GUARDD-2011.06.17--Sim-03.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

  * Tutorial: Data simulation [here](Tutorial#Simulate_and_export_RD_data.md)
  * Key sections of code
    * **`SimulationCurve.m`** holds a single curve for GUARDD simulation
    * **`SimulationCurveset.m`** holds a single curvese for a GUARDD simulation
    * **`SimulationSession.m`** holds information for all simulations in GUARDD

##### Kinetic Simulator #####
  * **Goal**: _Explore the nature of two-state exchange pheneomnea for planning experiments and edification_

<a href='http://chemistry.osu.edu/~foster.281/guardd//tutorial/tutorial-GUARDD-2011.06.17--Sim-04.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd//tutorial/tutorial-GUARDD-2011.06.17--Sim-04.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

  * Tutorial: Kinetic simulation [here](Tutorial#Explore_temperature-dependence_of_exchange_kinetics.md)
  * See related: Kinetic simulation equations [here](Manual#Kinetic_simulator.md)


### GUARDD Analysis menu ###

#### Fit Dispersion ####
  * **Goal**: _Implement fits to Group, view results, log notes, and designate paramter validity_
  * **Goal**: _The "product" is a **best** fitResult, and its parameters which are OK (those are used/displayed in subsequent analyses)_
  * **Note**: Tasks completed in this  window are autoamatically committed (no need for an "OK" or "Save" command)

<a href='http://chemistry.osu.edu/~foster.281/guardd//tutorial/tutorial-GUARDD-2011.06.17--16.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd//tutorial/tutorial-GUARDD-2011.06.17--16.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

  * This window contains six panels for fitting tasks
  * **Panel: (1a) Procedure**
    * Invividual → Specify one set of initial conditions for one simulation or optimization
    * Grid search → Specify a range of initial conditiosn for many simulations or optimizations, read [here](Manual#Grid_search.md)
  * **Panel: (1b) Task**
    * Optimize fit → Starting at the initial conditions, iteratively alter parameter to minimize the χ<sup>2</sup> for the Group, read [here](Manual#Fitting_data.md)
    * Simulate → Simulate the iniital conditoins for the fit
      * Useful for seeing what the initial conditions look like
  * **Checkbox**: Use Arrhenius → Use Arrhenius relation with ΔH and E<sub>AB</sub> for temperature-dependence of k<sub>ex</sub> and P<sub>A</sub> [link](Manual#Example_parameter_assignment.md)
  * **Button**: Go! → Initiate task

  * **Panel: (2) Set INITIAL CONDITIONS**
    * Note: The initial value of R<sub>2</sub><sup>0</sup> for each Curve is set to Min(R<sub>2</sub><sup>Eff</sup>) for that Curve
    * This panel operates in (Individual) or (Grid Search) mode, determined by Panel (1a)
    * **(Individual)**
      * **Table: Group parameters** → The kinetic parameters apply to the entire Group
      * **Table: Curveset parameter** → The structural parameter apply to each Curveset
      * **Table: Data and initial conditions for each Curve (read-only)** → Summary of dataset and its initial fit conditions
    * **(Grid Search)**
      * **Table: Grid search** → Limits of each dimension in grid earch, read [here](Manual#Grid_search.md)

  * **Panel: (3) SELECT fit and view results**
    * **List** → Select one of the available fits
      * The fit name is automatically generated from 5 features
      1. `FIT` vs `SIM`: Designates whether the fitResult is for an optimization (FIT) or simulation (SIM)
      1. `-1` vs `-G`: Designates whether the fitResult is from an individual fit (-1) or from a grid search (-G)
      1. `[--]` vs `[CR]`: Designates whether the Arrhenius "constrain rates" option is off (--) or on (CR)
      1. `Chi2=###`: Designates the value of χ<sup>2</sup> for the Group (lower value is better fit)
      1. `[Date-Time]`: Designates the date and time at which the fitResult was created
    * **Button: Set best fit** → Designate the current fit as the best one, which is displayed in all appearances of Group parameters
    * **Button: Delete fit** → Remove the selected fit from the list
    * **Button: Rename fit** → Rename the currently selected fit
      * Useful for when certain constraints are used, or if it is selected from a grid [here](Manual#Select_fit_from_grid_search.md)
    * **Button: Calc Errors** → Initiate Monte Carlo error analysis on the Group [here](Manual#Monte_Carlo_error_estimation.md)
    * **Button: Set as ICs** → Set the current fitResult as the initial conditions for the next fit
      * Useful for altering fit conditions during user-directed optimization

  * **Panel: (4) View data and SELECTED fit**
    * (Self explanatory)

  * **Panel: (5) Log notes for Group**
    * These can be displayed in the <u>Notes</u> window [here](Manual#Notes.md)
    * These can be exported in the <u>Results Table</u> window [here](Manual#Display_results_table.md)

  * **Panel: (6) Designate if SELECTED fit is OK**
    * To display/analyze a given best fit parameter, the best fit must be OK AND the particular parameter must be OK
    * **Checkbox: Exchange**: The Group exhibits exchange (true/false)
    * **Checkbox: Best fit is OK**: The Group fit is OK, which is required for subsequent display of fit results (true/false)
    * **Button: Set best fit** → Designate the current fit as the best one, which is displayed in all appearances of Group parameters
    * **Button: All** → Mark all the parameters as OK
    * **Button: R** → Make only [R20](https://code.google.com/p/guardd/source/detail?r=20) and Rex as OK
    * **Button: None** → Mark all of the parameters as NOT OK


  * Tutorial: Basic fitting [here](Tutorial#Fit_simple_group_manually.md)
  * Tutorial: Multi-temperature fitting [here](Tutorial#Fit_multi-temperature_group_manually.md)
  * Tutorial: Multi-temperature + multi-Curveset fitting [here](Tutorial#Fit_a_multi-curveset,_multi-temperature_group.md)
  * See related: fitting equations [here](Manual#Carver-Richards_Jones_for_MQ_disperstions.md)
  * See related: minimizing χ<sup>2</sup> [here](Manual#Fitting_data.md)


#### Batch Task ####
  * **Goal**: _Queue up lengthy computations for sequential processing_

<a href='http://chemistry.osu.edu/~foster.281/guardd//tutorial/tutorial-GUARDD-2011.06.17--18.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd//tutorial/tutorial-GUARDD-2011.06.17--18.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

  * Tutorial: set up a batch task [here](Tutorial#Perform_batch_task.md)

#### Notes ####
  * **Goal**: _Document notes on Session, and read notes on all Groups_

<a href='http://chemistry.osu.edu/~foster.281/guardd//tutorial/tutorial-GUARDD-2011.06.17--19.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd//tutorial/tutorial-GUARDD-2011.06.17--19.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

  * Group notes can be modified in the <u>Fit RD</u> window [here](Manual#Fit_Dispersion.md)
  * Group notes can be read and exported to plain-text in the <u>Results Table</u> [here](Manual#Display_results_table.md)
  * Tutorial: View notes [here](Tutorial#Document_notes_for_organization.md)


#### Debug ####
  * Runs the code in the function `GUARDD.m/menu_run_code_Callback()`, used for debugging
  * Helpful for debugging features of GUARDD


### GUARDD Output menu ###

#### Save session ####
  * **Goal**: _Write [Session](Manual#Session.md) to MATLAB file to save data and program state_
  * Read about Session file [here](FileFormats#Input/Output:_GUARDD_Session_file.md)

#### Display Dispersion ####
  * **Goal**: _Display RD Curves in a Group to assess fit quality (via residuals) and prepare figures for dissemination_

<a href='http://chemistry.osu.edu/~foster.281/guardd//tutorial/tutorial-GUARDD-2011.06.17--11.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd//tutorial/tutorial-GUARDD-2011.06.17--11.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

<a href='http://chemistry.osu.edu/~foster.281/guardd//tutorial/tutorial-GUARDD-2011.06.17--12.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd//tutorial/tutorial-GUARDD-2011.06.17--12.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

  * Tutorial: display the dispersion [here](Tutorial#View_fits_to_RD_data.md)

#### Display Chi2 Map ####
  * **Goal**: _Browse the results of a grid search or MC error analysis to assess and refine fit_

  * **Key info on features of chi2 maps**
    * The χ<sup>2</sup> map is a hypersurface with amplitude χ<sup>2</sup> and one dimension for each independent fitting parameter
      * E.g., 14 parameters yields a 14D hypersurface
    * Lower value of χ<sup>2</sup> indicates a more precise fit to the data
    * The goal is to obtain paramters at the **global** minimum of χ<sup>2</sup>
    * Issue: the nonlinear nature of RD yields a "rough" χ<sup>2</sup> map that can trap the fitting routine in local minima

<a href='http://chemistry.osu.edu/~foster.281/guardd//manual/figure-chi2_maps/figure-chi2_maps.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd//manual/figure-chi2_maps/figure-chi2_maps.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

_(Figure above) The response of χ<sup>2</sup> to just one parameter, k<sub>ex</sub>, produces a 2D slice through the hypersurface to illustrate four commonly encountered shapes that pose distinct challenges in obtaining an accurate fit._


  * **Goal**: _Interpret the **Grid Search** results the_<u>Chi2 Map</u> window_1. Each subplot shows a single parameter on the X-axis, and its different values in different fits
    1. Each **black point** corresponds to ONE optimized fit result
      1. There are 60 fits in this example (hence 60 points in each subplot), each of which started from a different location in parameter space
      1. Those initial locations can be displayed by setting **Results to display**: Initial
    1. The **red circle** designates the currently selected fit result
    1. The **blue square** designates the best fit from the grid search
    1. Clicking **Pick grid fit** will allow selection of any of the grid fits shown
      1. The **green diamond** designates the currently selected fit from the displayed grid list
      1. Any of these can be added to the list of fits, if desired_

<a href='http://chemistry.osu.edu/~foster.281/guardd//tutorial/tutorial-GUARDD-2011.06.17--20.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd//tutorial/tutorial-GUARDD-2011.06.17--20.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>


  * Initial conditions sampled from the grid search are uniformly distributed across paramter values
    * This is shown by selecting **Initial** conditions and **Histogram** mode

<a href='http://chemistry.osu.edu/~foster.281/guardd//tutorial/tutorial-GUARDD-2011.06.17--30.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd//tutorial/tutorial-GUARDD-2011.06.17--30.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

  * Tutorial: View grid search results for a good fit [here](Tutorial#View_Grid_Search_Chi2_Map_for_good_fit.md)
  * Tutorial: View grid search results for a bad fit [here](Tutorial#View_Grid_Search_Chi2_Map_for_fit_with_uknown_parameters.md)
  * See related: grid search [here](Manual#Grid_search.md)


##### Select fit from grid search #####
  * **Goal**: _To examine a particular fit from the grid search that is not the min(χ<sup>2</sup>), it must be selected from the list_
  * This is helpful for checking another well in χ<sup>2</sup> space (e.g., [Figure\_C](http://chemistry.osu.edu/~foster.281/guardd//manual/figure-chi2_maps/figure-chi2_maps.png))

<a href='http://chemistry.osu.edu/~foster.281/guardd//tutorial/tutorial-GUARDD-2011.06.17--31.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd//tutorial/tutorial-GUARDD-2011.06.17--31.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

  * Tutorial: select fit from grid search [here](Tutorial#View_Grid_Search_Chi2_Map_for_fit_with_uknown_parameters.md)


##### Display Monte Carlo Errors #####
  * **Key info on Monte Carlo analysis**
    * The goal of MC analysis is to generate and fit many **synthetic** datasets which differ from one another by an amount related to the goodness of fit to the original data
    * Each synthetic dataset will have a different set of optimal fit values (e.g., P<sub>A</sub>, k<sub>ex</sub>)
    * The distribution of fitted values reflects the degree to which the original data define its **own** optimal values
    * Example: A worse optimal fit to the original data yields **more different** MC datasets and therefore **more different** optimal parameter values


<a href='http://chemistry.osu.edu/~foster.281/guardd//manual/figure-monte_carlo/figure-monte_carlo.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd//manual/figure-monte_carlo/figure-monte_carlo.png' alt='[UNLOADED IMAGE]' width='300'> </img> </a>

_(Figure above) The example data contains 5 observations (black), 5 residuals (red), and 10 synthetic datasets (green squares), each with their own fit (green dotted lines) and set of optimized parameter values_

  * **Goal**: _Interpret the **MC Errors** results the_<u>Chi2 Map</u> window_1. Each subplot shows a single parameter on the X-axis, and its different values in different fits
    1. Each **black point** corresponds to ONE optimized fit result to a synthetic MC dataset
      1. There are 100 fits in this example (hence 100 points in each subplot), each of which corresponds to a synthetic MC dataset
      1. The initial conditions to each fit are given by the best fit to the original data (see **Results to display**: Initial)
    1. The **red circle** designates the best fit to the original data
    1. Set **Display Mode**: Histogram
    1. The gray lines show the hypothetical distributions reflecting "errors" in the data
      1. The **mean** of each distribution is from the best fit value to the original data
      1. The **standard deviation** of each distribution is the standard deviation from the distribution of MC fitted values
      1. Each deviation is reported as the "error" in each fitted parameter (shown in brackets)
    1. **Note**: it is usually best to use a **Top%**=100% for MC errors
      * Sometimes anomalous fits yield very large χ<sup>2</sup>, and can be discarded, but this is rare_

<a href='http://chemistry.osu.edu/~foster.281/guardd//tutorial/tutorial-GUARDD-2011.06.17--22.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd//tutorial/tutorial-GUARDD-2011.06.17--22.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

<a href='http://chemistry.osu.edu/~foster.281/guardd//tutorial/tutorial-GUARDD-2011.06.17--23.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd//tutorial/tutorial-GUARDD-2011.06.17--23.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>


  * Tutorial: View Monte Carlo results for a good fit [here](Tutorial#View_Monte_Carlo_Errors_Chi2_Map_for_good_fit.md)
  * Tutorial: View Monte Carlo results for a bad fit [here](Tutorial#View_Monte_Carlo_Errors_Chi2_Map_for_fit_with_uknown_parameters.md)
  * See related: Monte Carlo error estimation [here](Manual#Monte_Carlo_error_estimation.md)


#### Display rates ####
  * **Goal**: _Display results of rate analysis using Arrhenius and vant Hoff relations_

<a href='http://chemistry.osu.edu/~foster.281/guardd//tutorial/tutorial-GUARDD-2011.06.17--10.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd//tutorial/tutorial-GUARDD-2011.06.17--10.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

  * Tutorial: view the rates [here](Tutorial#Examine_rate_analysis_(vant_Hoff_and_Arrhenius).md)
  * See related: Arrhenius equations [here](Manual#Arrhenius:_Determining_activation_energy.md)
  * See related: vant Hoff equations [here](Manual#vant_Hoff:_Determining_enthalpy.md)

#### Display group results ####
  * **Goal**: _Visually organize fitting results to seek the nature of molecular motions_

  * **Button: New** → Add new empty DisplayCluster to hold Groups for displaying results
  * **Panel: All Groups** → Lists all Groups available to add/remove to/from the selected DisplayCluster
  * **Button: Make selection** → Deprecated function to intelligently select Groups from GUARDD
  * **Panel: Groups in DisplayCluster** → Lists all Groups in the selected DisplayCluster (can be removed)

  * **Panel: Display Settings**
    * **Table: Subplots** → Used to create a set of subplots for the display
    * **Plot number** → Select the subplot number (From 1 to Nrow\*Ncol)
    * **Type** → Select plot type (Custom will allow for any parameters to be displayed, others are pre-arranged)
    * **Y-Axis** → Select what to be displayed on Y-axis (non-histogram only)}
    * **X-Axis** → Select what to be displayed on the X-axis
    * **Table: Plot limits** → Set NaN for auto-limits, or type in your own and use linear or log scale (applies to all subplots, sorry!)
    * **Checkbox: Show Histogram** → Shows the histogram (requires only X-axis values)

  * Notes
    * Some paramters plot one point per Group (e.g., P<sub>A</sub> or k<sub>ex</sub>(37C))
    * Some parameter plot one point per Curveset (e.g., |Δω<sub>X</sub>|) and hence multiple points per Group
    * Some paramters **could** plot one point per Curve (e.g., R<sub>ex</sub>) but the FIRST Curve is selected by default
    * Otherwise there would be too many points on the plot


<a href='http://chemistry.osu.edu/~foster.281/guardd//manual/GUARDD-Groups-2011.06.23--05.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd//manual/GUARDD-Groups-2011.06.23--05.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

  * Tutorial: display Group results [here](Tutorial#View_results_in_display_cluster.md)
  * Key sections of code
    * **`DisplayCluster.m`** Holds information on the name, color, and Groups for display
    * **`ParamDisplay.m`** Holds information for display of the parameters (subplots, X and Y content)

#### Display results table ####

  * **Goal**: _Produce table of results for easy browsing_

  * Notes
    * Table is dynamically generated based on the user's selection criteria from an arbitrary set of RD parameters and Curves
      * E.g., only P<sub>A</sub> and k<sub>ex</sub> at one temperature, instead of all RD parameters for all Curves for all Groups
    * This customized table can be exported to plain-text for publication or external analysis

  * **Button: Export to CSV** → creates two plain-text files (two-column format and one-column format)
    * One is easier for plotting in external programs
    * Another is easier for preparing a publication quality table

<a href='http://chemistry.osu.edu/~foster.281/guardd//tutorial/tutorial-GUARDD-2011.06.17--25.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd//tutorial/tutorial-GUARDD-2011.06.17--25.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

  * Tutorial: display results table [here](Tutorial#View_results_in_table.md)

## Tips for optimal use ##

### Program tips ###
  * Save frequently
  * Drawing windows is relatively slow
    * Use the main display window to only update displays of interest
  * Use a CPU monitor application to see when GUARDD is processing results (e.g., fitting, drawing windows, exporting files)
  * Do not make other changes when performing grid search or error estimates
    * Data can be viewed but not altered
    * This is because data structures are stored before the batch run (or a single grid search or single error estimation) then re-saved upon completion of a batch step or single grid search or single error estimation

### Fitting tips ###
  * Usually dispersions with larger R<sub>ex</sub> have a more well-defined solution
    * Small R<sub>ex</sub> and/or noisy data are usually accompanied by challenges in fitting

  * If unsure about the fit, then don't interpret fitted parameters quantitatively
    * Additional inaccurate information can obscure proper interpretation of dynamics
    * A poor fit to the two-state model may indicate more complex exchange, such as three-state
    * Note this residue, and consider other fitting equations or more complex exchange models (unfortunately, not available in GUARDD v.2011.09.11)

  * Three solutions for ill-defined fits
    1. Select one of the fits, but mark the ill-defined parameters as “Not OK,”  thus preventing their mis-interpretation in subsequent analyses.
    1. Alter the Group and re-fit. One may remove noisy Curves and/or add additional Curvesets to help constrain the values of k<sub>ex</sub> and P<sub>A</sub>.
    1. Acquire more data and re-fit the new Group. The RD Simulator can help determine optimal conditions of temperature, magnetic field strength, and/or quantum coherence for efficient use of spectrometer time, [here](Manual#RD_Simulator.md)

  * Check for outliers in fitted data
    * Check sequence mapping for outliers
    * Check χ2 and fits for those outliers
    * What type of exchange do proximal residues exhibit?

  * Make sure fits which show no exchange have “NoEx” model selected as best

  * Check neighboring residues
    * Check dispersions for neighboring residues to get an idea of the type of motions one may expect in that region of the structure
    * If there is concerted motion, then k<sub>ex</sub> and Pa (and their temperature-dependence Ea(A → B), Ea (B → A), dH, dS) will be the same (or close) for residues close in structure
    * Note: There is no requirement that neighboring residues be similar though

  * k<sub>ex</sub> is most sensitive fitting parameter
    * Use the largest number of grid search steps
    * k<sub>ex</sub> should increase with temperature (e.g., Arrhenius)
    * P<sub>A</sub> may increase (ΔH < 0), decrease (ΔH > 0) or remain constant (ΔH=0) with temperature

### GUARDD approach to fast exchange and PhiEx ###
  * **Issue**: _In fast exchange (k<sub>ex</sub> >> Δν = Δω / (2π)), the quantities P<sub>A</sub>P<sub>B</sub> and Δω are correlated, and therefore cannot be independently defined_

  * **Solution**: sometimes although neither quantity can be defined independently, the quantity Φ<sub>ex</sub><sup>X</sup> = P<sub>A</sub>P<sub>B</sub>Δω<sub>X</sub><sup>2</sup> = P<sub>A</sub>(1-P<sub>A</sub>)Δω<sub>X</sub><sup>2</sup> , where X refers to the X nucleus, can be well-defined (Luz, 1963; Ishima, 1999)

  * Examine Φ<sub>ex</sub><sup>X</sup> in the <u>Chi2 Map</u> window to help assess the sensitivity of the final fit to either initial conditions (via grid search) or to noise in the data (via Monte Carlo error estimation)
    * In some cases, the parameters P<sub>A</sub> and Δω<sub>X</sub> are relatively sensitive to initial conditions (wide χ<sup>2</sup> maps), whereas Φ<sub>ex</sub> is relatively less sensitive (more narrow χ<sup>2</sup> map), which may indicate that it is reasonable to interpret Φ<sub>ex</sub>, but not P<sub>A</sub>.

<a href='http://chemistry.osu.edu/~foster.281/guardd//manual/GUARDD-Update-2011.09.13--01.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd//manual/GUARDD-Update-2011.09.13--01.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

  * The <u>Chi2 Map</u> window displays a correlation plot of the optimized values of Δω<sub>X</sub><sup>2</sup> and P<sub>A</sub>P<sub>B</sub>. In fast exchange, a strong correlation between these parameters yields a line of points, facilitating detection of fast exchange.

<a href='http://chemistry.osu.edu/~foster.281/guardd//manual/GUARDD-Update-2011.09.06--02.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd//manual/GUARDD-Update-2011.09.06--02.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

  * Check for fast exchange via the Fit RD window by comparing values of k<sub>ex</sub> and Δω as well as the exchange parameter α, which indicates fast exchange in the range 1.0 to 2.0 (Millet et al., 2000).

## Limitations ##
  * Liabilities of linkage to MATLAB
    1. GUARDD is slower than if it were coded using C or Python, for example
      1. MATLAB is an interpreted language
      1. Graphical interface uses Java
      1. Drawing the display, while reading or writing large session files, or while fitting data
    1. Malfunctions in MATLAB may hinder functionality of GUARDD
      1. However, enhancements to MATLAB may imbue enhancements to GUARDD
    1. User must have access to MATLAB (i.e., GUARDD is not a standalone program)
      1. However, MATLAB is a convenient cross-platform solution for dissemination of software
    1. Cannot be run using Octave, which can run many other MATLAB programs [link](http://www.gnu.org/software/octave/)
      1. Octave does not support the graphical user interface that is a key feature of GUARDD [link](http://www.gnu.org/software/octave/FAQ.html#MATLAB-compatibility)
      1. For what its worth, Octave supports a distinct GUI library called “Zenity” [link](http://octave.sourceforge.net/zenity/)

  1. Limitations of GUARDD functionality
    1. Exchange model is restricted to two-state using the all-timescales MQ Carver-Richards-Jones formulation
      1. No simplifications assuming skewed populations (P<sub>B</sub> < P<sub>A</sub>) (Ishima, 1999)
      1. No simplifications assuming fast-exchange (k<sub>ex</sub> > Δν)
    1. No three-site exchange
    1. No ZQ or DQ coherences
    1. No pressure-dependence of RD
    1. No Anti-TROSY/TROSY analysis
    1. No temperature-dependence via transition state theory
    1. No error analysis options: jacknife, covariance matrix method


## Feedback, Suggestions, Bugs ##
  * Please report bugs, suggestions, etc. in the Issues page [here](http://code.google.com/p/guardd/issues/list)


## Computational procedures ##

### Convert NMR signal intensity to relaxation rate ###
  * **Goal**: Given NMR signal intensites, generate a relatxation Curve

  * **Input**
    1. I(ν<sub>CPMG</sub>) = signal intensity in the 2D spectrum acquired with refocusing frequency ν<sub>CPMG</sub>
    1. I<sub>0</sub> = reference signal intensity obtained in the spectrum with no refocusing block
    1. T<sub>CPMG</sub> = duration of the refocusing block
  * **Output**
    1. R<sub>2</sub><sup>Eff</sup>
    1. Errors in intensities σ(R<sub>2</sub><sup>Eff</sup>) are estimated via standard deviation from repeat measures of I(ν<sub>CPMG</sub>)

> R<sub>2</sub><sup>Eff</sup> = -ln( I(ν<sub>CPMG</sub>)/I<sub>0</sub>) / T<sub>CPMG</sub>

### Converting ppm to rad/s ###
  * **Goal**: Obtain rad/s quantity for chemical shift difference using ppm value
    * **Note** rad/s is requried for trigonometric functions, like tangent
    * **Note**: Hz = /s is useful for direct comparison to k<sub>ex</sub> (also in /s) in determining exchange timescale

  * **Input**
    * ω<sub>X</sub> (rad/s)
    * γ<sub>X</sub> (from nucleus identity)
    * B<sub>0</sub>
  * **Output**
    * ω<sub>X</sub><sup>(rad/s)</sup> = 2πB<sub>0</sub>γ<sub>X</sub>ω<sub>X</sub><sup>(ppm)</sup>
    * ν<sub>X</sub><sup>(Hz)</sup> = B<sub>0</sub>γ<sub>X</sub>ω<sub>X</sub><sup>(ppm)</sup>

### Carver-Richards Jones for MQ disperstions ###
  * **Goal**: Obtain dispersion Curve R<sub>2</sub><sup>Eff</sup> as a function of ν<sub>CPMG</sub> given a set of 5 parameters

  * **Input**
    1. Δω<sub>H</sub>
    1. Δω<sub>X</sub>
    1. P<sub>A</sub>
    1. k<sub>ex</sub>
    1. R<sub>2</sub><sup>0</sup>
    1. ν<sub>CPMG</sub>
  * **Process**
    1. δ = 1 / (4ν<sub>CPMG</sub>)
    1. n = T<sub>CPMG</sub>ν<sub>CPMG</sub>
    1. Note: MQ simplifies to SQ if Δω<sub>H</sub> = 0
    1. (See equations below)
  * **Output**
    1. R<sub>2</sub><sup>Eff</sup>
  * **Location in code**
    * `chi2_MQRD_CRJ_group.m`
    * `chi2_MQRD_CRJ.m`
  * **Reference**
    * Korzhnev (2004)

<img src='http://chemistry.osu.edu/~foster.281/guardd//manual/formulae/formula-MQ_RD-Korzhnev-01.png' alt='[UNLOADED IMAGE]'> </img>

<img src='http://chemistry.osu.edu/~foster.281/guardd//manual/formulae/formula-MQ_RD-Korzhnev-02.png' alt='[UNLOADED IMAGE]'> </img>

<img src='http://chemistry.osu.edu/~foster.281/guardd//manual/formulae/formula-MQ_RD-Korzhnev-03.png' alt='[UNLOADED IMAGE]'> </img>

<img src='http://chemistry.osu.edu/~foster.281/guardd//manual/formulae/formula-MQ_RD-Korzhnev-04.png' alt='[UNLOADED IMAGE]'> </img>

<img src='http://chemistry.osu.edu/~foster.281/guardd//manual/formulae/formula-MQ_RD-Korzhnev-05.png' alt='[UNLOADED IMAGE]'> </img>

<img src='http://chemistry.osu.edu/~foster.281/guardd//manual/formulae/formula-MQ_RD-Korzhnev-06.png' alt='[UNLOADED IMAGE]'> </img>

<img src='http://chemistry.osu.edu/~foster.281/guardd//manual/formulae/formula-MQ_RD-Korzhnev-07.png' alt='[UNLOADED IMAGE]'> </img>

<img src='http://chemistry.osu.edu/~foster.281/guardd//manual/formulae/formula-MQ_RD-Korzhnev-08.png' alt='[UNLOADED IMAGE]'> </img>

<img src='http://chemistry.osu.edu/~foster.281/guardd//manual/formulae/formula-MQ_RD-Korzhnev-09.png' alt='[UNLOADED IMAGE]'> </img>

<img src='http://chemistry.osu.edu/~foster.281/guardd//manual/formulae/formula-MQ_RD-Korzhnev-10.png' alt='[UNLOADED IMAGE]'> </img>


### Fitting data ###
  * **Goal**: _Obtain a set of parameters that accurately describe RD Curves in the Group_
  * **Goal**: _Minimize the sum of squares target function_

  * **Input**
    1. R<sub>2Eff</sub><sup>Obs</sup> = RD Curve data points
    1. σ(R<sub>2Eff</sub><sup>Obs</sup>) = Errors in RD Curve data points
    1. Curve condition: B<sub>0</sub>
    1. Curve condition: Temperature
    1. Curve condition: QC
    1. Curve condition: <sup>A</sup>X
    1. Curve condition: T<sub>CPMG</sub>
    1. Fitting parameters: **p**
      1. P<sub>A</sub> and k<sub>ex</sub> for each temperature
      1. |Δω<sub>H</sub>| and |Δω<sub>X</sub>| for each Curveset
      1. R<sub>2</sub><sup>0</sup> for each Curve
  * **Process**
    1. MATLAB fmincon iteratively alters the fitting parameters **p** to minimize the target function χ<sup>2</sup>
    1. R<sub>2</sub><sup>Calc</sup> = calculated point using the Curve conditions and the independent fitting parameters **p** for the Group
    1. χ<sup>2</sup> becomes smaller as the Curve fit more closely matches the observed data
  * **Output**
    1. χ<sup>2</sup>
  * **Location in code**
    * `FitResult.fitMe`
  * **References**
    * MATLAB `fmincon` [link](http://www.mathworks.com/help/toolbox/optim/ug/fmincon.html)
    * MATLAB interior point algorithm [link](http://www.mathworks.com/help/toolbox/optim/ug/brnoxzl.html#brnpd5f)
    * Bevington (2003)
    * Motulsky (2003)

<img src='http://chemistry.osu.edu/~foster.281/guardd//manual/formulae/formula-chi2_target.png' alt='[UNLOADED IMAGE]'> </img>


### Exchange broadening ###
  * **Goal**: _Estimate exchange broadening R<sub>ex</sub> (height of the dispersion Curve) using the fitted RD Curve_

  * **Input**
    1. R<sub>2Eff</sub><sup>Calc</sup> = RD Curve data points
    1. σ(R<sub>2Eff</sub><sup>Obs</sup>) = Errors in RD Curve data points
    1. Curve condition: B<sub>0</sub>
    1. Curve condition: Temperature
    1. Curve condition: QC
    1. Curve condition: <sup>A</sup>X
    1. Curve condition: T<sub>CPMG</sub>
    1. Fitting parameters: **p**
      1. P<sub>A</sub> and k<sub>ex</sub> for each temperature
      1. |Δω<sub>H</sub>| and |Δω<sub>X</sub>| for each Curveset
      1. R<sub>2</sub><sup>0</sup> for each Curve
  * **Process**
    1. Sometimes evaluation at 0 Hz is not valid, therefore try 1 Hz, then 2 Hz, ...
      1. Try to use ν<sub>CPMG</sub> values as close to 0 and infinity as possible
  * **Output**
    1. R<sub>ex</sub>
  * **Location in code**
    * `FitResult.analyzeMe()`
    * `calculate_Rex.m`

> R<sub>ex</sub> ~ R<sub>2Eff</sub><sup>Fit</sup>(ν<sub>CPMG</sub>~0 Hz) - R<sub>2Eff</sub><sup>Fit</sup>(ν<sub>CPMG</sub>~10<sup>4</sup> Hz)

### Exchange timescale alpha ###
  * **Goal**: _Estimate scaling factor α for time regime of chemical exchange_

  * **Input**
    1. R<sub>ex</sub> at at least two field strengths
    1. Δω at the same field strengths
  * **Output**
    1. α
      * 0 <= α < 1	_Slow exchange_
      * α = 1 		_Intermediate exchange_
      * 1 < α <= 2	_Fast exchange_
  * **Location in code**
    * `FitResult.analyzeMe()`
    * `calculate_alpha.m`
  * **Reference**
    * Millet, et al. (2000)

> α = d( ln(R<sub>ex</sub>) ) / d( ln(Δω) )

### Exchange quantity PhiEx ###
  * **Goal**: _Calculate quantity Φ<sub>ex</sub> that appears in fast-exchange approximation to RD equations_
    * Sometimes this quantity is well-defined despite correlated/ill-defined P<sub>A</sub> and Δω

  * **Input**
    1. P<sub>A</sub>
    1. Δω<sub>X</sub> where X is the X nucleus
  * **Output**
    1. Φ<sub>ex</sub><sup>X</sup> (Hz<sup>2</sup>)
  * **Location in code**
    * `FitResult.analyzeMe()`
  * **Reference**
    * Luz & Meiboom (1963)
    * Ishima & Torchia (1999)

> Φ<sub>ex</sub><sup>X</sup> = P<sub>A</sub>P<sub>B</sub>Δω<sub>X</sub><sup>2</sup> = P<sub>A</sub>(1-P<sub>A</sub>)Δω<sub>X</sub><sup>2</sup>


### Arrhenius: Determining activation energy ###
  * **Goal**: Obtain activation energy and pre-exponential rate to characterize temperature-dependence of rate

  * **Input**
    1. P<sub>A</sub> at 2+ temperatures
    1. k<sub>ex</sub> at the same temperatures
  * **Process**
    1. R = gas constant
    1. T = absolute temperature
    1. k = k<sub>A</sub> = (1-P<sub>A</sub>)k<sub>ex</sub> (or k<sub>B</sub> = P<sub>A</sub>k<sub>ex</sub>) = kinetic rate of exchange from A→B (or B→A)
    1. Errors from MATLAB's fit routine (provided data at more than two temperatures), or from propagation of relative error from the fitting variables (when limited to data at only two temperatures).
  * **Output**
    1. P = P<sub>AB</sub> (or P = P<sub>BA</sub>) Pre-exponential rate, the exchange rate from A→B (or B→A) at infinite temperature
    1. E = E<sub>AB</sub> (or E = E<sub>BA</sub>) = Activation energy (≈ enthalpy) required to exchange from A→B (or B→A)
  * **Location in code**
    * `RateAnalysis.analyzeMe`
  * **Reference**
    * Winzor & Jackson (2006)

<img src='http://chemistry.osu.edu/~foster.281/guardd//manual/formulae/formula-arrhenius.png' alt='[UNLOADED IMAGE]'> </img>


### vant Hoff: Determining enthalpy ###
  * **Goal**: Obtain exchange enthalpy and entropy to characterize temperature-dependence of population

  * **Input**
    1. P<sub>A</sub> at 2+ temperatures
  * **Process**
    1. R = gas constant
    1. T = absolute temperature
    1. K = (1-P<sub>A</sub>) / P<sub>A</sub> = k<sub>A</sub> / k<sub>B</sub> = equilibrium constant for exchange
    1. Errors from MATLAB's fit routine (provided data at more than two temperatures), or from propagation of relative error from the fitting variables (when limited to data at only two temperatures).
  * **Output**
    1. ΔS = system entropy change from A→B
    1. ΔH = system enthalpy change from A→B
  * **Note**: Entropy is unreliable since it is highly sensitive to relatively noisy input data
  * **Location in code**
    * `RateAnalysis.analyzeMe`
  * **Reference**
    * Winzor & Jackson (2006)

<img src='http://chemistry.osu.edu/~foster.281/guardd//manual/formulae/formula-vanthoff.png' alt='[UNLOADED IMAGE]'> </img>

### Kinetic simulator ###
  * **Goal**: Itemizes all kinetic parameters of interest for two-state exchange, given minimal input required

  * **Input**
    1. ΔH
    1. E<sub>AB</sub>
    1. k<sub>ex</sub><sup>0</sup> = k<sub>ex</sub>(T<sub>0</sub>)
    1. P<sub>A</sub><sup>0</sup> = P<sub>A</sub>(T<sub>0</sub>)
    1. T<sub>0</sub> is an arbitrary temperature
  * **Process**
    1. R = gas constant
    1. T = absolute temperature
    1. (See below)
  * **Output**
    1. ΔH
    1. ΔS
    1. E<sub>AB</sub>
    1. P<sub>AB</sub>
    1. E<sub>BA</sub>
    1. P<sub>BA</sub>
    1. k<sub>ex</sub>(T)
    1. P<sub>A</sub>(T)
    1. k<sub>A</sub>(T)
    1. k<sub>B</sub>(T)
    1. T is an arbitrary temperature
  * **Location in code**
    * `SimulationCurveset.setKineticSpecs`
    * `SimulationCurveset.calc_PA`
    * `SimulationCurveset.calc_kA`
    * `SimulationCurveset.calc_kex`
    * `SimulationCurveset.calc_kB`
  * **Reference**
    * Winzor & Jackson (2006)

Using ΔH and P<sub>A</sub>(T0), the van't Hoff relation yields ΔS

<img src='http://chemistry.osu.edu/~foster.281/guardd//manual/formulae/formula-kinetic_simulator-03.png' alt='[UNLOADED IMAGE]'> </img>

which, with ΔH, determines P<sub>A</sub> at any temperature via van't Hoff

<img src='http://chemistry.osu.edu/~foster.281/guardd//manual/formulae/formula-kinetic_simulator-04.png' alt='[UNLOADED IMAGE]'> </img>

Next, using P<sub>A</sub> and k<sub>ex</sub> at T<sub>0</sub> determines k<sub>A</sub> and k<sub>B</sub> at T<sub>0</sub>

<img src='http://chemistry.osu.edu/~foster.281/guardd//manual/formulae/formula-kinetic_simulator-05.png' alt='[UNLOADED IMAGE]'> </img>

<img src='http://chemistry.osu.edu/~foster.281/guardd//manual/formulae/formula-kinetic_simulator-06.png' alt='[UNLOADED IMAGE]'> </img>

and using E<sub>AB</sub> and k<sub>A</sub> at T<sub>0</sub>, the Arrhenius relation yields P<sub>AB</sub>

<img src='http://chemistry.osu.edu/~foster.281/guardd//manual/formulae/formula-kinetic_simulator-07.png' alt='[UNLOADED IMAGE]'> </img>

which, with E<sub>AB</sub>, yields k<sub>A</sub> at any temperature via Arrhenius

<img src='http://chemistry.osu.edu/~foster.281/guardd//manual/formulae/formula-kinetic_simulator-08.png' alt='[UNLOADED IMAGE]'> </img>

Next, knowledge of P<sub>A</sub> and k<sub>A</sub> at any temperature yields k<sub>ex</sub> at any temperature

<img src='http://chemistry.osu.edu/~foster.281/guardd//manual/formulae/formula-kinetic_simulator-09.png' alt='[UNLOADED IMAGE]'> </img>

and therefore k<sub>B</sub> at any temperature

<img src='http://chemistry.osu.edu/~foster.281/guardd//manual/formulae/formula-kinetic_simulator-10.png' alt='[UNLOADED IMAGE]'> </img>

Knowledge of k<sub>B</sub> at any temperature yields E<sub>BA</sub> via the Arrhenius relation and selection of any two temperatures T<sub>1</sub> and T<sub>2</sub> (e.g., 280 K and 320 K)

<img src='http://chemistry.osu.edu/~foster.281/guardd//manual/formulae/formula-kinetic_simulator-11.png' alt='[UNLOADED IMAGE]'> </img>

Finally, using k<sub>B</sub>(T<sub>0</sub>) and E<sub>BA</sub>, the Arrhenius relation yields P<sub>BA</sub>

<img src='http://chemistry.osu.edu/~foster.281/guardd//manual/formulae/formula-kinetic_simulator-12.png' alt='[UNLOADED IMAGE]'> </img>




### Grid search ###
  * **Motivation**
    * Nonlinear nature of RD phenomena makes the relationship between χ<sup>2</sup> and fitting parameters (**p**) difficult to predict
    * Optimization algorithms often “fail” by finding a local minimum of χ<sup>2</sup>, which is sensitive to initial fitting conditions, instead of the intended global minimum of χ<sup>2</sup>
  * **Goal**: _Fit data multiple times to assess sensitivity of final fit to initial conditions_

  * **Six-dimensional (6D) grid search**
    1. |Δω<sub>H</sub>|
    1. |Δω<sub>X</sub>|
    1. P<sub>A</sub><sup>0</sup> = P<sub>A</sub>(T<sub>0</sub>), where T<sub>0</sub> is a specified temperature (e.g., 25C)
    1. k<sub>ex</sub><sup>0</sup> = k<sub>ex</sub>(T<sub>0</sub>), where T<sub>0</sub> is a specfied temperature (e.g., 25C)
    1. E<sub>AB</sub> (only for consraining rates via Arrhenius)
    1. ΔΗ (only for consraining rates via Arrhenius)

  * **Each point specifies initial conditions for the fit, as follows**
    * Δω values are used for every Curveset in the Group
      * Note: this may be sub-optimal since each Curveset can have a different Δω value
    * If constrain rates is NOT used
      * P<sub>A</sub><sup>0</sup> is used for all temperatures in the Group
      * k<sub>ex</sub><sup>0</sup> value is used at temperature T<sub>0</sub> and increased by 2x for each increase in 10C from T<sub>0</sub> (i.e., k<sub>ex</sub>(T) = k<sub>ex</sub><sup>0</sup><sup>(T-T,,0,,)/10</sup>)
    * If constrain rates IS used
      * P<sub>A</sub>(T) determined using P<sub>A</sub>^0 and ΔH
      * k<sub>ex</sub>(T) determined using k<sub>ex</sub><sup>0</sup> and E<sub>AB</sub>
    * R<sub>2</sub><sup>0</sup> is always the minimum value of the observed R<sub>2</sub> in the Curve


**Recommendations on bounds at T<sub>0</sub> = 25C**

| 		|**Δω<sub>H</sub>(ppm)**|**Δω<sub>Χ</sub>(ppm)**|**P<sub>A</sub><sup>0</sup>(%)**|**k<sub>ex</sub><sup>0</sup>(/s)**	| E<sub>AB</sub> (kcal/mol)	| ΔH (kcal/mol)	|
|:--|:----------------------|:----------------------|:-------------------------------|:----------------------------------|:--------------------------|:--------------|
| **Min** 	| 0.01  	               | 0.1  	                | 70  		                         | 500  		                           | -20			                    | -20			        |
| **Max** 	| 0.2  	                | 3  		                 | 99.9  	                        | 3500  		                          | 20			                     | 20			         |
| **Steps**	| 1-3 		                | 2-5 		                | 2-10		                         | 3-10			                           | 2-5			                    | 2-5			        |

**Recommendations on number of steps**

| **Group Size**	| **Num(Curves)**| **Num(Steps)**	| **Notes**			|
|:---------------|:---------------|:---------------|:------------|
| _Small_	       | 1-5		          | 5-50		         | _Easy to fit, usually only one solution_ 	|
| _Medium_	      | 5-10		         | 20-100	        | _Usually easy to fit, sometimes a few solutions_ 	|
| _Large_	       | 10-20	         | 100-200	       | _Sometimes challenging to fit, several solutions_|
| _Very Large_	  | 20-50	         | 500?		         | _Very challenging to fit_ 	|

  * **Unsorted notes**
    * k<sub>ex</sub> seems to be a very sensitive parameter, use the most points here
    * Sometimes MATLAB does not alter Δω values for multiple Curvesets
    * E<sub>AB</sub> and ΔH can be very difficult to optimize via grid search
  * **Location in code**
    * `Group.gridSearch`

### Monte Carlo error estimation ###
  * **Motivation**: _The final fit to RD data are sometimes very sensitive to noise in the data_
  * **Goal**: _Generate and fit multiple synthetic data to assess sensitivity of final fit to noise in data_

<a href='http://chemistry.osu.edu/~foster.281/guardd//manual/figure-monte_carlo/figure-monte_carlo.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd//manual/figure-monte_carlo/figure-monte_carlo.png' alt='[UNLOADED IMAGE]' width='300'> </img> </a>

_Monte Carlo procedure generates and fits synthetic data consistent with observed residuals (related to noise)_

**Procedure**

> (1) Calculate residuals for each ν<sub>CPMG</sub> value in a given Curve

> ε(ν<sub>CPMG</sub>) = R<sub>2Eff</sub><sup>Obs</sup>(ν<sub>CPMG</sub>) - R<sub>2Eff</sub><sup>Calc</sup>(ν<sub>CPMG</sub>)

> (2a) The residuals are used to create a normal distribution for the Curve with mean and variance

> Norm(mean(ε), var(ε))

> (2b) Alternatively, the experimental errors σ(R<sub>2Eff</sub><sup>Obs</sup>) can be used

> Norm(mean(σ), var(σ))

> (3) Generate a synthetic dispersion Curve using the fit at each ν<sub>CPMG</sub> plus a random sample from the distribution

> R<sub>2Eff</sub><sup>Synth</sup> = R<sub>2Eff</sub><sup>Calc</sup>(ν<sub>CPMG</sub>) + Sample( Norm(mean(ε), var(ε)) )

> _or using Norm(mean(σ), var(σ))_

> (4) Repeat for each Curve in the Group such that a synthetic Group is produced

> (5) Fit the synthetic Group using initial conditions from the best fit of the actual data.

> (6) Repeat (3)-(5) multiple times (default 100x, can be changed in settings "Nmc")

> This yields 100 synthetic Groups and 100 sets of optimized fit parameters

> (7) Calculate the error in a given parameter as the standard deviation of the optimized fit parameter from its 100 element distribution

> (8) Errors in subsequent quantities (e.g., k<sub>A</sub>, k<sub>B</sub>, ln(k<sub>A</sub>), etc.) are estimated using propagation of error assuming all parameters are uncorrelated (zero covariance)

  * **Notes**
    * Number of MC error iterations can be set via Input...Settings...`Nmc`
    * Debugging output can display the fits to each data vi Input...Settings...`OUTPUT_DEBUG_ERRORS`
  * **Location in code**
    * `FitResult.calculateErrors`
  * **Reference**
    * Motulsky (2003), p. 108

## Glossary ##
  * <u><b><sup>A</sup>X</b></u>: Any nucleus with mass number A and chemical symbol X (e.g,.<sup>1</sup>H, <sup>13</sup>C, <sup>15</sup>N)
  * <u><b>B<sub>0</sub></b></u>: Magnetic field strength (Tesla)
  * <u><b>C</b></u>: Curve number within the curveset
  * <u><b>Chi2</b></u>: χ<sup>2</sup>; Goodness of fit metric (smaller value indicates better fit)
  * <u><b>CPMG</b></u>: Carr-Purcell Meiboom-Gill (four scientists who poineered relaxation dispersion methods)
  * <u><b>CS</b></u>: Curveset number
  * <u><b>CTOT</b></u>: Total curve number within the group
  * <u><b>Curve</b></u>: A single set of R2Eff(νCPMG) data points
  * <u><b>Curveset</b></u>: Designates a ΔωH and ΔωX to a set of one or more Curves
  * <u><b>DQ</b></u>: Double Quantum (not implemented in GUARDD)
  * <u><b>E<sub>AB</sub></b></u>: E<sub>B</sub> - E<sub>A</sub>; Activation energy to exchange from A→B (cal/mol)
  * <u><b>G</b></u>: Group number
  * <u><b>Group</b></u>: Designates a P<sub>A</sub> and k<sub>ex</sub> at each temperatuer for a set of one or more Curvesets
  * <u><b>GUARDD</b></u>: Graphical User-friendly Analysis of Relaxation Dispersion Data
  * <u><b>GUI</b></u>: Graphical User Interface
  * <u><b>k<sub>A</sub></b></u>: (1-P<sub>A</sub>)k<sub>ex</sub>; Rate of exchange from A→B
  * <u><b>k<sub>B</sub></b></u>: P<sub>A</sub>k<sub>ex</sub>; Rate of exchange from B→A
  * <u><b>k<sub>ex</sub></b></u>: k<sub>A</sub> + k<sub>B</sub>; Total exchange rate between states (/s)
  * <u><b>MC</b></u>: Monte Carlo (randomization method used here for error analysis)
  * <u><b>MQ</b></u>: Multiple Quantum (signal detected in NMR); Note: MQ RD curves are sensitive to _both_ Δω<sub>H</sub> and Δω<sub>X</sub>
  * <u><b>NMR</b></u>: Nuclear Magnetic Resonance
  * <u><b>NMR probe</b></u>: One nucleus in the target molecule that can be observed via NMR; designated a unique unique residue number (e.g., 1,2,3,...) and atom (e.g,. H<sup>N</sup>, C<sup>O</sup>, Cδ<sub>2</sub>)
  * <u><b>P<sub>A</sub></b></u>: Population fraction of A state (fraction, %)
  * <u><b>ppm</b></u>: Parts Per Million (a dimensionless unit of measure for relative comparison)
  * <u><b>R</b></u>: Gas constant
  * <u><b>R<sub>2</sub><sup>0</sup></b></u>: Transverse relaxation rate in the absence of exchange (Hz)
  * <u><b>RD</b></u>: Relaxation Disperion
  * <u><b>SQ</b></u>: Single Quantum (signal detected in NMR); Note: SQ curves that pulse on <sup>A</sup>X nucleus are sensitive _only_ to Δω<sub>X</sub> (Δω<sub>H</sub> is fixed to zero)
  * <u><b>T<sub>CPMG</sub></b></u>: Total duration of the CPMG block in the NMR RD experiment
  * <u><b>ZQ</b></u>: Zero Quantum (not implemented in GUARDD)
  * <u><b>γ<sub>X</sub></b></u>: Gyromagnetic ratio for nucleus X (MHz/Tesla)
  * <u><b>ΔH</b></u>: H<sub>B</sub> - H<sub>A</sub>; Enthalpy difference to exchange from A→B (cal/mol)
  * <u><b>Δν</b></u>: Chemical shift difference in Hz
  * <u><b>Δω<sub>H</sub></b></u>: <sup>1</sup>H chemical shift difference between states A and B (ppm, rad/s) - **MQ only**
  * <u><b>Δω<sub>X</sub></b></u>: <sup>A</sup>X chemical shift difference between states A and B (ppm, rad/s)
  * <u><b>ν<sub>CPMG</sub></b></u>: Precession frequency of refocused magnetization during CPMG period of NMR RD experiment



## Acknowledgements ##
  * Foster Lab members for debugging during development
  * Advisor Prof. Mark Foster [link](http://chemistry.osu.edu/~foster.281/)
  * The Ohio State University Biochemistry Dept. [link](http://www.biosci.ohio-state.edu/~biochem/)
  * The Ohio State University Biophysics Program [link](http://www.biosci.ohio-state.edu/~biophys/)
  * The Ohio State University [link](http://www.osu.edu/)
  * National Institutes of Health [link](http://www.nih.gov/)

## Citing GUARDD ##
  * GUARDD manuscript: [http://dx.doi.org/10.1007/s10858-011-9589-y](http://dx.doi.org/10.1007/s10858-011-9589-y)

  * **Please cite your usage of GUARDD in BOTH ways**
    1. Kleckner, I. R., & Foster, M. P. (2012). GUARDD: user-friendly MATLAB software for rigorous analysis of CPMG RD NMR data. Journal of biomolecular NMR, 52(1), 11–22. doi:10.1007/s10858-011-9589-y
    1. http://code.google.com/p/guardd/

## References ##
  * **Please cite your usage of GUARDD in BOTH ways**
    1. Kleckner, I. R., & Foster, M. P. (2012). GUARDD: user-friendly MATLAB software for rigorous analysis of CPMG RD NMR data. Journal of biomolecular NMR, 52(1), 11–22. doi:10.1007/s10858-011-9589-y
    1. http://code.google.com/p/guardd/
  * **Review on protein dynamics via NMR**
    * Kleckner, I. R., & Foster, M. P. (2011). An introduction to NMR-based approaches for measuring protein dynamics. Biochimica et biophysica acta, 1814(8), 942-968. Elsevier B.V. doi: 10.1016/j.bbapap.2010.10.012.
  * **Fitting RD data is poorly determined**
    * Kovrigin, E. L., Kempf, J. G., Grey, M. J., & Loria, J. P. (2006). Faithful estimation of dynamics parameters from CPMG relaxation dispersion measurements. Journal of magnetic resonance (San Diego, Calif. : 1997), 180(1), 93-104. doi: 10.1016/j.jmr.2006.01.010.
    * Ishima, R., & Torchia, D. a. (2005). Error estimation and global fitting in transverse-relaxation dispersion experiments to determine chemical-exchange parameters. Journal of biomolecular NMR, 32(1), 41-54. doi: 10.1007/s10858-005-3593-z.
  * **Fast exchange approximation**
    * Luz, Z. & Meiboom, S. (1963). Nuclear magnetic resonance study of protolysis of trimethylammonium ion in aqueous solution - order of reaction with respect to solvent. J. Chem. Phys., 39, 366-370.
    * Ishima, R. & Torchia, D.A. (1999). Estimating the time scale of chemical exchange of proteins from measurements of transverse relaxation rates in solution. Journal of Biomolecular NMR, 14, 369-72. http://view.ncbi.nlm.nih.gov/pubmed/10526408
  * **MQ dispersion**
    * Korzhnev, D. M., Kloiber, K., & Kay, L. E. (2004). Multiple-quantum relaxation dispersion NMR spectroscopy probing millisecond time-scale dynamics in proteins: theory and application. Journal of the American Chemical Society, 126(23), 7320-9. doi: 10.1021/ja049968b.
  * **Quantum Coherences in dispersion**
    * Korzhnev, D. M., Neudecker, P., Mittermaier, A., Orekhov, V. Y., & Kay, L. E. (2005). Multiple-site exchange in proteins studied with a suite of six NMR relaxation dispersion experiments: an application to the folding of a Fyn SH3 domain mutant. Journal of the American Chemical Society, 127(44), 15602-11. doi: 10.1021/ja054550e.
  * **Exchange timescale α**
    * Millet, O., Loria, J. P., Kroenke, C. D., Pons, M., & Palmer, A. G. (2000). The Static Magnetic Field Dependence of Chemical Exchange Linebroadening Defines the NMR Chemical Shift Time Scale. Journal of the American Chemical Society, 122(12), 2867-2877. doi: 10.1021/ja993511y.
  * **Nonlinear fitting**
    * P, B., & D, R. (2003). Data reduction and error analysis for the physical sciences. (D. Bruflodt, Ed.) (3rd ed.). New York, NY: McGraw-Hill.
    * Motulsky, H. J., & Christopoulos, A. (2003). Fitting models to biological data using linear and nonlinear regression. A practical guide to curve fitting. (GraphPad Software Inc., Eds.) (2nd ed.). San Diego CA: GraphPad Software Inc.
  * **Temperature-dependence of rate and equilibrium constants (Arrhenius and vant Hoff analyses)**
    * Winzor, D. J., & Jackson, C. M. (2006). Interpretation of the temperature dependence of equilibrium and rate constants. Journal of Molecular Recognition, c(August), 389-407. doi: 10.1002/jmr.

## Author ##
  * (C) [Ian Kleckner](http://ianrobertkleckner.blogspot.com)

  * Work completed as part of PhD Dissertation
  * Mark Foster's Lab
  * The Ohio State University
  * Columbus, OH, USA