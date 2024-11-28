# Molecular Docking Optimization with HPC

This project demonstrates the power of **High-Performance Computing (HPC)** in molecular docking simulations by implementing parallelization techniques with **OpenMP**. Using [**RDKit**](https://www.rdkit.org/) as the core docking engine, the project provides a comprehensive benchmarking system to analyze performance improvements across different threading configurations.

## Table of Contents

- [Molecular Docking Optimization with HPC](#molecular-docking-optimization-with-hpc)
  - [Table of Contents](#table-of-contents)
  - [Overview](#overview)
  - [Features](#features)
  - [Installation](#installation)
    - [Prerequisites](#prerequisites)
    - [Clone the repository](#clone-the-repository)
    - [Environment Setup](#environment-setup)
      - [1. Create and activate conda environment](#1-create-and-activate-conda-environment)
      - [2. Install core numerical libraries](#2-install-core-numerical-libraries)
        - [3. Install RDKit and other dependencies](#3-install-rdkit-and-other-dependencies)

## Overview

Molecular docking is a computational technique used in drug discovery to predict binding orientations of small molecule drug candidates to their protein targets. This project focuses on optimizing these computationally intensive simulations through parallel processing, providing detailed performance metrics and visualizations to demonstrate the benefits of HPC in drug discovery workflows.

## Features

## Installation

### Prerequisites

1. Python 3.9
2. Git
3. Conda (required)

### Clone the repository

```bash
git clone https://github.com/albipuliga/molecular-docking-hpc.git
cd molecular-docking-hpc
```

### Environment Setup

#### 1. Create and activate conda environment

```bash
conda create -n docking python=3.9 -y
conda activate docking
```

#### 2. Install core numerical libraries

```bash
conda install -c conda-forge numpy scipy lapack blas -y
```

##### 3. Install RDKit and other dependencies

```bash
conda install -c conda-forge rdkit matplotlib seaborn scikit-learn -y
```
