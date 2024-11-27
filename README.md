# Molecular Docking Optimization with HPC

This project demonstrates the power of **High-Performance Computing (HPC)** in molecular docking simulations by implementing parallelization techniques with **OpenMP**. Using AutoDock Vina as the core docking engine, the project provides a comprehensive benchmarking system to analyze performance improvements across different threading configurations.

## Table of Contents

- [Molecular Docking Optimization with HPC](#molecular-docking-optimization-with-hpc)
  - [Table of Contents](#table-of-contents)
  - [Overview](#overview)
  - [Features](#features)
  - [Installation](#installation)
    - [Prerequisites](#prerequisites)
    - [Clone the Repository](#clone-the-repository)
  - [Usage](#usage)
  - [Performance Analysis](#performance-analysis)

## Overview

Molecular docking is a computational technique used in drug discovery to predict binding orientations of small molecule drug candidates to their protein targets. This project focuses on optimizing these computationally intensive simulations through parallel processing, providing detailed performance metrics and visualizations to demonstrate the benefits of HPC in drug discovery workflows.

## Features

- **OpenMP Parallelization**: Efficient multi-threaded execution of docking simulations
- **Comprehensive Benchmarking**: Performance analysis across different thread counts (1, 2, 4, 8)
- **Resource Monitoring**: Detailed tracking of CPU utilization and memory usage patterns
- **Performance Visualization**: Generation of comparative plots showing execution times and resource usage
- **Automated Analysis**: Python scripts for processing and analyzing docking results
- **Jupyter Integration**: Interactive notebooks for visualization and analysis

## Installation

### Prerequisites

1. **Python Environment Setup**

   ```bash
   conda create -n moldock python=3.9
   conda activate moldock
   ```

2. **Required Dependencies**

   ```bash
   conda install -c conda-forge vina "boost-cpp>=1.78.0" swig numpy
   conda install matplotlib pandas scipy jupyter
   ```

   Or install using the provided requirements file:

   ```bash
   pip install -r requirements.txt
   ```

### Clone the Repository

```bash
git clone https://github.com/albipuliga/molecular-docking-hpc.git
cd molecular-docking-hpc
```

## Usage

1. **Prepare Input Files**:

   - Place your receptor (protein) file in **_PDBQT_** format in the `data/receptor/` directory
   - Place your ligand files in **_PDBQT_** format in the `data/ligands/` directory

2. **Run Benchmarks**:

   ```python
   from molecular_docking import MolecularDocking

   # Initialize docking simulation
   docking = MolecularDocking(
       receptor_file="data/receptor/protein.pdbqt",
       ligand_file="data/ligands/ligand.pdbqt",
       center=(0, 0, 0),
       box_size=(20, 20, 20)
   )

   # Run benchmarks
   results = docking.benchmark(thread_counts=[1, 2, 4, 8])

   # Generate visualization
   docking.plot_benchmarks(results)
   ```

3. **Analyze Results**:
   - Launch Jupyter notebook:
     ```bash
     jupyter notebook notebooks/benchmark_analysis.ipynb
     ```

## Performance Analysis

The project includes comprehensive benchmarking capabilities that measure:

- Execution time across different thread counts
- CPU utilization patterns
- Memory usage profiles
- Speedup and efficiency metrics
