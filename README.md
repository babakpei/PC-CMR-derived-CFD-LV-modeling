# PC-CMR-derived-CFD-LV-modeling
The repository contains codes to model a PC-MRI driven left ventricle (LV) hemodynamics and the results captured in our study "Computational modeling of left ventricular flow using PC-CMR-derived four-dimensional wall motion"

1- "NRIR codes" directory contains the Matlab codes to capture the myocardial strains and endocardial displacement form the MRI images.

2- "fluent codes" directory contains a UDF files and a matlab codes to correspond the displacement of the nodes acquired from the NRIR method to the fluent nodes on software and creat the moving wall boundary conditon to be use in Fluent.

3- "Results_dat_cas_files" directory contatins the dat and cas files resulted from the CFD modeling.

# NRIR
To capture the myocardial strains (radial, circumferential and longitudinal strains) and endocardial displacements(in X, Y, and Z directions), segment the epicardium and endocard of the LV. Then, using the.CSV files, run ing_reg_script to extract displacements and strains from images. After that, run the img_reg_postp_cart2pol_script to calculate radial, circumferential and longitudinal strains. Ffinally, run data_save to write .dat files.

# fluent codes
In Ansys Fluent, use the "Get_Nodes_3D.c" UDF in the "Fluent UDFs" directory to extract the node numbers of the geometry. Use the .out file and the "NRIR_disp_2_CFD_input" matlab code in the "moving wall" directory to creat a .dat file representing the displacemnt of each node in the Fluent model. Finally, use the "Move_By_File_Membrane.c" file n the "Fluent UDFs" directory as UDF to impose the moving wall boundary in the Ansys Fluent.


# Results_dat_cas_files
In this directory we have shared our .dat files and .cas files resulted of our four-dimensional moving wall CFD modeling.
