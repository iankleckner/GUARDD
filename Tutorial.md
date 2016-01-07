<a href='Hidden comment: 
This text will be removed from the rendered page.

<wiki:gadget url="http://mathml-gadget.googlecode.com/svn/trunk/mathml-gadget.xml" border="0" up_content="root3x + x^phi + x_1" height="15"/>

http://code.google.com/images/code_sm.png

# 1
# 2
# 3
# 4


* 1
* 2
* 3
* 4


<ol>
<li>1

Unknown end tag for &lt;/li&gt;


<ol>
<li>2

Unknown end tag for &lt;/li&gt;


<ol>
<li>3

Unknown end tag for &lt;/li&gt;


<ol>
<li>4

Unknown end tag for &lt;/li&gt;




Unknown end tag for &lt;/ol&gt;




Unknown end tag for &lt;/ol&gt;




Unknown end tag for &lt;/ol&gt;




Unknown end tag for &lt;/ol&gt;




Wiki
http://guardd.googlecode.com/files/figure-data_management.png

Link
[http://guardd.googlecode.com/files/figure-data_management.png image]

HTML+Link (Works)
<a href="http://guardd.googlecode.com/files/figure-data_management.png"> <img src="http://guardd.googlecode.com/files/figure-data_management.png.png" alt="image" width="100"> 

Unknown end tag for &lt;/a&gt;



OBJECT TYPE (Doesn"t work)
<object type="image/png" data="http://guardd.googlecode.com/files/figure-data_management.png" width="300" >

'></a>


## Contents ##


## Goals ##
  * Become familiar with basic features of GUARDD

## Requirements ##
  1. 60-90 min
  1. [MATLAB software](http://www.mathworks.com)
  1. [MATLAB Optimization Toolbox](http://www.mathworks.com/products/optimization/)
  1. [MATLAB Curve Fitting Toolbox](http://www.mathworks.com/products/curvefitting/)
  1. [MATLAB Statistics Toolbox](http://www.mathworks.com/products/statistics/)
  1. GUARDD program [download](http://code.google.com/p/guardd/downloads/list)
    1. Matlab .m and .fig files
  1. Tutorial files for this example [download](http://code.google.com/p/guardd/downloads/list)

## General notes ##
  1. Tutorial images shown below are from GUARDD v.2011.07.01 and associated `GUARDD-Session-Tutorial.mat` file
    1. This tutorial is **also** compatible with GUARDD v.2011.09.11 and associated `GUARDD-Session-Tutorial.mat` file,
    1. v.2011.09.11 session uses more points in grid search than the v.2011.07.01 session (150 vs. 60)
  1. See Manual for Glossary [here](Manual#Glossary.md)
  1. <u>Underlined</u> items are GUARDD window titles
  1. **Boldface** items are commands (buttons, menus) and important points
  1. GUARDD utilizes multiple GUI windows (may need to be resized)
    1. Higher monitor resolution helps (1024x768 minimum)
  1. Matlab **must remain open** (it controls GUARDD)
  1. GUARDD <u>Main</u> window **must remain open** (it controls other GUI windows)
  1. Check <u>Matlab command window</u> for additional output
  1. GUARDD is sometimes slow. Turn on CPU monitor to see when program is processing
    1. **Win**: Ctrl+Alt+Del, click _Task Manager_, watch icon in task bar
    1. **Mac**: _Applications_ folder → _Utilities_ folder → launch _Activity Monitor_
  1. "Tooltips" are revealed by hovering mouse cursor over buttons, tables, etc.

## Tutorial ##

### Download and unpack files ###
  1. Download files [download](http://code.google.com/p/guardd/downloads/list)
  1. Unpack files
    1. E.g., `/home/user/Desktop/` or `C:\My_Favorite_Folder\`
  1. Ensure proper directory structure
    1. GUARDD--YYYY.MM.DD/ (**Note**: `YYYY.MM.DD` codes for the date (e.g., `2011.06.17`))
      1. `tutorial/`
      1. (Many .m files)
      1. (Many .fig files)

### Start GUARDD ###
  1. Start **Matlab**
  1. Open Matlab command window: **Desktop...Command Window**
  1. Navigate to GUARDD/ directory and start program
    1. <u>Matlab command window</u>: **`cd 'c:\My_Favorite_Folder\GUARDD--YYYY.MM.DD\'`**
    1. **Note**: _`YYYY.MM.DD` is replaced by the date corresponding to the GUARDD version (e.g., `2011.06.08`)_
    1. <u>Matlab command window</u>: **`clear; GUARDD`**
  1. **Important**: _Main window must remain open (it controls all other GUI windows)_
  1. Check Matlab command window for additional output

<a href='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--01.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--01.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

### Load data ###
  * **Goal**: _Get RD data into the program for analysis_
  * **Tip**: _A variety of input types are available (see [Manual](Manual#Input:_Script_file_to_load_data.md))_

  1. <u>Main</u>
    1. **Input...Data manager...**
  1. <u>Data Manager</u>
    1. **Input...Script...**
      1. `tutorial/data/GUARDD-Data-ApoTRAP-Kleckner.txt`
  1. 14 datasets loaded
    1. 600 and 800 MHz
    1. 25, 32, and 37<sup>o</sup>C
    1. SQ and MQ coherence

<a href='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--02.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--02.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

### Create groups for fitting ###
  * **Goal**: _Aggregate RD curves from the same NMR signal (assignment) for group fitting_

  * **Essential notes on data organization**
    * **Datasets** designate experimental conditions
    * **Datasets** contain **Curves**, which contain RD data
    * **Curves** are aggregated across common NMR probes (assignment) into **Curvesets** (to share Δω values)
    * **Curvests** are aggregated across different NMR probes into **Groups** (to share k<sub>ex</sub> and P<sub>A</sub>)
  * **Details** regarding data organization are discussed in the [Manual](Manual#Organizing_data.md)

  1. <u>Data Manager</u>
    1. **Group...Generate from subset of data...**
  1. <u>Create Groups</u>
    1. Make groups only for Ile residues at 25<sup>o</sup>C
      1. Check _Residue_
      1. Type _Ile_
      1. Check _TempC_
      1. Type _25_
    1. Click **Generate groups**


<a href='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--03.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--03.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>


  1. <u>Data Manager</u>
    1. **Group...Generate from subset of data...**
  1. <u>Create Groups</u>
    1. Make groups only for index 22
      1. Check _Index_
      1. Type _22_
    1. Click **Generate groups**
  1. <u>Data Manager</u>
    1. **Group...Sort groups**
  1. Close the <u>Data Manager</u> window

<a href='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--04.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--04.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

### Select groups that exhibit exchange ###
  * **Goal**: _Determine which groups exhibit flexibility, and therefore warrant further analysis_
    * **Details**: Read more about describing dispersions in the [Manual](Manual#Describing_dispersions.md)
  1. <u>Main</u>
    1. Click **Refresh** to show loaded groups
    1. Use **<** and **>** to cycle through groups
    1. Check **Exch?** if the data are not horizontal (i.e., if R<sub>ex</sub> > 0)
      1. **Note**: all residues exhibit exchange except Ile 61δ<sub>1</sub> and Ile 68δ<sub>1</sub>

<a href='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--05.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--05.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

### Fit RD data ###
  * **Goal**: _Obtain best-fit values for the 4-5 parameters required to describe each curve_
    1. Δω<sub>H</sub> = <sup>1</sup>H chemical shift difference between states A and B (ppm, rad/s, Hz) - **MQ only**
    1. Δω<sub>X</sub>= <sup>A</sup>X chemical shift difference between states A and B (ppm, rad/s, Hz)
    1. P<sub>A</sub> = Population fraction of A state (fraction, %)
    1. k<sub>ex</sub> = k<sub>A</sub> + k<sub>B</sub> = Total exchange rate between states (/s)
    1. R<sub>2</sub><sup>0</sup> = Transverse relaxation rate in the absence of exchange (Hz)

#### Fit simple group manually ####
  * **Goal**: _Use_<u>Fit RD</u> window to manually fit one group_*_Determine optimal P<sub>A</sub>, and k<sub>ex</sub>, at each temperature (x1) → propagate to all curves in group_*_Determine optimal Δω<sub>H</sub>, Δω<sub>X</sub>, for each curveset (x1) → propagated to all curves in curveset_*_Determine and R<sub>2</sub><sup>0</sup> for each curve (x4)_* **Goal**:_Demonstrate basic fitting options (Simulate vs. Optimize, Individual vs. Grid)_* **Details**: Read more about the_<u>Fit RD</u> window in the [Manual](Manual#Fit_Dispersion.md)

  1. <u>Main</u>
    1. Check **Fit dispersion**
    1. Select _Ile 26_

  1. <u>Fit RD</u>
    1. _Contains 6 panels for sequential fitting tasks_
    1. (1a) Procedure: **Individual**
    1. (1b) Task: **Simulate**
    1. (2) INITIAL CONDITIONS: _(Leave default)_
      1. **Note**: Often, one may change starting P<sub>A</sub>, k<sub>ex</sub>, Δω<sub>H</sub>, and Δω<sub>X</sub>
      1. To change starting [R20](https://code.google.com/p/guardd/source/detail?r=20), see https://groups.google.com/d/topic/guardd/A4c-3bn21Yk/discussion
    1. Click **Go!** (1-5 sec)
      1. Note that these initial conditions are reasonable (fit is somewhat close to data)
    1. (1b) Task: **Optimize fit**
    1. Click **Go!** (5-30 sec)
    1. (3) SELECT fit and view results
      1. There are three "fits" to the data: {{NoEx, Sim-1, and Fit-1}}
      1. Select each at a time, and note that `Fit-1` is the best (lines go through data in panel (4))
      1. Select `Fit-1`
      1. Click **Set best fit**
    1. (6) Designate which parameters are OK
      1. Check **Best fit is OK**
      1. Click **All**
      1. **Note**: In general, one should more carefully check if the best fit is OK (see [Manual](Manual#Determining_which_parameters_are_OK.md))

<a href='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--06.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--06.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>


  * **Goal**: _If unsure about which initial conditions to use, the grid search fits multiple times with different initial conditions_
    1. (1a) Procedure: **Grid search**
    1. In the interest of time, use this relatively small grid

| 		| **dwH(ppm)**	| **dwX(ppm)**	| **PA0(%)**	| **kex0(/s)**	|
|:--|:-------------|:-------------|:-----------|:-------------|
| **Min** 	| 0.01  	      | 0.1  	       | 80  		     | 500  	       |
| **Max** 	| 0.1  	       | 3.00  	      | 99.9  	    | 3000  	      |
| **Steps**	| 1  		        | 2  		        | 2  		      | 3  		        |

  1. Click **Save**
  1. (1b): Task: **Optimize fit**
  1. Click **Go!** (5-10 sec/fit x 12 fits = 60-120 sec)
  1. **Note**: _Progress can also be viewed in the MATLAB_<u>Command Window</u>_1. (3) SELECT fit and view results
  1. The `Fit-G` result listed is the best fit (lowest χ<sup>2</sup>) out of all the 12 fits in the grid search
  1. The remaining 11 fits can be viewed in the_<u>Chi2 Map</u> window (see [Manual](Manual#Display_Chi2_Map.md))
    1. (6) Designate which parameters are OK
    1. Click **All**

  1. **Observe**: _Becuase the initial conditions used for `Fit-1` above were appropriate, both `Fit-1` and `Fig-G` yield the same result_
  1. **Note**: _The grid search can demonstrate success if the optimal fit is **insensitive** to inital conditions_

<a href='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--07.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--07.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

  * **Note**: Saving data and output plots are discussed [below](Tutorial#View_results_in_display_cluster.md)

#### Save GUARDD session to file ####
  * **Goal**: _Save progress (loaded data and fits) to resume a GUARDD session later_
  1. <u>Main</u>
    1. **Output...Save session as...**
    1. _GUARDD will create an output folder named with the date, and suggest a filename for you_
    1. **Note**: _To change the default output folder, use the_<u>Settings</u> window (see [Manual](Manual#Settings.md))_* **Tip**:_Save your work often (in case GUARDD and/or MATLAB crashes)

#### Fit multi-temperature group manually ####
  * **Goal**: _Use_<u>Fit RD</u> window to manually fit one group acquired at multiple temperatures_*_Determine optimal P<sub>A</sub>, and k<sub>ex</sub>, at each temperature (x3) via two methods (A and B) → propagate to all curves in group_*_Determine optimal Δω<sub>H</sub>, Δω<sub>X</sub>, for each curveset (x1) → propagated to all curves in curveset_*_Determine and R<sub>2</sub><sup>0</sup> for each curve (x10)

  * **Goal**: _Demonstrate multi-temperature fitting options_
    * Method A (No rate constraint): _Determine optimal P<sub>A</sub> and k<sub>ex</sub> at each temperature_
    * Method B (Impose rate constraint): _Determine optimal P<sub>A</sub> and k<sub>ex</sub> at some temperature T<sub>0</sub>, with ΔH and E<sub>AB</sub> to determine P<sub>A</sub> and k<sub>ex</sub> at an arbitrary temperature_
    * **Details**: Read more about assigning fitting parameters in the [Manual](Manual#Assigning_parameters_for_fitting.md)

  * **Goal**: _Fit without rate constraints (Method A)_
  1. <u>Main</u>
    1. Select _Leu 22delta1_
    1. _The_<u>Fit RD</u> window should automatically open (no double-click required)_1._If it does not open, check **Fit dispersion** then select **Leu 22delta1**_1._<u>Fit RD</u>
    1. (1a) Procedure: **Individual**
    1. (1b) Task: **Simulate**
    1. Uncheck **Use Arrhenius**
    1. (2) Individual initial conditions

| **Temp(C)** 	| **PA(%)**	| **kex(/s)**	|
|:-------------|:----------|:------------|
| 25		         | 95		      | 1000		      |
| 32		         | 96		      | 1200		      |
| 37		         | 97		      | 1500		      |

| **Curveset**	| **dwH(ppm)**	| **dwX(ppm)**	|
|:-------------|:-------------|:-------------|
| Leu 22\delta1| 0.1		        | 1		          |

  1. Click **Go!** (1-5 sec)
    1. Note that these initial conditions are reasonable (fit is somewhat close to data)
  1. (1b) Task: **Optimize fit**
  1. Click **Go!** (5-30 sec)

  1. (3) Select `Fit-1[--]` fit result
    1. Click **Set best fit**
  1. (6) Designate that all parameters are OK
    1. Check **Best fit is OK**
    1. Click **All**

<a href='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--08.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--08.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>


  * **Goal**: _Fit with rate constraints (Method B)_
  1. <u>Fit RD</u>
    1. (1a) Procedure: **Individual**
    1. (1b) Task: **Simulate**
    1. Check **Use Arrhenius**
    1. (2) Individual initial conditions

| **T0(C)**	| **PA0(%)**	| **kex0(/s)**	| **dH(kcal/mol)**	| **Eab(kcal/mol)**	|
|:----------|:-----------|:-------------|:-----------------|:------------------|
| 25		      | 95		       | 1000		       | -5			            | 1			              |

| **Curveset**	| **dwH(ppm)**	| **dwX(ppm)**	|
|:-------------|:-------------|:-------------|
| Leu 22\delta1| 0.1		        | 1		          |

  1. Click **Go!** (1-5 sec)
    1. Note that these initial conditions are reasonable (fit is somewhat close to data)
  1. (1b) Task: **Optimize fit**
  1. Click **Go!** (5-30 sec)

  1. (3) Select `Fit-1[CR]` fit result
    1. Click **Set best fit**
  1. (6) Designate that all parameters are OK
    1. Check **Best fit is OK**
    1. Click **All**

<a href='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--09.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--09.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

#### Examine rate analysis (vant Hoff and Arrhenius) ####
  * **Goal**: _Use_<u>Rates</u> window to examine temperature-dependence of rates (vant Hoff and Arrenius)_1._<u>Main</u>
    1. _Make sure **Leu 22delta1** is selected_
    1. **Output...Display rates...**
  1. <u>Rates</u>
    1. Select fit: **`Fit-1[--]`**
      1. The rates in this fit are independently determined for each temperature
      1. ΔH, E<sub>AB</sub>, and E<sub>BA</sub> are **extracted** from the slopes
    1. Select fit: **`Fit-1[CR]`**
      1. The rates are **constrained** to lie along the line with slope ΔH, E<sub>AB</sub>, or E<sub>BA</sub>
    1. _Save the figure to a file_
    1. Close <u>Rates</u>

<a href='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--10.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--10.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

#### View fits to RD data ####
  * **Goal**: _Use_<u>Display RD</u> window to assess the fit to the RD data, and prepare an output figure

  * **Goal**: _Create a 3D plot that highlights the amount of data in the set_
  1. <u>Main</u>
    1. _Make sure **Leu 22delta1** is selected_
    1. **Output...Display RD...**
  1. <u>Display RD</u>
    1. Select all the curves in the Curveset(Curve) list
    1. Select fit `Fit-1[CR]` from fit list
    1. Check **Y scale** to auto-scale the Y-axis for this group only
    1. Check **3D Angle**
    1. Uncheck **Show Residuals**
    1. Click **Save Figure to Disk** icon in taskbar
    1. _GUARDD will prepare a filename for saving, and you must type the file extension_
    1. Type **ps** to save as a postscript file and click **Save** (or hit **Enter**)

<a href='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--11.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--11.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

  * **Goal**: _Create a 2D plot with residuals that highlights the fit to some of the data_
  1. <u>Display RD</u>
    1. Select only the following curves from the list
      1. Curve 1: 800-MQ-25C
      1. Curve 5: 800-MQ-32C
      1. Curve 8: 800-MQ-37C
    1. Select fit `Fit-1[--]` from fit list
    1. Uncheck **3D Angle**
    1. Check **Show Residuals**
    1. Click **Save Figure to Disk** icon in taskbar
    1. _GUARDD will prepare a **new** filename becuase it is a different fit number_
    1. Type **ps** to save as a postscript file and click **Save** (or hit **Enter**)
    1. Close the <u>Display RD</u> window

<a href='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--12.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--12.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

  * **Save the session often**
    1. <u>Main</u>
      1. **Output...Save session as...**

#### Create and fit a multi-curveset, multi-temperature group manually ####
  * **Goal**: _Prepare and fit a relatively large group of data_


##### Create a multi-curveset, multi-temperature group #####
  * **Goal**: _Use_<u>Data Manager</u> to create a group with multiple curvesets_1._<u>Main</u>
    1. **Input...Data manager...**
  1. <u>Data Manager</u>
    1. Create a new group for Leu 22
      1. Click **New** in the panel _Groups for fitting_
      1. Table on right, enter group **name**: _Leu 22_
      1. Table on right, enter group **index**: _22_
      1. Click **Save** in the panel _Groups for fitting_
    1. Add two curvesets to this new group
      1. Select group **Leu 22\delta1**
      1. Select curveset **Leu 22\delta1**
      1. Click **Copy to group**
    1. <u>Select Group</u>
      1. Select group **Leu 22** (at the bottom)
      1. Click **Select**
      1. (Repeat this process with the second curveset, **Leu 22\delta2**)

<a href='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--13.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--13.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

  1. **Group...Sort groups...**
  1. Make sure that group _Leu 22_ contains two curvesets: _Cp(Leu 22\delta1)_ and _Cp(Leu 22\delta2)_
    1. **Note**: A **copy** ("Cp") is made because this is a **different** curvest than the original, and therefore may contain a **different** set of curves (e.g., only one temperature, only MQ)
    1. It can be **renamed** if desired, with no adverse effects
    1. See [Manual](Manual#Organizing_data.md) for more on organizing data
  1. Close <u>Data Manager</u>

<a href='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--14.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--14.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

##### Fit a multi-curveset, multi-temperature group #####
  * **Goal**: _Use_<u>Fit RD</u> window to manually fit one group containing multiple curvesets_*_Determine optimal P<sub>A</sub>, and k<sub>ex</sub>, at each temperature (x3) → propagate to all curves in group_*_Determine optimal Δω<sub>H</sub>, Δω<sub>X</sub>, for each curveset (x2) → propagated to all curves in curveset_*_Determine and R<sub>2</sub><sup>0</sup> for each curve (x20)

  1. <u>Main</u>
    1. Uncheck **Fit dispersion** so the window does not open automatically
    1. Click **Refresh** so the new group appears
    1. Select **Leu 22**
    1. Check **Exch?**
    1. **Analysis...Fit dispersion...**
  1. <u>Fit RD</u>
    1. (1a) Procedure: **Individual**
    1. (1b) Task: **Optimize fit**
    1. Uncheck **Use Arrhenius**
    1. (2) Individual initial conditions

| **Temp(C)** 	| **PA(%)**	| **kex(/s)**	|
|:-------------|:----------|:------------|
| 25		         | 95		      | 1000		      |
| 32		         | 96		      | 1200		      |
| 37		         | 97		      | 1500		      |

| **Curveset**	| **dwH(ppm)**	| **dwX(ppm)**	|
|:-------------|:-------------|:-------------|
| Cp(Leu 22\delta1)| 0.1	         | 1		          |
| Cp(Leu 22\delta1)| 0.1	         | 1		          |

  1. Click **Go!** (50-100 sec)
  1. (3) Select `Fit-1[--]` fit result
    1. Click **Set best fit**
  1. (6) Designate that all parameters are OK
    1. Check **Best fit is OK**
    1. Click **All**

<a href='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--16.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--16.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>


  * **Goal**: _Demonstrate issue that some optimized fits are sensitive to initial conditions (especially noisy and/or many data)_
  1. <u>Fit RD</u>
    1. Fit without rate constraints
    1. (1a) Procedure: **Individual**
    1. (1b) Task: **Optimize fit**
    1. Uncheck **Use Arrhenius**
    1. (2) Individual initial conditions

| **Temp(C)** 	| **PA(%)**	| **kex(/s)**	|
|:-------------|:----------|:------------|
| 25		         | 90		      | 2000		      |
| 32		         | 90		      | 2000		      |
| 37		         | 90		      | 2000		      |

| **Curveset**	| **dwH(ppm)**	| **dwX(ppm)**	|
|:-------------|:-------------|:-------------|
| Cp(Leu 22\delta1)| 0.1	         | 1		          |
| Cp(Leu 22\delta1)| 0.1	         | 1		          |

  1. Click **Go!** (50-100 sec)
  1. (3) Select `Fit-1[--]` fit result
  1. (6) Designate that all parameters are OK
    1. Check **Best fit is OK**
    1. Click **All**

  * **Observe**: _This optimized fit is significantly different than pevious `Fit-1[--]`_

| **Fit**	| **PA(%)** 	| **kex(/s)**	| **Chi2**	|
|:--------|:-----------|:------------|:---------|
| First	  | 87.4		     | 1094.0	     | 394.78	  |
| Second	 | 79.3		     | 1179.9	     | 457.38	  |

  * There are systematic ways to assess quality of fit [below](Tutorial#Assess_quality_of_fit.md)
  * Close <u>Fit RD</u> window


<a href='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--17.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--17.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

  * **Save the session often**
    1. <u>Main</u>
      1. **Output...Save session as...**

#### Perform batch task ####
  * **Goal**: _Fit several groups sequentially to obviate need for user input_
  1. <u>Main</u>
    1. **Analysis...Batch task...**
  1. <u>Batch</u>
    1. Select groups for analysis
      1. Highlight rows corresponding to each group
      1. Click **Include** button
      1. **Note**: _The checkboxes are read-only (not clickable, sorry!)_
    1. Specify the task
      1. Grid search: **Optimize fit**
      1. Use Arrhenius: **Unchecked**
  1. **Note**: _Fixing Arrhenius analysis adds two more dimensions to the grid search (dH and Eab)_
    1. Errors: **Unchecked**
    1. Click on any one row to specify grid search limits

| 		| **dwH(ppm)**	| **dwX(ppm)**	| **PA0(%)**	| **kex0(/s)**	|
|:--|:-------------|:-------------|:-----------|:-------------|
| **Min** 	| 0.01  	      | 0.1  	       | 80  		     | 500  	       |
| **Max** 	| 0.1  	       | 3.00  	      | 99.9  	    | 3000  	      |
| **Steps**	| 1  		        | 2  		        | 2  		      | 3  		        |

  * **Note**: The tutorial file included in GUARDD v.2011.09.11 session uses **Steps** = 2, 3, 5, 5 for a total of 150 points, instead of **Steps** = 1, 2, 2, 3 (60 points) shown here in v.2011.07.01

  1. Click **Save to Selected** to save thid grid to all of the groups in the batch
  1. Estimate time required
    1. _This calculator will help plan the time required for an estimated steptime_
    1. _As seen in the tutorial, each fit step may take 5-100 sec, depending on the size of data and accuracy of initial conditions_
    1. Estimate **10 sec/step**, for a total of **~20 min**
  1. Click **Go!**

  * **Note**: _After each group step is done, a session file `GUARDD-Session--Batch_Progress.mat` is written to the default output directory_
    * This was designed for two purposes
      1. In case the program crashes, progress is saved
      1. Allows the user to start a batch task on one computer (e.g., at work), then download/view the results remotely on another computer (e.g., at home)

<a href='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--18.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--18.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>


### Time for a break? ###
  * _This is a good stopping point in the tutorial, in case you want to resume later_
  * _The batch task does not need to be completed_
  * _The tutorial proceeds using a pre-saved GUARDD session_

<a href='http://chemistry.osu.edu/~foster.281/guardd/tutorial/take-a-break-from-work.jpg'> <img src='http://chemistry.osu.edu/~foster.281/guardd/tutorial/take-a-break-from-work.jpg' alt='[UNLOADED IMAGE]' width='200'> </img> </a>



### Assess quality of fit ###
  * **Goal**: _Determine how well RD parameters are determined and which parameters are OK_
    * Increasingly challenging for larger and/or noisier datasets

  * **Methods of assessment**
    1. Check fit to data and the resulting **residuals**
      1. A well-determined fit yields residuals randomly distributed about zero (i.e., not systematically shaped)
    1. Check sensitivity of fit to initial conditions (**grid search**)
      1. A well-determined fit is insensitive to initial conditions
    1. Check sensitivity of fit to errors in data (**Monte Carlo errors**)
      1. A well-determined fit yields a narrow set of MC-fits from Monte Carlo analysis
    1. Check **exchange-timescale** parameter α
      1. Fast exchange (k<sub>ex</sub>>>Δω; α→2.0) precludes knowledge of P<sub>A</sub> and Δω
      1. This is often evident in prior steps

  * **Goal**: _Load GUARDD session with data already fit_
  1. <u>Main</u>
    1. **Input...Load session...**
      1. Select tutorial file: `tutorial/data/GUARDD-Session-Tutorial.mat` (or `GUARDD-Session--Tutorial-After_Break.mat` in v.2011.09.11
    * This session contains data from above, with completed 60-point grid search and MC errors
    * Focus on two examples
    1. **Leu 22delta1**, a good fit with known parameters
      * Medium dataset (10 curves)
      * α = 1.0: intermediate exchange
      * Grid search: fit **is** sensitive to ICs, but well-defined solution at min(χ<sup>2</sup>)
      * MC Errors: model example, symmetric about optimum solution
      * Parameters: All are known
    1. **Ile 43**, a good fit with unknown parameters
      * Small dataset (4 curves)
      * α = 1.4-1.9: fast exchange
      * Grid search: two solution with different values
      * MC Errors: very wide, reflecting many fitting soltuions
      * Parameters: P<sub>A</sub> and Δω unknown

#### View fit and residuals ####
  * **Goal**: _View the RD fit and residuals to help assess fit quality_
  * Confer prior tutorial steps on using the <u>Display RD</u> window [here](Tutorial#View_fits_to_RD_data.md)

<a href='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--12.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--12.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

#### View Grid Search Chi2 Map for good fit ####
  * **Goal**: _Assess the extent to which fitting is sensitive to initial conditions_
  * **Key info on features of chi2 maps**
    * A Chi2 map displays a set of parameter values (e.g., for k<sub>ex</sub>) on the X-axis and the goodness of fit (χ<sup>2</sup>) associated with that value on the Y-axis
    * The most precise fit is at the min(χ<sup>2</sup>)
    * Chi2 maps take a variety of shapes, such as ".", "U", "W", and "-"
    * **Details**: Read more in the [Manual](Manual#Grid_search.md)

<a href='http://chemistry.osu.edu/~foster.281/guardd/manual/figure-chi2_maps/figure-chi2_maps.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd/manual/figure-chi2_maps/figure-chi2_maps.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

  * **Goal**: _Use both_<u>Chi2 Map</u> window and <u>Fit RD</u> window to view data_1._<u>Main</u>
    1. Select **Leu 22delta1**
    1. **Output...Display chi2 map...**
    1. **Analysis...Fit dispersion...**
  1. <u>Chi2 Map</u>
    1. **Parameters**: dwH, dwX, Pa, kex
    1. **Curveset (Curve)**: 800-MQ-25C, 800-MQ-32C, 800-MQ-37C
    1. **Top%** slider all the way to the top (100%)
    1. **Fit**: `* FIT-G[--] Chi2=93.33`
    1. **Task to Display**: Grid Search
    1. **Results to Display**: Final
    1. **Display Mode**: Scatter

  * **Goal**: _Interpret the **Grid Search** results the_<u>Chi2 Map</u> window_1. Each subplot shows a single parameter on the X-axis, and its different values in different fits
    1. Each **black point** corresponds to ONE optimized fit result
      1. There are 60 fits in this example (hence 60 points in each subplot), each of which started from a different location in parameter space (**note** tutorial file in GUARDD v.2011.09.11 uses 150 points instead of 60)
      1. Those initial locations can be displayed by setting **Results to display**: Initial
    1. The **red circle** designates the currently selected fit result
    1. The **blue square** designates the best fit from the grid search
    1. Clicking **Pick grid fit** will allow selection of any of the grid fits shown
      1. The **green diamond** designates the currently selected fit from the displayed grid list
      1. Any of these can be added to the list of fits, if desired_

<a href='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--20.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--20.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

  * **Observe**: _The fit to the no exchange model is inappropriate_
    1. <u>Chi2 Map</u>
      1. Select **Fit**: `NoEx[--]`
      1. The χ<sup>2</sup> = 2163.58, which is very large
      1. The 60 optimized fits are well below this value
    1. <u>Fit RD</u>
      1. Select **Fit**: `NoEx[--]`
      1. The fit is a poor representation of the data

  * **Observe**: _The best fit is appropriate since the chi2 map remains U-shaped near the best result_
    1. <u>Chi2 Map</u>
      1. Select **Fit**: `* FIT-G[--] Chi2=93.33`
      1. Move the **Top%** slider down to 50% in 4-6 small steps
      1. **Observe**: _The chi2 map remains U-shaped even as the poorest fits are eliminated from display_

<a href='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--21.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--21.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

#### View Monte Carlo Errors Chi2 Map for good fit ####
  * **Goal**: _Assess the extent to which fitting is sensitive to noise in the data_
  * **Key info on Monte Carlo analysis**
    * The goal of MC analysis is to generate and fit many **synthetic** datasets which differ from one another by an amount related to the goodness of fit to the original data
    * Each synthetic dataset will have a different set of optimal fit values (e.g., P<sub>A</sub>, k<sub>ex</sub>)
    * The distribution of fitted values reflects the degree to which the original data define its **own** optimal values
    * Example: A worse optimal fit to the original data yields **more different** MC datasets and therefore **more different** optimal parameter values
    * **Details**: Read more about Monte Carlo error estimation in the [Manual](Manual#Monte_Carlo_error_estimation.md)

<a href='http://chemistry.osu.edu/~foster.281/guardd/manual/figure-monte_carlo/figure-monte_carlo.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd/manual/figure-monte_carlo/figure-monte_carlo.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

  1. <u>Chi2 Map</u>
    1. Make sure **Fit**: `* FIT-G[--] Chi2=93.33` is selected
    1. Set **Top%** slider all the way to the top (100%)
    1. **Task to Display**: MC Errors
    1. **Results to Display**: Final
    1. **Display Mode**: Scatter

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

<a href='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--22.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--22.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

  * **Observe**: _The symmetry of the MC chi2 maps indicate reliable estimation of error, and is consistent with reasonable parameter values_
    * The scatter plot illustrates a circular distribution about the optimal result
    * The histogram is roughly symmetric, and is well-described by the standard deviation

<a href='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--23.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--23.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>


#### View Grid Search Chi2 Map for fit with uknown parameters ####
  * **Goal**: _Illustrate features of Grid Search and MC Errors which correspond to a partially-defined fit_
  * **Ile 43**, a good fit with unknown parameters
    * Small dataset (4 curves)
    * α = 1.4-1.9: fast exchange
    * Grid search: two solution with different values
    * MC Errors: very wide, reflecting many fitting soltuions
    * Parameters: P<sub>A</sub> and Δω unknown

  1. <u>Main</u>
    1. Select **Ile 43 delta1**
    1. **Output...Display chi2 map...**
    1. **Analysis...Fit dispersion...**
  1. <u>Chi2 Map</u>
    1. **Parameters**: dwH, dwX, Pa, kex
    1. **Curveset (Curve)**: 800-MQ-25C
    1. **Top%** slider all the way to the top (100%)
    1. **Fit**: `* FIT-G[--] Chi2=20.49`
    1. **Task to Display**: Grid Search
    1. **Results to Display**: Final
    1. **Display Mode**: Scatter
  * **Observe**: _The grid search illutrates solutions at two distinct points_

<a href='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--26.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--26.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

  * **Goal**: _Add the higher-χ<sup>2</sup> fit to the fit list for further inspection_
  1. <u>Chi2 Map</u>
    1. Check **Pick grid fit**
    1. Scroll to the right, and select fit number 60, chi2=20.9464 (or number 93, 20.9456 in v.2011/09/11)
      1. The green diamond should highlight this fit
    1. Click **Add to list**
      1. The fit `FIT-G[--] Chi2=20.95` is now highlighted by the green diamond and red circle (since it is selected)
  1. <u>Fit RD</u>
    1. (3) SELECT the new fit `FIT-G[--] Chi2=20.95` from the list
      1. **Note**: if it is not shown, the list can be update by re-selecting any fit on the list (then check again)
    * **Observe**: _These two fits both appear to go through the data! (which one is best?)_
    * **Note**: Residuals can be compared using the <u>Display RD</u> window

  * For now, we will continue to analyze the lower-χ<sup>2</sup> fit

<a href='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--27.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--27.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>


#### View Monte Carlo Errors Chi2 Map for fit with uknown parameters ####
  * **Goal**: _Illustrate features of Grid Search and MC Errors which correspond to a partially-defined fit_
  1. <u>Chi2 Map</u>
    1. Make sure **Fit**: `* FIT-G[--] Chi2=20.49` is selected
    1. Set **Top%** slider all the way to the top (100%)
    1. **Task to Display**: MC Errors
    1. **Results to Display**: Final
    1. **Display Mode**: Scatter
    * **Observe**: _A wide range of Δω and P<sub>A</sub> values can describe these data → Δω and P<sub>A</sub> are not OK!_
    1. Close <u>Chi2 Map</u> window

<a href='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--28.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--28.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

  * **Goal**: _Mark these parameters as "Not OK" in the_<u>Fit RD</u> window_1._<u>Fit RD</u>
    1. (3) SELECT the fit `* FIT-G[--] Chi2=20.49` from the list
    1. (6) Designate which elements of this fit are OK
    1. **Exchange**: check
    1. **Best fit is OK**: check
    1. Click **Set best fit**, if possible (should be "best" already)
    1. Cilck **All**
    1. **Group parameters**: uncheck PA
    1. **Curveset parameters**: uncheck both dwH and dwX
    1. Make note of this in the **(5) Log notes for group** panel (_or take note of the current note_)
    1. Close <u>Fit RD</u> window

<a href='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--29.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--29.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

#### Document notes for organization ####
  * **Goal**: View and maintain organized notes for interpreting fit results
    1. <u>Main</u>
      1. **Analysis...Notes...**
    1. <u>Notes</u>
      1. Notes on groups are edited in the <u>Fit RD</u> window
      1. Notes on the session can be created and edited in the <u>Notes</u> window
      1. Close the <u>Notes</u> window

<a href='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--19.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--19.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

### Output results ###
  * **Goal**: _Aggregate and output any/all results for dissemination_

#### View results in display cluster ####
  * **Goal**: _Visual display of results from all groups_

  * **Goal**: _Load GUARDD session with data already fit (in case this has not been done already)_
  1. <u>Main</u>
    1. **Input...Load session...**
      1. Select tutorial file: `tutorial/data/GUARDD-Session-Tutorial.mat` (or `GUARDD-Session--Tutorial-After_Break.mat` in v.2011.09.11
      * This session contains data from above, with completed 60-point grid search and MC errors (150 point grid for tutorial file in GUARDD v.2011.09.11)

  * **Goal**: _Create two display groups to compare different fiting constraints_
  1. <u>Main</u>
    1. **Output...Display group results...**
  1. <u>Groups</u>
    1. Click **New**
    1. Set **name**: Isolated fits
    1. Click **Save**
    1. Panel _All Groups_, select all groups _except_ Leu 22
    1. Click **Add**
    1. Click **New**
    1. Set **name**: Group fits
    1. Set _RGB_ to 1 0 0 (for the color Red)
    1. Click **Save**
    1. Panel _All Groups_, select _only_ Leu 22
    1. Click **Add**

  * **Goal**: _Compare individual fits from each NMR probe to form candidate groups, identify outliers, etc._
  1. <u>Groups</u>
    1. Panel _Display settings_
    1. Select **plot type**: _Kinetic rate (25C)_
      1. **Note**: Differences in k<sub>A</sub>, k<sub>B</sub> values indicates the extent of site-specific motion in the protein_1. **Note**: Global fit for Leu 22 (red) is close to both individual fits for Leu 22δ\_1 and Leu 22δ\_2 (blue)
    1. Set **Subplots**: Rows=2, Cols=1
    1. **Plot number**:_Subplot 01_1. **Type**:_Custom_1. **Y-Axis**:_kex_,_25C_1. **X-Axis**:_Residue_1. **Plot number**:_Subplot 02_1. **Type**:_Custom_1. Check **Show Histogram**
      1. **X-Axis**:_kex_,_25C_1. Click the **Save Figure** icon in the title bar
      1._GUARDD will prepare a filename for saving, and you must type the file extension_1. Type **ps** to save as a postscript file and click **Save** (or hit **Enter**)
    1. Close_<u>Groups</u> window
  * **Bug**: Selecting **dwX\_ppm** results in an error involving `iscolumn()` in some versions of MATLAB (at least R2009a on Windows)

<a href='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--24.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--24.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

#### View results in table ####
  * **Goal**: _Aggregate and output any/all results for dissemination_
  1. <u>Main</u>
    1. **Output...Display results table...**
  1. <u>Results Table</u>
    1. Select all display parameters in left-most list
    1. Select all conditions in the following three lists
  1. Click **Export to CSV** [details](FileFormats#Output:_Parameter_Table.md)

  * **Bug**: Selecting all items in the table results in an error in some versions of MATLAB (at least R2009a on Windows)

<a href='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--25.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--25.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

#### Export data and groups ####
  * **Goal**: _Aggregate and output results for dissemination_
  1. <u>Main</u>
    1. **Input...Data manager...**
  1. <u>Data Manager</u>
    1. **Output...Datasets...**
      1. Save the file [details](FileFormats#Output:_Datasets.md)
      * This copies all imported datasets
    1. **Output...Groups...**
      1. Save the file [details](FileFormats#Output:_Groups.md)
      1. Contains all groups, curvesets, and curves created for analysis

### Simulate and export RD data ###
  * **Goal**: _Explore the nature of RD phenomena_
  * **Question**: _What are limits of detection (i.e., when is R<sub>ex</sub>>0)?_

#### Simulate multi-field dataset ####
  * **Goal**: _Simulate a simple dataset at two magnetic fields_
  1. <u>Main</u>
    1. **Input...RD Simulator...**
  1. <u>RD Simulator</u>
    1. _Create a new SimCurveset, which specifies kinetics and chemical shifts for all curves within_
      1. CURVESETS: Click **New**
      1. Set **Name** to _Simple_
      1. Click **Save**
    1. _Create a new SimCurve, which specifies NMR conditions for simulation_
      1. CURVES: Click **New**
      1. Set **B0(MHz)** to _500_
      1. CURVES: Click **New**

<a href='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--Sim-01.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--Sim-01.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>


#### Simulate multi-field, multi-temperature dataset ####
  * **Goal**: _Simulate a dataset at two magnetic fields and three temperatures_
  1. <u>RD Simulator</u>
    1. _Create a new SimCurveset_
      1. CURVESETS: Click **New**
    1. _Create two new SimCurves at 15C (500 MHz and 800 MHz)_
      1. CURVES: Click **New**
      1. Set **Temp(C)** to _15_
      1. Set **B0(MHz)** to _500_
      1. CURVES: Click **New**
      1. Set **Temp(C)** to _15_
    1. _Create two new SimCurves at 25C (500 MHz and 800 MHz)_
      1. CURVES: Click **New**
      1. Set **B0(MHz)** to _500_
      1. CURVES: Click **New**
    1. _Create two new SimCurves at 35C (500 MHz and 800 MHz)_
      1. CURVES: Click **New**
      1. Set **Temp(C)** to _35_
      1. Set **B0(MHz)** to _500_
      1. CURVES: Click **New**
      1. Set **Temp(C)** to _35_

<a href='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--Sim-02.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--Sim-02.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>


#### Explore experimental condtions for observing RD ####
  * **Goal**: _Explore the nature of RD phenomena using surface plot_
    * **Note**: _Please complete prior tutorial section before proceeding_

  * **Question**: _What temperature range is appropriate for acquisition?_
  1. <u>RD Simulator</u>
    1. Display settings: click **3D** angle
    1. Set **Y-Axis Parameter** to _Temp_
    1. Check **Show surface**
    1. **Observations**
      1. _For these exchange kinetics, the largest dispersions are observed around 10-20C, and therefore experiments should be focused there_
      1. _The RD curve is nearly undetectable above 50C because k<sub>ex</sub> is too large compared to Δω<sub>X</sub>(Hz)_

  * _Change chemical shift to observe the effect on the RD signal_
    1. CURVESET: Set **dwX(ppm)** to _0.50_
    1. **Observations**
      1. _With smaller Δω<sub>X</sub>(ppm), the dispersions are smaller, because k<sub>ex</sub> is larger in comparison_
    1. CURVESET: Set **dwX(ppm)** back to _1.00_

  * _Change magnetic field strength to observe the effect on the RD signal_
    1. CURVE: Set **B0(MHz)** to _1000_
    1. **Observations**
      1. _At higher field strength, dispersions are larger, becuse Δω<sub>X</sub>(Hz) is increased_


<a href='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--Sim-03.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--Sim-03.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

#### Explore temperature-dependence of exchange kinetics ####
  * **Goal**: _Explore the nature of exchange kinetics using the_<u>Kinetic Simulator</u>_* **Note**:_Please complete prior tutorial section before proceeding

  1. <u>RD Simulator</u>
    1. _Start the Kinetic Simulator_
    1. CURVESET: Click **Run Kinetics Sim**
  1. <u>Kinetic Simulator</u>
    1. _This window operates on the Sim Curvesets, and displays the effect of temperature on the RD parameters P<sub>A</sub> and k<sub>ex</sub>_
    1. Select **SimSet 2** from the pull-down menus
    1. _Alter the kinetic parameters in the **Input Kinetic Specifications** table_
      1. Set **dH** to _5_
      1. _Now, P<sub>A</sub> will decrease with increasing temperature_
      1. Set **Eab** to _15_
      1. _This ensures that k<sub>ex</sub> still increases with temperature_
    1. _Check the **Kinetic Report** for the quantitative values of exchange parameters_
      1. Set **Input temperature** to _50_
      1. **Observe**: _P<sub>A</sub> is 82.4% and k<sub>ex</sub> is 4039.7 /s_

  * _Check this effect on the simulated RD surface plot_
  1. <u>RD Simulator</u>
    1. Click the **Refresh display** icon in the title bar
    1. **Observe**: _The RD signal now **increases** with temperature, becuase the population of the minor state, P<sub>B</sub> = (1-P<sub>A</sub>), becomes larger at higher tempertures_

  1. <u>Kinetic Simulator</u>
    1. Close the window (X)

<a href='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--Sim-04.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--Sim-04.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>

#### Export simulated data ####
  * **Goal**: _Assess accuracy of fitting procedure by analyzing data with "known" solution_
    * **Note**: _Please complete prior tutorial section before proceeding_

  1. <u>RD Simulator</u>
    1. Click the **Export** icon in the title bar
  1. <u>RD Simulator Export</u>
    1. Set **Sim Points** to _15_
    1. Click **Export to TXT**
      1. Save the file [details](FileFormats#Output:_GUARDD_Simulator.md)
  1. <u>RD Simulator</u>
    1. Click the **Export** icon in the title bar
    1. Set **Sim Points** to _15_
    1. Click **Export to GUARDD**
      1. _This automatically creates a Group for each simulated Curveset_

  * **Note**: _Simulated groups can be viewed in the_<u>Main</u> window and/or the <u>Data Manager</u>, just like any other group_1. Fitting can be accomplished as per the [simple group](Tutorial#Fit_simple_group_manually.md) or for the [multi-temperature group](Tutorial#Fit_multi-temperature_group_manually.md)
    1. Fits of these data should achieve within 10% accuracy of the simulation conditions_


<a href='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--Sim-05.png'> <img src='http://chemistry.osu.edu/~foster.281/guardd/tutorial/tutorial-GUARDD-2011.06.17--Sim-05.png' alt='[UNLOADED IMAGE]' width='200'> </img> </a>


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

## Author ##
  * (C) [Ian Kleckner](http://ianrobertkleckner.blogspot.com)

  * Work completed as part of PhD Dissertation
  * Mark Foster's Lab
  * The Ohio State University
  * Columbus, OH, USA