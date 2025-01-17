# PC-CMR-derived-CFD-LV-modeling
This repository contains codes to model PC-MRI driven left ventricle (LV) hemodynamics, as detailed in our study "Computational modeling of left ventricular flow using PC-CMR-derived four-dimensional wall motion."

1- NRIR Codes: Contains Matlab codes to capture myocardial strains and endocardial displacement from MRI images.

2- Fluent Codes: Contains UDF files and Matlab codes to map the displacement of nodes acquired from the NRIR method to the Fluent nodes in the software, creating the moving wall boundary condition for use in Fluent.

3- Results_dat_cas_files: Contains the .dat and .cas files resulting from the CFD modeling.

# NRIR
To capture the myocardial strains (radial, circumferential, and longitudinal strains) and endocardial displacements (in X, Y, and Z directions), segment the epicardium and endocardium of the LV. Using the .CSV files, run ing_reg_script to extract displacements and strains from images. Then, run img_reg_postp_cart2pol_script to calculate radial, circumferential, and longitudinal strains. Finally, run data_save to write .dat files.

# fluent codes
In Ansys Fluent, use the Get_Nodes_3D.c UDF in the "Fluent UDFs" directory to extract the node numbers of the geometry. Use the .out file and the NRIR_disp_2_CFD_input Matlab code in the "moving wall" directory to create a .dat file representing the displacement of each node in the Fluent model. Finally, use the Move_By_File_Membrane.c file in the "Fluent UDFs" directory as a UDF to impose the moving wall boundary in Ansys Fluent.


# Results_dat_cas_files
This directory contains our .dat and .cas files resulting from our four-dimensional moving wall CFD modeling.
