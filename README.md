# PC-CMR-derived-CFD-LV-modeling
The repository contains codes to model a PC-MRI driven left ventricle (LV) hemodynamics and the results captured in our study "Computational modeling of left ventricular flow using PC-CMR-derived four-dimensional wall motion"
1- "NRIR codes" directory contains the Matlab codes to capture the myocardial strains and endocardial displacement form the MRI images.
2- "fluent codes" directory contains a UDF files and a matlab codes to correspond the displacement of the nodes acquired from the NRIR method to the fluent nodes on software and creat the moving wall boundary conditon to be use in Fluent.
3- "Results_dat_cas_files" directory contatins the dat and cas files resulted from the CFD modeling.
