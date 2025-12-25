# PyTorch Custom Dataset Implementation

**Custom PyTorch Dataset class with JSON/CSV data handling**

**Stack:** Python, PyTorch, Jupyter Notebook

## Overview

This project demonstrates the implementation of a custom PyTorch Dataset class for token-based data processing. It showcases data loading from multiple formats (JSON, CSV), automatic padding functionality, and integration with PyTorch's DataLoader for efficient batch processing in machine learning workflows.

## Problem & Approach

**Problem:** Create a flexible, reusable dataset class for handling variable-length token sequences with proper padding and batching.

**Approach:**
- Implement custom `TokenDataset` class extending `torch.utils.data.Dataset`
- Load and parse data from JSON and CSV formats
- Handle variable-length sequences with automatic padding
- Integrate train/validation splitting functionality
- Provide efficient batching through DataLoader

## Tech Stack

- **Python 3.x** - Core programming language
- **PyTorch** - Deep learning framework and Dataset/DataLoader utilities
- **NumPy** - Numerical computing for array operations
- **scikit-learn** - Train/validation splitting
- **Jupyter Notebook** - Interactive development environment

## Repository Structure

```
./
├── token_dataset.ipynb    # Implementation notebook
├── data.json             # Token sequences and labels (JSON)
├── data.csv              # Structured data (CSV)
├── requirements.txt      # Python dependencies
└── README.md             # This file
```

## Setup / Installation

1. **Install dependencies:**
```bash
pip install -r requirements.txt
```

Or manually:
```bash
pip install torch numpy scikit-learn jupyter
```

## How to Run

1. **Start Jupyter Notebook:**
```bash
jupyter notebook token_dataset.ipynb
```

2. **Execute cells sequentially** from top to bottom

Alternative with JupyterLab:
```bash
jupyter lab token_dataset.ipynb
```

## Data / Inputs

**Input Files:**
- `data.json` - JSON file with token arrays and corresponding labels
- `data.csv` - CSV file with structured tabular data

**Data Format:**
- Token sequences of variable lengths
- Categorical labels for supervised learning
- All data files located in project directory

**Data Location:** Both files are in the root of the project directory

## Outputs

**Implementation Components:**
- `TokenDataset` class - Custom PyTorch Dataset with padding
- Data preprocessing functions
- Train/validation split implementation
- DataLoader initialization examples

**Outputs:**
- Processed batches of padded token sequences
- Dataset statistics and information
- Visual output within notebook cells

## Reproducibility Notes

- All file paths are relative to project directory
- Random seed can be set for reproducible train/val splits
- Notebook includes complete implementation from scratch
- No external dependencies beyond specified packages
- Padding implemented to maximum sequence length in dataset

## Troubleshooting

**Common Issues:**

- **Import errors:** Install all dependencies with `pip install torch numpy scikit-learn jupyter`
- **Data file not found:** Ensure `data.json` and `data.csv` are in the same directory as notebook
- **Colab usage:** Upload data files to Colab environment before running
- **Memory issues:** Reduce batch size if processing large datasets

**Path Issues:**
- Notebook expects data files in same directory
- Use relative paths for portability

## Notes

- TokenDataset includes automatic padding to max sequence length
- Compatible with PyTorch's standard DataLoader interface
- Demonstrates best practices for custom dataset implementation
- Suitable as template for similar data processing tasks
