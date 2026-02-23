# Practice 5: Python Regular Expressions (RegEx)

## 1. Objective

This practice focuses on mastering regular expressions in Python. You will learn to search, match, find, and replace text patterns using Python's `re` module. Practical exercises include parsing receipt data from the provided `raw.txt` file.

---

## 2. Tasks

### 2.1 Learn Python RegEx from W3Schools

Read and complete exercises from W3Schools Python Tutorial:

🔗 **W3Schools Python**: [https://www.w3schools.com/python/python_regex.asp](https://www.w3schools.com/python/python_regex.asp)

**Topics to Cover**:
- RegEx Introduction
- RegEx Syntax and Metacharacters (., *, +, ?, ^, $, [], |, (), \\)
- Special Sequences (\d, \w, \s, \D, \W, \S, \A, \Z)
- Sets and Character Classes
- Quantifiers ({n}, {n,}, {n,m})
- re.search() - Find first match
- re.findall() - Find all matches
- re.split() - Split strings
- re.sub() - Replace patterns
- re.match() - Match at beginning
- Flags (re.IGNORECASE, re.MULTILINE, etc.)

**Instructions**:
- Read each section carefully
- Complete all exercises and "Try It Yourself" examples
- Practice creating different regex patterns

---

### 2.2 Practical Exercise: Receipt Parsing

Use the provided `raw.txt` file in this folder to practice receipt parsing:

**Tasks**:
1. Extract all prices from the receipt
2. Find all product names
3. Calculate total amount
4. Extract date and time information
5. Find payment method
6. Create a structured output (JSON or formatted text)

**Implementation**:
- Create a `receipt_parser.py` file
- Use appropriate regex patterns to extract data
- Handle various formatting edge cases
- Output parsed data in a readable format

---

### 2.3 Save Examples to GitHub

Organize your code in GitHub:

**Repository Structure**:
```
Practice5/
├── receipt_parser.py
├── raw.txt
└── README.md
```

**Commit Instructions**:
```bash
git add .
git commit -m "Add Practice5 - Python RegEx and receipt parsing examples"
git push origin main
```
---

## 2.4 Online Problem Set

Solve programming problems to apply your knowledge:

🔗 **[Problem Set 05](http://ejudge.kz/new-client?contest_id=705)**

- Register/Login to the ejudge system
- Complete the problems related to iterators, dates, math, and JSON
- Submit your solutions before the deadline

---

## 3. What You Must Complete?

To pass this practice, you must:

- ✅ Complete all RegEx sections from W3Schools
- ✅ Create examples for each regex function (search, findall, split, sub)
- ✅ Demonstrate metacharacters, special sequences, and quantifiers
- ✅ Complete the receipt parsing exercise using `raw.txt`
- ✅ Extract and display all required information from receipts
- ✅ Push all code to GitHub with clear commit messages

**Deadline**: check MS Teams announcements

---

## 4. 🛠 Troubleshooting

If you encounter issues:

- **RegEx Testing**: Use [regex101.com](https://regex101.com/) to test patterns
- **Python RegEx**: Test at [https://www.w3schools.com/python/trypython.asp](https://www.w3schools.com/python/trypython.asp)
- **Pattern Issues**: Break down complex patterns into simpler parts
- **Receipt Parsing**: Examine `raw.txt` structure carefully

---

## 5. Resources

- 📚 [W3Schools Python RegEx](https://www.w3schools.com/python/python_regex.asp)
- 🔧 [regex101.com - RegEx Tester](https://regex101.com/)
- 📚 [Python re Module Documentation](https://docs.python.org/3/library/re.html)
- 📚 [RegExr - Learn & Test](https://regexr.com/)
- 📚 [RegEx Cheat Sheet](https://www.rexegg.com/)
- 💻 [Python Try It Online](https://www.w3schools.com/python/trypython.asp)