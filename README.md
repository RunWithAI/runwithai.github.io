# Quarto Website Demo

This repository demonstrates how to build and deploy a multi-language static website using **Quarto**, integrating both **R** and **Python** code execution and outputs. It was developed as part of the [UBC MDS DSCI 521 Milestone 3](https://ubc-mds.github.io/DSCI_521_platforms-dsci/assignments/milestone3.html) assignment.

- **Live Website:** [View the published site here](https://runwithai.github.io/)

---

## Overview

The primary goal of this assignment is to showcase:
- Building a Quarto website with embedded code chunks and html text.
- Executing **R** and **Python** code using relative packages.

---

## Reproducibility & Build Instructions

Follow the steps below to set up the environment and render the website locally.

### 0. Clone the Repository
```bash
git clone https://github.com/RunWithAI/runwithai.github.io.git
```

### 1. Prerequisites
Ensure you have the following installed on your machine:

- Python 3.14 [Installation Guide](https://realpython.com/installing-python/)
- uv: Fast Python package manager [Installation Guide](https://docs.astral.sh/uv/getting-started/installation)
- R 4.6.1 [Installation Guide](https://cran.r-project.org/doc/manuals/r-patched/R-admin.html)
- Quarto ([Download Quarto](https://quarto.org/docs/get-started/))

### 2. Install Dependencies
#### Python Dependencies:
Install the locked dependencies into the virtual environment using uv:

```bash
cd runwithai.github.io
uv sync
``` 

#### R Dependencies:

Install renv:

```bash
R -e 'if (!requireNamespace("renv", quietly = TRUE)) install.packages("renv", repos = "[https://cloud.r-project.org](https://cloud.r-project.org)")'
```
Restore R environment:
```bash
R -e 'renv::restore()'
```

### 3. Build the Website
Render the entire site (output will be generated in the docs/ folder):

```bash
uv run quarto render
```

### 4. Local Preview
To preview the website locally with live reload:

```bash
uv run quarto preview
```

### 5. Deployment (GitHub Pages)

Commit and push the generated docs/ folder and updated project files to GitHub.

In your GitHub repository, navigate to Settings > Pages.

Under Build and deployment > Branch, select main (or your default branch) and choose the /docs folder, then click Save.