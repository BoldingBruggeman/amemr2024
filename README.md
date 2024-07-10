# AMEMR 2024 modelling workshop

The software we will use for this workshop is available for Windows, Mac (Intel and Apple CPUs) and Linux.
It does not require administrator/root privileges to install.

We will work in a terminal window while installing necessary files and running the models.
On Windows, use the "Anaconda prompt" from the start menu (instructions on how to install that below).

We will be editing text files (yaml files and Python scripts) with model configurations. This can be done with many different editors, e.g., [Visual Studio Code](https://code.visualstudio.com/), Notepad on Windows, `vi` on Linux/Mac. We recommend using one you are already familiar with.

## Installation

### Step 1. Anaconda

Ensure you have Anaconda:
- Linux/Mac: execute `conda --version` in a terminal
- Windows: look for “Anaconda prompt” in the start menu

If you *do not* have Anaconda, [install Miniconda](https://docs.anaconda.com/miniconda/miniconda-install/).

### Step 2. Install the water columnn model

1. Create an isolated `amemr` environment with the water column model and visualization tools.
   To do this, open a terminal window (on Windows, use the "Anaconda prompt" from the start menu) and type:
   ```
   conda create -n amemr -c conda-forge -y gotm pyncview
   ```

   If you experience any issue with the above, we recommend you first execute `conda update conda` to ensure your conda is up to date.
   Should this fail because of lack of permissions, we recommend you [install Miniconda](https://docs.anaconda.com/miniconda/miniconda-install/).
   After you have an up-to-date conda, retry the `conda create ...` command.

   The above command installs a pre-compiled version of [GOTM](https://gotm.net), which include reference versions of the biogeochemical models [ERSEM](http://ersem.com), [ECOSMO](https://doi.org/10.5194/gmd-15-3901-2022), [PISCES](https://www.pisces-community.org/), [iHAMOCC](https://doi.org/10.5194/gmd-13-2393-2020), [ERGOM](https://ergom.net/), and [MOPS](https://doi.org/10.5194/gmd-8-2929-2015), among others.

2. Test your installation by running the following in a terminal window:
   ```
   conda activate amemr
   gotm --version
   multiplot --version
   ```
   These three commands should complete without errors.

### Step 3. Install 3D offline simulator

1. Install FABM Offline Simulator in your isolated `amemr` environment.
   To do this, open a terminal window (on Windows, use the "Anaconda prompt" from the start menu) and type:
   ```
   conda install -n amemr -c conda-forge -c bolding-bruggeman -y fabmos
   ```

2. Test your installation by running the following in a terminal window:
   ```
   conda activate amemr
   python -c "import fabmos"
   ```
   These commands should complete without errors.

## Get transport matrices to drive global simulations

1. Download the MITgcm 2.8° circulation (`MITgcm_2.8deg`) from [Samar Khatiwala](http://kelvin.earth.ox.ac.uk/spk/Research/TMM/TransportMatrixConfigs/)
2. Extract this tar file to a directory on disk (remember where you put it; we’ll use it from a terminal later). On Windows, you may get error message such as "A required privilege is not held by the client". This can be ignored - you can skip the two affected files.
