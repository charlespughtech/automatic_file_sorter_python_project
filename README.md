# Automatic File Sorter Project

# python_automatic_file_sorter_project

---

Python-based Automatic File Sorter implemented in a Jupyter Notebook to organize files in a specified directory into subfolders based on their file extensions.

---

## Author

**Charles Pugh**

Google-certified Data Analyst

Email: [charlespughtech@gmail.com](mailto:charlespughtech@gmail.com)

LinkedIn: [https://www.linkedin.com/in/charlespughtech/](https://www.linkedin.com/in/charlespughtech/)

Date: May 27, 2025

---

## Table of Contents

- [Automatic File Sorter Project](#automatic-file-sorter-project)
- [python\_automatic\_file\_sorter\_project](#python_automatic_file_sorter_project)
  - [Author](#author)
  - [Table of Contents](#table-of-contents)
  - [Project Overview](#project-overview)
  - [Requirements](#requirements)
  - [Project Structure](#project-structure)
  - [Directory Setup](#directory-setup)
  - [File Sorting](#file-sorting)
  - [Usage](#usage)
  - [Contact](#contact)

---

## Project Overview

This project organizes files in a user-specified directory (e.g., `C:/Users/Alicja/Desktop/Charles/family_tree/`) into subfolders based on their file extensions. The supported file types are:

- **Python files** (`.py`): Sorted into a `py_files` folder.
- **PDF files** (`.pdf`): Sorted into a `pdf_files` folder.
- **Markdown files** (`.md`): Sorted into a `md_files` folder.

The project uses the `os` and `shutil` Python libraries to interact with the file system, list files, create subfolders, and move files to their respective folders. No external dataset is required; the input is the directory path and the files it contains.

---

## Requirements

- Python 3.12 or higher
- Jupyter Notebook (recommended via Anaconda or JupyterLab)
- Standard Python libraries:
  - `os` (for directory and file operations)
  - `shutil` (for moving files)

---

## Project Structure

```bash
python_automatic_file_sorter_project/
├── python_automatic_file_sorter_project.ipynb  # Jupyter Notebook with file sorter code
└── README.md                                   # Project overview and instructions
```

---

## Directory Setup

The directory setup process prepares the file system by defining the target directory and creating subfolders for sorting. Follow these steps to replicate:

- **Define Directory Path**:
  - Specify the path to the directory containing files to be sorted (e.g., `C:/Users/Alicja/Desktop/Charles/family_tree/`).
  - Use the `os` library to list files in the directory with `os.listdir()`.
- **Create Subfolders**:
  - Check if subfolders (`py_files`, `pdf_files`, `md_files`) exist using `os.path.exists()`.
  - Create them if they do not exist using `os.makedirs()`.
- **Full Implementation**:
  - The complete code for setting up the directory and creating subfolders is shown below (from the notebook):

```python
import os, shutil

path = r"C:/Users/Alicja/Desktop/Charles/family_tree/"

file_names = os.listdir(path)

folder_names = ['py_files', 'pdf_files', 'md_files']

for loop in range(0,3):
    if not os.path.exists(path + folder_names[loop]):
        print(path + folder_names[loop])
        os.makedirs(path + folder_names[loop])
```

---

## File Sorting

The file sorting process identifies file types in the specified directory and moves them to the appropriate subfolders based on their extensions. Follow these steps to replicate:

- **Sort Files by Extension**:
  - Use `os.listdir()` to retrieve all file names in the specified directory.
  - Loop through each file, check its extension (e.g., `.py`, `.pdf`, `.md`), and move it to the corresponding subfolder (`py_files`, `pdf_files`, `md_files`) using `shutil.move()` if it’s not already there.
- **Full Implementation**:
  - The complete code for sorting files is shown below (from the notebook):

```python
import os, shutil

path = r"C:/Users/Alicja/Desktop/Charles/family_tree/"

file_names = os.listdir(path)

folder_names = ['py_files', 'pdf_files', 'md_files']

for loop in range(0,3):
    if not os.path.exists(path + folder_names[loop]):
        print(path + folder_names[loop])
        os.makedirs(path + folder_names[loop])

for file in file_names:
    if ".py" in file and not os.path.exists(path + "py_files/" + file):
        shutil.move(path + file, path + "py_files/" + file)
    elif ".pdf" in file and not os.path.exists(path + "pdf_files/" + file):
        shutil.move(path + file, path + "pdf_files/" + file)
    elif ".md" in file and not os.path.exists(path + "md_files/" + file):
        shutil.move(path + file, path + "md_files/" + file)
```

- **Key Insights**:
  - The program automates file organization by sorting `.py`, `.pdf`, and `.md` files into designated subfolders.
  - It prevents duplicate moves by checking if a file already exists in the target subfolder using `os.path.exists()`.
  - The process can be extended to other file types by modifying the `folder_names` list and adding corresponding conditions in the sorting logic.

---

## Usage

To explore or replicate the Automatic File Sorter Project, follow these steps:

1. **Clone the Repository**:

   ```bash
   git clone https://github.com/charlespughtech/python_automatic_file_sorter_project.git
   cd python_automatic_file_sorter_project
   ```

2. **Explore the Project**:

   - Open `python_automatic_file_sorter_project.ipynb` in Jupyter Notebook or JupyterLab.
   - The notebook contains:
     - **Markdown Cells**: Explanations of the file sorting process, library imports, and steps.
     - **Code Cells**: Directory setup, subfolder creation, and file sorting logic.
   - Run the notebook cells sequentially, ensuring the `path` variable points to a valid directory on your system containing `.py`, `.pdf`, and/or `.md` files.
   - Verify that files are moved to the correct subfolders (`py_files`, `pdf_files`, `md_files`).

3. **Replicate the Project from Scratch** (Optional):

   - Create a new Jupyter Notebook named `python_automatic_file_sorter_project.ipynb`.
   - Add Markdown cells to document:
     - The purpose of the file sorter (organizing files by extension).
     - The libraries used (`os` and `shutil`).
     - The steps for directory setup and file sorting.
   - Add code cells to:
     - Import `os` and `shutil`.
     - Define the directory path (update `path` to a valid directory on your system).
     - List files using `os.listdir()`.
     - Create subfolders (`py_files`, `pdf_files`, `md_files`) using `os.makedirs()`.
     - Sort files into subfolders using `shutil.move()`.
   - Follow the steps in Directory Setup and File Sorting to implement the logic.
   - Test the notebook with a directory containing sample files (e.g., `.py`, `.pdf`, `.md`) to verify that files are sorted into the correct subfolders.

Results are available in `python_automatic_file_sorter_project.ipynb`. Check the code cells for the implementation and Markdown cells for documentation.

---

## Contact

For inquiries or data analytics services, please contact:

**Charles Pugh**

Google-certified Data Analyst

Email: [charlespughtech@gmail.com](mailto:charlespughtech@gmail.com)

LinkedIn: [https://www.linkedin.com/in/charlespughtech/](https://www.linkedin.com/in/charlespughtech/)
