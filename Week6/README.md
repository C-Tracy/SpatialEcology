Assignment for Lab 6 looking at spatial dependence across a landscape. 

Main tools used:
Correlograms - using ncf::correlog() function, allowing for MCMC resampling and a confidence envelope. 
Semivariograms - using geoR::variog() and geoR::variog.mc.env() functions, calculating a semivariogram and then creating an envelope to calculate a confidence interval for if the data were randomly distributed on the landscape. 
