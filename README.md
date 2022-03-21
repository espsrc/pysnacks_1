# PySnacks 1  - Astronomical Data Science with Python

The PySnacks 1 virtual workshop is the first event of the IAA Severo Ochoa Training Initiative `PySnacks`, which consists on a series of workshops on 
the use of Python packages for astrophysics and space science.

The purpose of the workshop is that you become familiar with astronomical software tools of general use. We will start with essential information, and we will build up in complexity until we apply machine learning algorithms and we measure physical parameters relevant to our problem. The thread joining the narrative will be the identification and analysis of the Open Cluster M44, so the plan is to apply everything we learn to a real scientific case. The workshop will be mainly practical, so you are supposed to work and solve the guided exercises yourself. The topics covered in this workshop will be:

- Astropy fundamentals: Quantities, units and Tables
- Astropy. Manipulation of coordinates and reference frames
- Astroquery. Accessing Vizier catalogs
- Plotting with matplotlib
- Exploratory data analysis. Pandas dataframes
- Query Virtual Observatory catalogs with ADQL
- Clustering analysis with Scikit-Learn. KMeans and DBSCAN methods
- Introduction to using isochrones templates

# Course contents and materials
PySnacks 1 consist of four sessions that will take place on 22, 25, 29 March and 1 April, 2022 from 10am to 1pm (CET):

Session 1 - 22nd March 2022  
[Tutorial 01 notebook](./tutorials/tutorial_01/pysnack_1_01.ipynb)

 - Astropy Quantities, units
 - Coordinates and reference frames
 - Astroquery and accessing Vizier
 - Querying and downloading Gaia data
 
Session 2 - 25th March 2022  
[Tutorial 02 notebook](./tutorials/tutorial_02/pysnack_1_02.ipynb)

 - Tables for scientific analysis: Astropy and Pandas tables 
 - Plotting with matplotlib
 - Exploratory data analysis

Session 3 - 29th March 2022
[Tutorial 03 notebook (TBD)](./tutorials/tutorial_03/pysnack_1_03.ipynb)

 - Introduction to ADQL queries
 - Advance plotting
 - Manipulating coordinates. Change of reference frames.

Session 4 - 1st April 2022  
[Tutorial 04 notebook (TBD)](./tutorials/tutorial_04/pysnack_1_04.ipynb)

 - Clustering analysis with Scikit-Learn. KMeans and DBSCAN methods
 - Advance visualization and analysis of an HR diagram with isochrones templates.

The session materials are inspired on the Data Carpentry Astronomy Curriculum "Foundations of Astronomical Data Science *beta*" lesson (see https://datacarpentry.org/astronomy-python/), but modified to better tailor the IAA-CSIC participant needs. 

This repository hosts the materials for the workshop and instructions on how to run the tutorials. It also contains a conda environment needed to execute the python notebooks, either locally or in a cloud platform.


# Execution of the tutorials

Tutorials execution will be on Jupyter Lab instances of a dedicated JupyterHub server kindly provided by the Spanish SKA Regional Centre Prototype (SPSRC) at the IAA-CSIC. You need to login to your Jupyter Lab, which will be available until two weeks after the end of the workshop. Your progress will be stored and can be retrieved every time you access the service.

If you prefer to use your own machine, we recommend that you follow the instructions below to make sure you have all the software needed with the right dependency versions.


## Option 1. Execute notebook tutorials in the JupyterHub instance

The IAA-CSIC Severo Ochoa Center provides a JupyterHub server available here:  
https://spsrc-jupyter.iaa.csic.es/pysnacks/

Credentials for the participants will be sent by email before the the workshop begins.

The first time you access, it will take some minutes to create the instance. You can access your instance in `https://spsrc-jupyter.iaa.csic.es/user/<username>/lab/` and you can start by using the navigation bar on the left to open the file `pysnacks_1/tutorials/index.ipynb`.

A lightweight desktop is also available, you can access it immediately by changing lab to desktop in the path. For example go to: `https://spsrc-jupyter.iaa.csic.es/user/<username>/desktop/` and you will have a desktop environment with graphical interface in your browser.

All virtual machines and their contents will be removed by the 18th of April, 2022.

In case of problems using this JupyterHub instance please file an issue at https://github.com/spsrc/pysnacks_1/issues or contact the organizers by email or slack.


## Option 2. Execute notebook tutorials in your local machine

### Install conda

We recommend using `conda` to manage the dependencies. Miniconda is a light-weight version of Anaconda. First we show how to install Miniconda if you don't have it already. More details [here](https://docs.conda.io/projects/conda/en/latest/user-guide/install/linux.html)

Miniconda for Linux:
```bash
curl -O https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
bash ./Miniconda3-latest-Linux-x86_64.sh
rm ./Miniconda3-latest-Linux-x86_64.sh
```

Miniconda for macOS:
```bash
curl -O https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-x86_64.sh
bash Miniconda3-latest-MacOSX-x86_64.sh
rm Miniconda3-latest-MacOSX-x86_64.sh
```

Note that the installation will suggest you to modify your `.bashrc` to make `conda` always available in your terminal, which is a good idea in general. Alternatively, if you want the Miniconda installation to be encapsulated in your working directory without affecting the rest of your system you can install it with the following option. The first command only needs to be done once, and the second one needs to be done everytime you open a new terminal. 

```bash
bash ./Miniconda3-latest-Linux-x86_64.sh -b -p my_conda_env
source my_conda_env/etc/profile.d/conda.sh
```

### Get the contents of the workshop

Download this repository and create conda environment with the dependencies
```bash
git clone https://github.com/spsrc/pysnacks_1.git
cd pysnacks_1
conda env create -f environment.yml
conda activate pysnack_1
```
You can start JupyterLab with:
```bash
jupyter lab
```

## Option 3. Execute the tutorials on myBinder

At any moment, also after the school, you can still run the tutorials in [myBinder.org](https://mybinder.org) following this link: 
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/spsrc/pysnacks_1/main?urlpath=lab/tree/tutorials/index.ipynb)

[myBinder.org](https://mybinder.org) is a free and open organization providing free cloud resources. Therefore, the resources may be limited and the changes you make in the notebooks or the system are not persistent. Please, always keep a local copy of any file you want to keep, because Binder will automatically eliminate the virtual machine assigned to you after some time of inactivity.
