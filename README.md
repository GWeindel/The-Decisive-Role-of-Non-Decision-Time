# Summary
This is the github repo for the [preprint](https://psyarxiv.com/gewb3/) "The Decisive Role of Non-Decision Time for Interpreting Decision Making Models" hosted on [OSF](https://osf.io/t2ar3/) 

It contains all the code used to fit the models (mixed or drift diffusion models) draw the figures and generate the tables of the paper.

# Structure of the repo

DDM/ contains all the files for the estimation of the DDM to RT and PMT

MixedModels/ contains all the files needed to fit the LME to RT, PMT and MT

About the files : 
- 1-Behavior_EMG.ipynb contains the code necessary to extract LME parameters for RT,PMT and MT and the plots from the models
- 2-a and 2-b plot the QPplot for each DDM model as well as the DIC and BPIC, respectively for PMT and RT
- 3-DDM_analysis.ipynb recovers parameter values for DDM fits on RT and PMT, plots the results and also compare to V1 data in monkeys
- EWMA.py contains the exponentially weighted moving average as coded by Micheal D. Nunez https://github.com/mdnunez/bayesutils/blob/master/wienerutils.py
- HDDM_ModelSelection_pmt.py and HDDM_ModelSelection_rt.py fit all the DDM models used in the model selection procedure from the dataset dataHDDM_pmt.csv or dataHDDM_rt.csv in the DDM folder. 
- HDDMreg_PMT.py contains the code to fit the regression version of the model selected during the model selection step

# Instructions for reproducing the analyses
In order to use the main notebooks you can install anaconda https://docs.anaconda.com/anaconda/install/index.html and install the packages listed in spec-file_pystan.txt. If you are on a linux 64 machine simply use the specification file "spec-file_pystan.txt" to exactly match the installation used for the results of the paper : 
 1. Installing conda env (assuming anaconda is installed) :
 1.1    - for a linux 64 machine run the following command in a terminal to exactly match the package installation used for the analysis : $ conda create --name pystan --file spec-file_pystan.txt or do a fresh install as for windows
 1.2    - If you're a windows/mac user, if a URL is broken or if you want a lighter version of the environment, type : $ conda create env -n pystan python=3.8.5 pystan=2.19.1.1 arviz-0.10.0 jupyterlab=2.2.8
 2. activate the environment through : $ conda activate pystan
 3. launch Jupyter lab (recommended) : $ jupyter lab
 4. launch any .ipynb in the main or the MixedModels folder except the files starting with HDDM*, see below.

Fitting drift diffusion models (DDM) required python 2.7.15 and HDDM 0.6. To ease reproducibility we extracted the traces and statistics of the MCMC chains from the DDM models to .csv contained in DDM/. If you want to reproduce the fits you can do this by creating a new anaconda environment from the "spec-file_hddm.txt", either manually or automatically on linux 64 :
 1.Installing conda env (assuming anaconda is installed) :
     - $ conda create --name hddm --file spec-file_hddm.txt
     - for windows/mac users or if you want a lighter version of the environment : $ conda create env -n hddm python=2.7.15 hddm=0.6.0 jupyterlab=0.33.12
 2. activate the environment through : $ conda activate hddm
 3. launch Jupyter lab (recommended) : $ jupyter lab
 4. launch any .ipynb or .py in the DDM/ folder

Finally, the 

## Note on computation time
On a single CPU with (current) average speed, a single MCMC for the linear mixed model takes approximatively 4 hours. The MCMC from the hddm package are however notoriously slow and the regression model can take up to one month given the high number of burn-in samples. One way to fasten this estimation is to reduce the number of burn-in samples, from our experience the inferences should be the same albeit noisier. 

The computation time of all other files are not noteworthy.

# Updates planned :
- add the data 
- add the experiment creation code
