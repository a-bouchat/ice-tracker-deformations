# Deformations From Sea Ice Tracker Data

## Overview

This project aims at computing arctic sea-ice deformations from icetracker data (Sentinel-1 and RCM). Two distinct methods can be used to compute sea-ice deformations. 

###### Method M00

In the first method, data points with Latitude/Longitude coordinates are processed. A Delaunay triangulation is performed on these data points and the RIOPS grid is used to create local cartesian coordinate systems for each triangular data cell. The triangulated and converted data set is then used to compute sea-ice deformations following *Bouchat et al. (2020)*.

###### Method M01

In the second method, data points with X/Y coordinates are processed. After performing a Delaunay triangulation, we compute sea-ice deformations following *Bouchat et al. (2020)*.

## Installation

Start by cloning the repository:

```
ssh -T git@gitlab.science.gc.ca
git clone git@gitlab.science.gc.ca:bdu002/2021_SeaIceDeformation.git
```

This project uses a **virtual environment**. Start by accessing the project folder:

```
cd 2021_SeaIceDeformation
```

Create and activate the project virtual environment:

```
python3 -m venv .venv --without-pip
curl -sS https://bootstrap.pypa.io/get-pip.py -o get-pip.py
source .venv/bin/activate
python get-pip.py
```

Install the python dependencies on the virtual environment:

```
python -m pip install -r requirements.txt
```

## Usage

In order to launch a data processing experience, the main module must be executed. The user can configure the experience by modifying the definitions of the parameters in namelist.ini.  

## Documentation

To generate PDF documentation for this project, start by accessing the `docs/SeaIceDeformation_Methods` folder (assuming we are already in the project folder):

```
cd docs/SeaIceDeformation_Methods
```

Finally, write the following command:

```
make SeaIceDeformation_Methods.pdf
```

*SeaIceDeformation_Methods.pdf* will be stored in the current directory.
