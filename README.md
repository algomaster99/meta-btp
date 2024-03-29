# Analysis of Work Hardening Behaviour

The project implements various models to analyse work hardening behaviour of
light aluminium alloys. Apart from the work hardening, we have also implemented
the model for [YLD200][yld2000] which is useful in predicting yield criterion.
The eventual goal of this project is to plot formability limit diagram which
has a high relevance in industry.

## Try out the project yourself

### Prerequisites

1. Python 3.6+
2. Jupyter Notebook kernel

### Setup

1. Clone the project.
   ```sh
   git clone https://github.com/algomaster99/meta-btp.git
   ```

2. Install the dependencies required in the project.
   ```sh
   pip install -r requirements.txt
   ```
   Please note that you may install the dependencies globally or locally in a
   [Python virtual environment][virtualenv]. The latter is recommended.

3. Start the Jupyter notebook server.
   ```sh
   jupyter-notebook
   ```

### Feed script with dataset

The script for work hardening analysis takes a CSV file of the form:
```sh
engineering stain (mm/mm),engineering stress (MPa)
```
For example,
```sh
1E-05,0.05602
1E-05,0.11128
2E-05,0.21463
3E-05,0.44231
```

All of your datasets have to be fed to the entry point of the project which
is [dataset_initialisation](dataset_initialisation.ipynb). Inside the notebook,
under the heading "Dataset", there is an array which takes in
**1 or more paths** to various datasets. Some functions in the script will show
a combined plot of the datasets passed whereas some will show each of them
individually.

## Outputs

The script will automatically generate an *output* directory at the root of the
project. It will store the necessary parameters and graphs obtained while
running the script. Alternate way to save plots obtained in the script is to
right-click on them and save.

## Submission

The [report](submission/BTP%20Report.pdf) and
[presentation](submission/BTP%20PPT.pptx) of this project is also hosted
online. Click on the respective links to have a look at them.

## FAQ

**Q. Where to enter path to datasets?**

A. Read [this section][dataset].

**Q. Do I need to have crystal plasticity data to work with YLD2000.ipynb?**

A. No, it is optional. The script is self-sufficient. You can comment the lines
   related to it (they have been marked in the notebook) and the script would
   run without it.

**Q. How to change resolution of graphs and figures?**

A. The script uses [fig.set_dpi][figure] to set the DPI of the figures.
   Alternatively, you can also pass `dpi` argument to `fig.savefig`.

[yld2000]: https://www.sciencedirect.com/science/article/abs/pii/S0749641902000190
[virtualenv]: https://pypi.org/project/virtualenv/
[figure]: https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.figure.html
[dataset]: #feed-script-with-dataset
