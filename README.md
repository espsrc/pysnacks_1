# Pysnacks 1  

Tht PySnacks 1 virtual workshop is the first event of the IAA Severo Ochoa Training Initiative which consists on a series of workshops on 
the use of Python packages for astrophysics/space science called ”PySnacks”. 

PySnacks 1 consist of four sessions dedicated to fundamental packages (Pandas, Astropy, Astroquery) in combination with the Gaia and Pa-STARRS datasets which will take place on 22, 25, 29 March and 1 April 2022 from 10am to 1pm (CET), 

Session 1 - 22nd March 2022
 - Basic queries
 - Coordinate Transformations

Session 2 - 25th March 2022 
 - Plotting and Tabular Data
 - Plotting and Pandas
 - Transform and Select

Session 3 - 29th March 2022
 - Join
 - Photometry

Session 4 - 1st April 2022 
 - Visualization

The session materials are based on the Data Carpentry Astronomy Curriculum "Foundations of Astronomical Data Science *beta*" lesson (see https://datacarpentry.org/astronomy-python/), but modified to better tailor the IAA participant needs. 

This repository hosts the materials for the workshop and instructions on how to run the tutorials. It also contains a conda environment needed to execute the python notebooks, either locally or in a cloud platform.


# Workshop materials

## Session 1
- [Tutorial 1: Basic queries and coordinate transformations](session_01/pysnack_1_01.ipynb)
    
## Session 2
TBC 

## Session 3
TBC

## Session 4
TBC    


# Execution of the tutorials

Tutorials execution will be on a JupyterHub instance at IAA-CSIC. The virtual machines will be served by Jupyter Hub deployed on the host institution (IAA). You need to login to your dedicated machine and the Jupyter instance will be available for two weeks from the end of the workshop. Your progress will be stored and can be retrieved every time you access the service. You can use this service to experiment and work on your own files.

The IAA-CSIC Severo Ochoa Center provides a prototype JupyterHub instance available here:
TBC

Login with user `firstname.lastname` and password `xxxxx`(the password will be sent to your email days before the workshop begins). 

It will take some minutes to create the instance (especially the first time you access). You can access your instance in `https://spsrc-jupyter.iaa.csic.es/user/<username>/lab/` and you can start by using the navigation bar on the left to open the file `pysnacks_1/tutorials/index.ipynb`.

A lightweight desktop is also available, you can access it immediately by changing lab to desktop in the path. For example go to: `https://spsrc-jupyter.iaa.csic.es/user/<username>/desktop/` and you will have a desktop environment with graphical interface in your browser.

All virtual machines and their contents will be removed by the 18th of April, 2022.

In case of problems using this JupyterHub instance please file an issue at https://github.com/spsrc/pysnacks_1/issues



