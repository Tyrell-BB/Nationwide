# Data Cleaning

# Overview
This python script dissects a dataset, removes duplicate rows, splits the dataset into manageable sizes for cleaning, validates the data, removes inconsistencies in the dataset and reconstructs it as one file into a readable format.

# Requirements
* [Google Colab](https://colab.research.google.com/)
* Dataset
* Pandas
* Regular expression library
* os library
* Google Translate library

# Installation
Import the relevant modules and libraries
```python
import pandas as pd
import os
import re
!pip install googletrans==4.0.0-rc1
from googletrans import Translator
```
* pandas: For data manipulation and analysis
* os: For manipulating paths
* re: Specifies a set of strings that matches it
* Translator: Converting Chinese to English

# Functioning Process

# Split Dataset
```python
def split_csv(input_file, output_folder, num_chunks):
```
* input_file: csv file
* output_folder: designated chunk files
* num_chunks: number of chunks to split file

# Translate Headers
```python
def translate_headers(input_file, output_file):
```
* input_file: chunks folder
* output_file: translated chunks

# Check For Duplicates
```
def remove_duplicates(input_folder, output_folder, dump_folder):
```
* Check for duplicate entries in key identifier columns
* 

# Check For Valid Emails
```python
def is_valid_email(email):
  """Checks if an email address is valid."""
  if pd.isnull(email):
    return False
  pattern = r"^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$"
  return bool(re.fullmatch(pattern, email))
```
* Validates email addresses using a regular expression

# Clean and Garbage Extraction
```python
def drop_columns_in_chunks(input_folder, output_folder, columns_to_drop):
```
* Drop columns not relevant to personal key identifiers
* columns_to_drop: list columns to drop

# Normalize Headers
```python
def rename_headers(input_folder, output_folder):
```
* Normalize headers to proper format (replace spaces with underscores)

# Combine Chunks
```python
def merge_csv_files(input_folder, output_file):
```
* Combines chunks in the chunks folder to create one file
* Combine cleaned chunks to cleaned csv
* Combine invalid chunks to invalid csv

# Conclusion
These functions and processes extract, transform and store data into clean, readable datasets.
