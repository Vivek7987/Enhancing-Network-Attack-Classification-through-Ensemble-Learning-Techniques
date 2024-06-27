# Enhancing-Network-Attack-Classification-through-Ensemble-Learning-Techniques

import nbformat

# Load the uploaded notebook file
notebook_path = '/mnt/data/proposed.ipynb'
with open(notebook_path, 'r') as file:
    notebook_content = nbformat.read(file, as_version=4)

# Extract the title, description, and other details from the notebook's markdown cells
title = ""
description = ""
for cell in notebook_content.cells:
    if cell.cell_type == 'markdown':
        lines = cell.source.split('\n')
        for line in lines:
            if line.startswith('# '):
                title = line[2:]
            elif line:
                description += line + '\n'

title, description
Classification: 2 (1+1) Classes
Overview
This project focuses on the classification task involving 2 classes (1+1). The notebook includes steps for data exploration, preprocessing, model training, and evaluation.

Contents
Exploratory Data Analysis (EDA): Detailed analysis of the dataset to understand its structure and characteristics.
Installation
To run the code in this repository, you will need to have the following dependencies installed:
