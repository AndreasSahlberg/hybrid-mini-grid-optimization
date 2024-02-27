# Hybrid mini-grid optimization

This repository contains the code to perform an optimization of the generation system of a PV/diesel/hybrid mini-grid system. A Particle Swarm Optimization (PSO) algorithm is applied to search the solution-space and identify the combination of PV capacity, diesel generator capacity and battery capacity that can meet the demand at the lowest cost. The initial methodology is outlined in [this MSc thesis](https://www.diva-portal.org/smash/get/diva2:1197546/FULLTEXT01.pdf), and further improved with the PSO algorithm as described in [this pre-print](https://www.researchsquare.com/article/rs-3043251/v1).

The optimization is done by simulating the system over each hour during one year. To do so, hourly PV resource availability and temperature data is required. A module is developed that automatically retrieves such data from renewables.ninja. To do so, the user needs to provide an access token to the renewables.ninja API - see instructions [here](https://renewables.ninja/documentation).

## Content 
This repository contains:
* The source code of the mini-grid simulation algorithm and PSO implementation
* An environment .yml file needed for creating the python environment to run the scripts using Anaconda.
* Two example notebooks. The first provides an example implementation that optimizes a single settlement, and the second an example implementation that automatically optimizes multiple settlements through a case of Sierra Leone.

## Installing and running the clustering notebook

**Requirements**

The scripts in this repo have been developed in Python 3. We recommend installing [Anaconda's free distribution](https://www.anaconda.com/distribution/) as suited for your operating system.

**Install the clustering repository from GitHub**

After installing Anaconda you can download the repository directly or clone it to your designated local directory using:

```
> conda install git
> git clone https://github.com/AndreasSahlberg/hybrid-mini-grid-optimization.git
```
Once installed, open anaconda prompt and move to your local directory using:
```
> cd ..\hybrid-mini-grid-optimization
```

In order to be able to run the tool you have to install all necessary packages. The "environment.yml" files contains all of these and can be easily set up by creating a new virtual environment using:

```
conda env create --name mgopt --file environment.yml
```

This might take some time. When complete, activate the virtual environment using:

```
conda activate mgopt
```

With the environment activated, you can start by testing the example notebooks in a "jupyter notebook" session by simply typing:

```
..\hybrid-mini-grid-optimization > jupyter notebook 
```