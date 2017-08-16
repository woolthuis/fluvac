# Influenza vaccination models

This repository contains the models used in Woolthuis, R.G., et al. Variation in loss of immunity shapes influenza epidemics and the impact of vaccination (2017).

The models are implemented in jupyter notebook (see http://jupyter.org/). Versions: Python 2.7.11 |Anaconda 4.0.0 (x86_64)| IPython 4.1.2.

Five models are presented, the basic model and variations/extentions of the basic model:

- The basic model (1).
- One year vaccine protection. Basic model with protection after vaccination lasting only one year (2).
- Model with a leaky vaccine instead of a vaccine giving all-or-nothing protection (3).
- Age-stratified model with three age classes (4).
- The full model with age structure, a leaky vaccine, and two latent and infectious compartments (5).


1. The basic model

    - Functions.ipynb
    
        Contains (common) functions that are used in the other notebooks in /basic.
        
        
    - Timeseries-Plotting.ipynb
    
        Construction of Figure 1. Uses data generated in Timeseries.ipynb and Timeseries-Vaccination.ipynb.
        
        
    - Timeseries.ipynb
    
        Makes figure of the influenza epidemics of multiple seasons, i.e. top figure of Figure 1.
        
        
    - Timeseries-Vaccination.ipynb
        
        Influenza epidemics when introducing vaccination, i.e. bottom figure of Figure 1.
        
        
    - SweepVc.ipynb
    
        Parameter sweep of the basic model. Probability of outbreak, peak prevalence, and attack rates are calculated for various values of vaccination coverage. Output data is written to .dat file.
        
        
    - SweepVc-Plot.ipynb
    
        Data generated in SweepVc.ipynb is plotted. Here Figure 2 and Figure 3 are constructed using this data.
        
        
    - Correlations.ipynb
    
        Calculate correlations between successive susceptibilities in timeseries of seasonal epidemics. This analysis results in the correlation plot, i.e. Figure 4.
    
    
    - SuscAttackPlot.ipynb
    
        Construction of Supplementary Figures (Fig S1 and Fig S2).
        



2. One year vaccine protection.

    - Functions.ipynb
    
        Contains some functions that are used in the other notebooks in /oneyear.
    
    
    - SweepVc.ipynb
    
        Parameter sweep of the one year vaccine protection model. Similar as the SweepVc.ipynb of the basic model.
        
        
    - SweepVc-Plot.ipynb
    
        Data generated in SweepVc.ipynb is plotted. Similar as the SweepVc-Plot.ipynb of the basic model. Results in Figure S3.
        
        
        
        
3. Leaky vaccine model.

    - Classes.ipynb
    
        Classes for the leaky vaccine scenario. Note that the basic model is recoverd by setting Ve = 0.5 and Vr = 1.0. Contrasting the models above, here we use a class for each time series calculated. As the complexity of the models increase, it is easier to use classes as structure. The classes can be saved and opened using the python module 'pickle'.
        
    - LeakyFunctions.ipynb
    
        Contains some functions that are used in the other notebooks in /leaky. Because of the use of the Timeseries class, the functions here differ considerably from Functions.ipynb in models 1 en 2.
        
        
    - SIR-FinalsizeEquation-Check.ipynb
    
        Compares the results from the final size equations with the ODE-system. Used to find potential coding errors.
        
        
    - SweepVc.ipynb
    
        Parameter sweep of the leaky vaccine model. Now with saving the timeseries in the Timeseries class.
        
        
    - SweepVc-Plot.ipynb
    
        Data generated in SweepVc.ipynb is plotted. Similar as the SweepVc-Plot.ipynb of the basic model. Results in Figure S5.
        



4. Age-stratified model.

    - Classes.ipynb
    
        Timeseries class for age-stratified model. Similar, but slightly different from Classes.ipynb in leaky vaccine model.
        
        
    - AgeFunctions.ipynb
    
        Functions used in /age. Contains the final size calculations using contact matrix.
        
      
    - SIR-FinalsizeEquation-Check.ipynb
    
        Comparing final size equations with the age-stratified ODE-system (SIR model). Is a check for coding errors.
        
        
    - SweepVc.ipynb
    
        Parameter sweep of the age-stratified model. Similar as /leaky/SweepVc.ipynb.
        
        
    - SweepVc-Plot.ipynb
    
        Data generated in SweepVc.ipynb is plotted. Output is Figure S6.
        
    - SweepVc-Plot-All.ipynb
    
        Uses SweepVc.ipynb generated data in /age and /leaky, to construct Figure S4
        
        
        
        
5. The full model

    - Classes.ipynb
    
        Timeseries class, specified to the full model.

    - SEEIIR.ipynb
    
        Notebook to simulate a single season using the SEEIIR (full) model.
        
    
    - SEEIIRfunctions.ipynb
    
        Functions used in /full, contains function to simulate multiple seasons with the SEEIIR model.
        
    
     - SweepVc.ipynb
    
        Parameter sweep of the full model. Similar as /leaky/SweepVc.ipynb.
        
        
    - SweepVc-Plot.ipynb
    
        Data generated in SweepVc.ipynb is plotted. Output is Figure 5.
        
        
    - Calculating-Reffective.ipynb
    
        Extra notebook to calculate the effective reproduction number.
        
    
