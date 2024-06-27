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
