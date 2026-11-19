# AACE-Project-Overview

This project ran from July to November 2026 and focused on investigating and developing a way to view and compare Finite Element Analysis (FEA) results for hip revision implants without access to the specialist software.

AACE Surgical provided ten 3D hip revision models that had been built and solved in Abaqus, which they no longer had access to. Flinders University did not have access to Abaqus either, but has access to an alternate software, Ansys. However, the input files (.inp) and the result files (.odb) can only be opened and run in Abaqus. The project attempted to recover these models, whilst simultaneously making FEA results easier for clinicians and researchers to review, minimising the potential for similar accessibility issues to reoccur later down the line.

Using Ansys Workbench the geometry, materials, assembly and element definitions could be accurately rebuilt. However, the contact and friction behaviour, and interference fits did not have exact Ansys equivalents. Additionally, no attempt at manual reconstruction could run to completion, with multiple errors preventing success. Without the original results, even if a model could be rebuilt in Ansys, it would not be verifiable. This investigation was captured in a python rebuild tool that reads an Abaqus model and outputs step-by-step workbench instructions and geometry for rebuild. Moving forwards, the execution of these instructions may be successful by someone with more expertise with the original results provided for validation.  

Considering this substantial roadblock, the project refocused on processing and visualising results, using a simplified hip revision model built in Ansys. This simple model allowed for two more tools to be developed alongside the python rebuild tool:
-	Ansys Exporter: a python tool which converts a solved ansys result file (.rst) into a single ZIP which contains the 3D mesh, displacement, stress and strain results and model details. This tool needs Ansys to be run, however, the ZIP output is software independent.
-	Results Dashboard: a browser application that opens the software independent ZIP. This dashboard displays an interactive stress, strain and displacement heatmaps. Individual parts can be shown and hidden, and two models can be compared side by side with a shared scale and standardised cup orientation and size.

A local host of the dashboard has been captured under final-vid, displaying a simplified model and a slightly more complex model using realistic geometry, this includes a function which standardizes the size and direction of the cup for effective comparisons.







