# NLP Name Parser

## Overview

This code provides an **NLP-driven approach** for cleaning and extracting first and last names from raw textual data. It leverages **spaCy** for **named entity recognition (NER)** and **part-of-speech (POS) tagging** to intelligently parse and filter names, ensuring accurate extraction.

## Features

- **Advanced NLP Processing**: Uses **spaCy's Transformer-based model** (`en_core_web_trf`) for precise entity recognition.  
- **Intelligent Honorific Removal**: Detects and removes titles only when they appear as separate words.  
- **Handles Noisy Data**: Preprocesses input to fix spacing inconsistencies.  
- **Optimized with Swifter**: Applies parallelized name cleaning for efficient large-scale processing.  
- **Flexible CSV Processing**: Reads, processes, and writes structured output files.  

## Setup

### Prerequisites

Ensure you have the following installed:

- Python 3.7+
- `spacy`, `pandas`, `swifter`, `re`

Install dependencies using:

```sh
pip install spacy pandas swifter
python -m spacy download en_core_web_trf
```

## Usage

### 1️. Process a CSV File

```python
name_column = "<ENTER COLUMN NAME>"
input_csv = "<ENTER FILE NAME>"
output_csv = "output.csv"

process_csv(input_csv, output_csv)
```

### 2️. Example Output

| Person - Name       | First Name | Last Name |
|---------------------|------------|-----------|
| Dr. Maria Smith    | Maria      | Smith     |
| Mr. John O'Connor  | John       | O'Connor  |
| Prof. Alice Carter | Alice      | Carter    |

## How It Works

- **Preprocessing**: Adds missing spaces after honorifics.
- **NER & POS Filtering**: Extracts only proper nouns and named entities classified as persons.
- **Honorific Removal**: Eliminates titles if they appear as separate words.
- **Refined Cleaning**: Ensures only a single-word **first name** and **last name** are retained.

## Performance Considerations

- Uses **spaCy's transformer model** for high accuracy.
- Parallelized with **Swifter** for large dataset handling.

## Best Practices

**Ensure input names are well-structured** – preprocessing handles some noise, but cleaner inputs yield better results.  
**Use a GPU (if available)** – `en_core_web_trf` runs significantly faster on GPUs.  
**Tune honorific lists as needed** – extend or modify the list based on domain-specific titles.  

## Contributing

Contributions are welcome! Feel free to submit issues or pull requests.

---
