# ExplainableProportionEstimation

This system is used to generate proportion estimation (on the use case of hominin DNA data), and explain the output results.
The use case on which the system runs is the problem of estimating the proportion of species in a genomic dataset.

Important methods:

## Getting Started

These instructions will give you a copy of the project up and running on your local machine.

### Prerequisites

Requirements for running the GUI and the system on your **linux machine** (you can use [WSL](https://docs.microsoft.com/en-us/windows/wsl/install) if you have a windows machine): 
- [python](https://www.python.org/)
- [Jupyter notebooks](https://jupyter.org/)
- [biopython](https://biopython.org/)
- [SHAP](https://shap.readthedocs.io/en/latest/index.html)
- [pysam](https://pysam.readthedocs.io/en/latest/api.html)
- [joblib](https://joblib.readthedocs.io/en/latest/)
- [bioconda](https://bioconda.github.io/)
- [termcolor](https://anaconda.org/conda-forge/termcolor)


### Work with the python code

The important methods are:
- Constructor (gets dataset, references) and runs the preProcessing of the proportion estimation maximum likelihood algorithm
- ``estimate_proportions`` - estimating the proportions of the dataset (after running the constructor)
- ``estimate_shapley_value_for_read`` - returning for each data point in the dataset an explanation vector of the estimation of the scaled Shapley values (how the data point is influencing the output of the algorithm)
- ``calculate_reference_influence`` - returning for each reference an explanation vector that is estimating how the reference is influencing the output of the algorithm
-  ``generateCounterFactualMinimalSetToRemoveAndChangeMax`` - calculating a counter factual - meaning what is the minimal subset that removing it from the dataset would cause the dominant label to change.

### Run the GUI project

1. Clone this repo
2. Run ``Jupyter lab`` in root directory.
3. Run the ``GUI`` notebook for the GUI that interacts with the system (cell by cell). 
4. Choose a dataset to analyze from the datasets under the data directory.
