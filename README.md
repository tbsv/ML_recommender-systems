# Machine Learning // Recommender Systems

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/tbsv/ML_recommender-systems/master?filepath=recommender-systems_solution.ipynb) [![nbviewer](https://img.shields.io/badge/nb-viewer-orange?logo=jupyter)](https://nbviewer.jupyter.org/github/tbsv/ML_recommender-systems/blob/master/recommender-systems_solution.ipynb)

This is Binder-compatible repo with a `requirements.txt` file.

## Summary

In this project, it's all about creating a simple working recommendation system that recommends movies that are as similar as possible to a specific movie.

## Contents

There is 1 notebook in this repository:

- [recommender-systems_solution.ipynb](recommender-systems_solution.ipynb) : runs a recommender system exercise that is taken from a Udemy course (see details in the *About* section below).

In addition, the following ressources are in this repository:

- [requirements.txt](requirements.txt) : lists all Python libraries that the notebook depends on.
- [DATA](DATA) : contains all data sets and further ressources that are used within the Jupyter Notebook.

## Usage

Dependencies are specified in [requirements.txt](/requirements.txt) :

```
pip install -r requirements.txt
```

You can access this repo via **Binder** at the following URL 
https://mybinder.org/v2/gh/tbsv/ML_recommender-systems/master or via the Binder badge above.

For a quick look into the notebook, you can use the **NBViewer** badge above.

Alternatively, you can run the notebook locally. Therefore, you will need to have python installed,
preferably through [Anaconda](https://www.anaconda.com/download/).

## Run the notebook

Each cell of code can be run with `shift + enter` or you can run the entire notebook by selecting `Cell` -> `Run All` in the toolbar.

![Screenshot](DATA/jn_run-all.png?raw=true "Screenshot")

For more information on running Jupyter notebooks, see the [Jupyter Documentation](https://jupyter.readthedocs.io/en/latest/).

## Example (for reproduction)

### Import libraries
```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
sns.set_style('white')
%matplotlib inline
```

### Import data set
```python
// user items
column_names = ['user_id', 'item_id', 'rating', 'timestamp']
df = pd.read_csv('./DATA/u.data', sep='\t', names=column_names)

// movies
movie_titles = pd.read_csv("./DATA/Movie_Id_Titles")

// merge both into one dataframe
df = pd.merge(df,movie_titles,on='item_id')
```


### Create a jointplot
```python
sns.jointplot(x='rating',y='num of ratings',data=ratings,alpha=0.5)
```

### Result plot
![plot](DATA/recommender-systems_jointplot.png?raw=true "Plot")

## Issues

Please [open an issue](https://github.com/tbsv/ML_recommender-systems/issues) if you encounter any problems while trying to run the notebooks.

## About
This data science exercise is part of the Digital Business Engineering Master at HHZ.

The given examples were taken from the Udemy course [Python for Data Science, Machine Learning & Visualization](https://www.udemy.com/course/python-data-science-machine-learning/).

Adaptions to the jupyter notebook are made by [Tobias Vetter](mailto:tobias.vetter@student.reutlingen-university.de).