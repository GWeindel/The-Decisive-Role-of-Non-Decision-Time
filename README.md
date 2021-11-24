# Summary
This is the github repo for the [preprint](https://psyarxiv.com/gewb3/) "The Decisive Role of Non-Decision Time for Interpreting Decision Making Models" hosted on [OSF](https://osf.io/t2ar3/) 

It contains all the code used to fit the model used (whether mixed models or drift diffusion model), and all the way the figures and tables were generated

# Structure of the repo
This folder contains all the files for the analysis in the paper.

DDM/ contains all the files needed to fit the DDM to RT and PMT
MixedModels/ contains all the files needed to fit the LME to RT, PMT and MT

About the files : 
- 1-Behavior_EMG.ipynb contains the code necessary to extract LME parameters for RT,PMT and MT and the plots from the models
- 2-a and 2-b plot the QPplot for each DDM model as well as the DIC and BPIC, respectively for PMT and RT
- 3-DDM_analysis.ipynb recovers parameter values for DDM fits on RT and PMT, plots the results and also compare to VI data in monkeys
- EWMA.py contains the exponetnially weighted moving average as coded by Micheal D. Nunez https://github.com/mdnunez/bayesutils/blob/master/wienerutils.py
- HDDM_ModelSelection_pmt.py and HDDM_ModelSelection_rt.py fit all the DDM models used in the model selection procedure from the dataset dataHDDM_pmt.csv or dataHDDM_rt.csv  in the DDM folder. 
- HDDMreg_PMT.py contains the code to fit the regression version of the model selected during the model selection step

# Updates planned :
- add the data 
- add the conda env used for DDM and mixed models