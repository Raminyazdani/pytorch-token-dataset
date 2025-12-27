# Project Identity

## Display Title
PyTorch Custom Dataset Implementation

## Repo Slug (suggestion)
pytorch-token-dataset

## Tagline
Custom PyTorch Dataset classes for flexible token-based and CSV data loading with automatic padding and batch processing

## GitHub Description
A production-ready implementation of custom PyTorch Dataset classes demonstrating best practices for handling variable-length token sequences and structured CSV data. Features automatic padding, train/validation splitting, and efficient DataLoader integration.

## Primary Stack
- Python
- PyTorch
- Jupyter Notebook
- NumPy
- scikit-learn

## Topics/Keywords
- pytorch
- machine-learning
- deep-learning
- dataset
- data-loading
- custom-dataset
- token-processing
- data-preprocessing
- batch-processing
- python
- jupyter-notebook
- pytorch-dataset

## Problem & Approach

**Problem:** Machine learning workflows require flexible, reusable dataset classes that can handle variable-length sequences and multiple data formats efficiently.

**Approach:** Implements two custom PyTorch Dataset classes:
1. `TokenDataset` - Handles variable-length token sequences from JSON with automatic padding
2. `CSVDataset` - Processes structured CSV data with one-hot encoding for labels

Both integrate seamlessly with PyTorch's DataLoader for efficient batching and support train/validation splitting.

## Inputs
- JSON files containing token arrays and labels (variable-length sequences)
- CSV files with structured tabular data and categorical labels

## Outputs
- Custom Dataset instances compatible with PyTorch DataLoader
- Batched, padded token sequences ready for model training
- Preprocessed CSV data with one-hot encoded labels
- Complete implementation demonstrating dataset creation, splitting, and loading patterns
