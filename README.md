# AMEMR 2024 modelling workshop

We will work in a terminal window while installing necessary files and running the models.
On Windows, use the "Anaconda prompt" from the start menu (instructions on how to install that below).

We will be editing text files (yaml files and Python scripts) with model configurations. This can be done with many different editors, e.g., [Visual Studio Code](https://code.visualstudio.com/), Notepad on Windows, `vi` on Linux/Mac. We recommend using one you are already familiar with.

## Installation

1. Ensure you have Anaconda:
   - Linux/Mac: execute `conda --version` in a terminal
   - Windows: look for “Anaconda prompt” in the start menu

   If you *do not* have Anaconda, [install Miniconda](https://docs.anaconda.com/miniconda/miniconda-install/).

2. Create an isolated `amemr` environment with the models and visualization tools:
   ```
   conda create -n amemr -c conda-forge -y gotm pyncview
   ```

   [NB the above command will be updated to also install `fabmos`, which we will use for the last part of the workshop. At the moment, that does not yet work because fabmos is not yet available from conda-forge]

   If you experience any issue with the above, we recommend you first execute `conda update conda` to ensure your conda is up to date.
   Should this fail because of lack of permissions, we recommend you [install Miniconda](https://docs.anaconda.com/miniconda/miniconda-install/).
   After you have an up-to-date conda, retry the `conda create ...` command.

   The above command installs pre-compiled versions of [gotm](https://gotm.net) and [fabmos](https://github.com/BoldingBruggeman/fabmos/wiki) that includes reference versions of [ERSEM](http://ersem.com), [ECOSMO](https://doi.org/10.5194/gmd-15-3901-2022), [PISCES](https://www.pisces-community.org/), [iHAMOCC](https://doi.org/10.5194/gmd-13-2393-2020), [ERGOM](https://ergom.net/), and [MOPS](https://doi.org/10.5194/gmd-8-2929-2015), among others.

### Test your installation

Open a terminal window (on Windows, use the "Anaconda prompt" from the start menu), and in there, type:

```
conda activate amemr
gotm --version
multiplot --version
```

These three commands should complete without errors.

## Get transport matrices to drive global simulations

1. Download the MITgcm 2.8° circulation (`MITgcm_2.8deg`) from [Samar Khatiwala](http://kelvin.earth.ox.ac.uk/spk/Research/TMM/TransportMatrixConfigs/)
2. Extract this tar file to a directory on disk (remember where you put it; we’ll use it from a terminal later). On Windows, you may get error message such as "A required privilege is not held by the client". This can be ignored - you can skip the two affected files.
