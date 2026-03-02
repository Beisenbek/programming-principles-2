````markdown
# Practice 6: Python File Handling and Built-in Functions

## 1. Objective

This practice focuses on working with files, directories, and core built-in functions in Python. You will practice reading, writing, and managing files and directories, and create examples that demonstrate commonly used built-in functions for data processing.

---

## 2. Tasks

### 2.1 Learn from W3Schools

Read and complete the W3Schools sections for file handling and built-in functions:

🔗 **W3Schools File Handling**: https://www.w3schools.com/python/python_file_handling.asp

**Topics to cover**:
- File modes: `r`, `w`, `a`, `x`
- Reading files: `read()`, `readline()`, `readlines()`
- Writing and appending files
- Context manager: `with` statement
- File and path operations: `os`, `shutil`, `pathlib`
- Directory management: `os.mkdir()`, `os.makedirs()`, `os.listdir()`, `os.chdir()`, `os.getcwd()`, `os.rmdir()`
- Built-in functions: `len()`, `sum()`, `min()`, `max()`, `map()`, `filter()`, `reduce()`, `enumerate()`, `zip()`, `sorted()`, type conversion functions

---

### 2.2 Practical Exercises

**File handling exercises**:
1. Create a text file and write sample data
2. Read and print file contents
3. Append new lines and verify content
4. Copy and back up files using `shutil`
5. Delete files safely

**Directory exercises**:
1. Create nested directories
2. List files and folders
3. Find files by extension
4. Move/copy files between directories

**Built-in functions practice**:
1. Use `map()` and `filter()` on lists
2. Aggregate with `reduce()` (from `functools`)
3. Use `enumerate()` and `zip()` for paired iteration
4. Demonstrate type checking and conversions

---

### 2.3 Save Examples to GitHub

Organize your code and push to your repository.

Example repository structure:
```
Practice6/
├── file_handling/
│   ├── read_files.py
│   ├── write_files.py
│   └── copy_delete_files.py
├── directory_management/
│   ├── create_list_dirs.py
│   └── move_files.py
├── builtin_functions/
│   ├── map_filter_reduce.py
│   └── enumerate_zip_examples.py
└── README.md
```

Commit instructions:
```bash
git add .
git commit -m "Add Practice6 - file handling and built-in functions examples"
git push origin main
```

---

## 3. Online Problem Set

Complete the online problem set to apply your knowledge:

🔗 **Problem Set 06**: http://ejudge.kz/new-client?contest_id=706

Register/Login and submit solutions before the deadline.

---

## 4. What You Must Complete

To pass this practice you must:

- ✅ Complete all file handling exercises
- ✅ Create examples for reading, writing, appending, copying, and deleting files
- ✅ Demonstrate directory creation and management
- ✅ Implement examples using built-in functions listed above
- ✅ Push code to GitHub with clear commit messages

**Deadline**: check MS Teams announcements

---

## 5. 🛠 Troubleshooting

- **File paths**: prefer `pathlib.Path` for cross-platform paths
- **Permissions**: check read/write permissions if operations fail
- **Directory errors**: ensure the target directory exists before writing
- **Imports**: `import os`, `import shutil`, `from pathlib import Path`, `from functools import reduce`

---

## 6. Resources

- 📚 W3Schools: https://www.w3schools.com/python/python_file_handling.asp
- 📚 Python `os` module: https://docs.python.org/3/library/os.html
- 📚 Python `pathlib`: https://docs.python.org/3/library/pathlib.html
- 📚 Python built-in functions: https://docs.python.org/3/library/functions.html
- 💻 Python Try It Online: https://www.w3schools.com/python/trypython.asp
````
