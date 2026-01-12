# Lab 6: Python File Handling and Built-in Functions

## 1. Objective

This lab focuses on working with files and directories in Python. You will learn to read, write, create, and delete files, manage directories, and understand Python's built-in functions. These skills are essential for data processing and system automation.

---

## 2. Tasks

### 2.1 Learn Python File Handling from W3Schools

Read and complete exercises from W3Schools Python Tutorial:

🔗 **W3Schools Python**: [https://www.w3schools.com/python/default.asp](https://www.w3schools.com/python/default.asp)

**Topics to Cover**:

#### File Handling:
- File Modes (r, a, w, x)
- Reading Files (read(), readline(), readlines())
- Creating and Writing Files
- Deleting Files
- Context Manager (with statement)
- File Object Methods

#### Working with Directories:
- Creating Directories (os.mkdir(), os.makedirs())
- Listing Directories (os.listdir())
- Changing Directories (os.chdir())
- Getting Current Directory (os.getcwd())
- Deleting Directories (os.rmdir(), shutil.rmtree())
- Path Operations (os.path)

---

### 2.2 Learn Python Built-in Functions

**Topics to Cover**:
- Print and Input Functions
- Type Checking: type(), isinstance()
- Numeric Functions: len(), sum(), min(), max(), abs(), round()
- Conversion Functions: int(), str(), float(), bool(), list(), dict(), tuple()
- Iteration Functions: range(), enumerate(), zip()
- Functional Programming: map(), filter(), reduce()
- Sorting: sorted(), reversed()
- Other Useful Functions: all(), any(), divmod(), pow(), bin(), hex(), oct()

---

### 2.3 Save Examples to GitHub

Organize your code in GitHub:

**Repository Structure**:
```
Lab6/
├── file_handling/
│   ├── read_files.py
│   ├── write_files.py
│   ├── create_files.py
│   ├── delete_files.py
│   ├── file_modes.py
│   └── context_manager.py
├── directory_management/
│   ├── create_directories.py
│   ├── list_directories.py
│   ├── change_directory.py
│   ├── delete_directories.py
│   └── path_operations.py
├── builtin_functions/
│   ├── type_functions.py
│   ├── numeric_functions.py
│   ├── conversion_functions.py
│   ├── iteration_functions.py
│   ├── functional_functions.py
│   └── utility_functions.py
├── sample_files/
│   ├── example.txt
│   └── data.csv
└── README.md
```

**Commit Instructions**:
```bash
git add .
git commit -m "Add Lab6 - Python file handling and built-in functions"
git push origin main
```

---

### 2.4 Practical Exercises

**File Handling Tasks**:
1. Create a text file and write data to it
2. Read the file and display contents
3. Append data to the file
4. Create a backup copy of the file
5. Delete the original file

**Directory Tasks**:
1. Create nested directory structure
2. List all files in a directory
3. Find files with specific extensions
4. Move/copy files between directories

**Built-in Functions Practice**:
1. Use map() and filter() with lambda functions
2. Use reduce() for aggregation
3. Use enumerate() and zip() for iteration
4. Type checking and conversion examples

---

## 3. What You Must Complete?

To pass this lab, you must:

- ✅ Complete all file handling exercises
- ✅ Create examples for read, write, append, and delete operations
- ✅ Demonstrate directory creation and management
- ✅ Create examples for all major built-in functions
- ✅ Complete all practical exercises
- ✅ Push all code to GitHub with clear commit messages

**Deadline**: check MS Teams announcements

---

## 4. 🛠 Troubleshooting

If you encounter issues:

- **File Paths**: Use absolute or relative paths correctly
- **Permissions**: Check file read/write permissions
- **Directory Errors**: Ensure directories exist before operations
- **Module Imports**: Import os, shutil, and functools modules
- **Testing Code**: Use [Python Try It Online](https://www.w3schools.com/python/trypython.asp)

---

## 5. Resources

- 📚 [W3Schools Python File Handling](https://www.w3schools.com/python/python_file_handling.asp)
- 📚 [W3Schools Python File Methods](https://www.w3schools.com/python/python_file_methods.asp)
- 📚 [Python os Module](https://docs.python.org/3/library/os.html)
- 📚 [Python pathlib Module](https://docs.python.org/3/library/pathlib.html)
- 📚 [Python Built-in Functions](https://docs.python.org/3/library/functions.html)
- 💻 [Python Try It Online](https://www.w3schools.com/python/trypython.asp)
