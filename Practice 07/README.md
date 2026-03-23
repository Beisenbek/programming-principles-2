# Practice 7: Python & PostgreSQL, PhoneBook

## 1. Objective

This practice focuses on integrating Python with PostgreSQL. You will design a relational database schema, connect to it from Python using `psycopg2`, and implement a console-based PhoneBook application that supports inserting, querying, updating, and deleting contacts.

---

## 2. Key Concepts

| Abbreviation | Stands for | Meaning |
|---|---|---|
| **DB** | Database | Used to store structured information (data) |
| **RDB** | Relational Database | Data is stored in **tables** (also called *relations*), structured in **rows** and **columns** (also called *records* and *fields*). A record represents one entity; fields represent its individual data items. |
| **RDBMS** | Relational Database Management System | Software needed to create and work with an RDB |
| **SQL** | Structured Query Language | The language used to communicate with an RDBMS |
| **CRUD** | Create, Read, Update, Delete | The four basic operations on data (rows, not tables) |

**CRUD ↔ SQL mapping**:

| CRUD operation | SQL keyword |
|---|---|
| Create | `INSERT` |
| Read | `SELECT` |
| Update | `UPDATE` |
| Delete | `DELETE` |

**SQL is a declarative language** - you describe *what* you want, not *how* to do it (unlike imperative languages like C++, Java, Python, etc.).

**PostgreSQL** is an ORDBMS (Object-Relational DBMS) that uses its own dialect of SQL. We will use it as our database engine in this practice.

**Installing PostgreSQL**: follow the steps at https://www.w3schools.com/postgresql/postgresql_install.php

**psycopg2** is the Python module that lets us work with PostgreSQL. Install it by running:
```bash
pip install psycopg2
```
(you may need to use `pip3` instead of `pip` and/or `psycopg2-binary` instead of `psycopg2`)

---

## 3. Tasks

### 3.1 Learn from PostgreSQL Tutorial

Read the PostgreSQL + Python tutorial to understand how to connect and work with a database from Python:

🔗 **PostgreSQL Python Tutorial**: https://neon.com/postgresql/postgresql-python

**Topics to cover**:
- Installing and configuring PostgreSQL
- Connecting to PostgreSQL from Python (`psycopg2`)
- Creating tables
- Inserting rows (single and batch)
- Querying data with `SELECT`
- Updating existing rows
- Deleting rows
- Handling transactions and error recovery

---

### 3.2 Practical Exercise: PhoneBook

Build a **PhoneBook** application backed by PostgreSQL.

1. Design table(s) for the PhoneBook
2. Implement inserting data from a CSV file
3. Implement inserting data entered from the console (user name, phone)
4. Implement updating a contact's first name or phone number
5. Implement querying contacts with different filters (e.g. by name, by phone prefix)
6. Implement deleting a contact by username or phone number

---

### 3.3 Save Examples to GitHub

Organize your code and push to your repository.

Example repository structure:
```
Practice7/
├── phonebook.py
├── config.py
├── connect.py
└── contacts.csv
```

Commit instructions:
```bash
git add .
git commit -m "Add Practice7 - PhoneBook with PostgreSQL"
git push origin main
```

---

## 4. What You Must Complete

To pass this practice you must:

- ✅ Design and create PhoneBook table(s) in PostgreSQL
- ✅ Implement CSV-based data import
- ✅ Implement console-based data entry
- ✅ Implement updating contacts (name or phone)
- ✅ Implement querying with different filters
- ✅ Implement deleting contacts by username or phone
- ✅ Push code to GitHub with clear commit messages

**Deadline**: check MS Teams announcements

---

## 5. 🛠 Troubleshooting

- **Connection refused**: make sure the PostgreSQL server is running (`sudo service postgresql start` or check `pg_isready`)
- **Authentication errors**: verify your username, password, and database name in the connection config
- **psycopg2 not found**: install with `pip install psycopg2-binary` (or `pip3`)
- **CSV encoding**: open CSV files with `encoding='utf-8'` to avoid decode errors
- **Transactions**: remember to call `conn.commit()` after write operations, or use `with conn:` as a context manager

---

## 6. Resources

- 📚 PostgreSQL Python Tutorial: https://neon.com/postgresql/postgresql-python/
- 📚 psycopg2 Documentation: https://www.psycopg.org/docs/
- 📚 PostgreSQL Official Docs: https://www.postgresql.org/docs/
- 📚 Python `csv` Module: https://docs.python.org/3/library/csv.html
