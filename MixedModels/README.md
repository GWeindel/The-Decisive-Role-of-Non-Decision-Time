 This repo contains all code used for the mixed models reported in the paper :
 
 - data_preparation_G-LME.py is the first executed. It takes the raw data at '../../Markers/MRK_ForceEMG.csv', removes multiple EMG trials and unfinite pre-motor times, recodes participant in a numerical format, correct the coding of force for two participants and then applies an exponentially weighted moving average to censor data points detected as being fast-guesses. Newly generated data is stored as 'data_pre_G-LME.csv'
 - GLMEdata_model_init.py recodes the factor (see manuscript) and writes/compiles the stan model. 'GLMEdata.csv', 'GLME.stan' and 'cached-GLME-b8c8c24dce32113cb317dd428021efdf.pkl' are generated.
 - LMEdata_model_init.py selects only correct responses, takes the log for RT,PMT and MT, recodes the factor and writes/compiles the stan model. 'LMEdata.csv', 'LME.stan' and 'cached-LME-3535856e449ab2df75cb057031a2ad56.pkl' are generated.
 - Each file ending with *fit.py, read the corresponding data, defines the fixed/random effect structure, the priors, fits the stan model and automatically run checks for divergence treedepth reached and energy.
 - FittedModels/ should contain the recording of the models fitted but these were removed due to large files (> 1.5 GB). In order to recreate the fitted LMEs just run the file corresponding to the variable of interest (e.g. RTfit for RTs).
 
