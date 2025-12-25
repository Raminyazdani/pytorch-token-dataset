# PyTorch Token Dataset

A custom PyTorch Dataset implementation for token-based data processing.

## Overview

This project provides custom PyTorch Dataset classes for handling variable-length token sequences and structured CSV data with automatic padding and efficient batch processing.

## Features

- Custom `TokenDataset` class for JSON-based token sequences
- Custom `CSVDataset` class for structured data
- Automatic padding for variable-length sequences
- Train/validation splitting support
- Compatible with PyTorch DataLoader

## Setup

```bash
pip install -r requirements.txt
```

## Usage

Run the notebook to see the implementation:

```bash
jupyter notebook token_dataset.ipynb
```

## Data Files

- `data.json` - Token sequences with labels
- `data.csv` - Structured tabular data
