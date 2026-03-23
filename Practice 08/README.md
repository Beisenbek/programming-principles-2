# Practice 8: PostgreSQL Functions & Stored Procedures, PhoneBook (cont.)

## 1. Objective

This practice extends the PhoneBook application from Practice 7 by introducing PostgreSQL **functions** and **stored procedures**. You will move core data-manipulation logic into the database layer, gaining experience with server-side SQL programming, control flow, and input validation inside PostgreSQL.

---

## 2. Key Concepts

| Term | Meaning |
|---|---|
| **Function** | A named block of SQL/PL/pgSQL code that accepts parameters, performs computation, and **returns a value** (scalar or table). Called with `SELECT`. |
| **Stored Procedure** | Similar to a function but designed for **performing actions** (inserts, updates, deletes) rather than returning values. Called with `CALL`. |
| **PL/pgSQL** | PostgreSQL's procedural language extension that adds variables, loops, conditionals, and exception handling to plain SQL. |
| **Pagination** | Retrieving data in chunks using `LIMIT` and `OFFSET` instead of loading all rows at once. |

**Creating a function** (example):
```sql
CREATE OR REPLACE FUNCTION get_contacts_by_pattern(p text)
RETURNS TABLE(name VARCHAR, phone VARCHAR) AS $$
BEGIN
    RETURN QUERY SELECT c.name, c.phone FROM contacts c
                 WHERE c.name ILIKE '%' || p || '%'
                    OR c.phone ILIKE '%' || p || '%';
END;
$$ LANGUAGE plpgsql;
```

**Creating a stored procedure** (example):
```sql
CREATE OR REPLACE PROCEDURE upsert_contact(p_name VARCHAR, p_phone VARCHAR)
LANGUAGE plpgsql AS $$
BEGIN
    IF EXISTS (SELECT 1 FROM contacts WHERE name = p_name) THEN
        UPDATE contacts SET phone = p_phone WHERE name = p_name;
    ELSE
        INSERT INTO contacts(name, phone) VALUES(p_name, p_phone);
    END IF;
END;
$$;
```

---

## 3. Tasks

### 3.1 Learn About Functions & Stored Procedures

Read the PostgreSQL tutorial sections on functions and procedures:

🔗 **PostgreSQL Functions**: https://neon.com/postgresql/postgresql-plpgsql

**Topics to cover**:
- Creating and calling functions (`CREATE FUNCTION`, `SELECT`)
- Creating and calling procedures (`CREATE PROCEDURE`, `CALL`)
- PL/pgSQL basics: variables, `IF`/`ELSE`, `LOOP`, `FOR`
- Returning scalars vs. tables (`RETURNS TABLE`, `RETURN QUERY`)
- Exception handling in PL/pgSQL

---

### 3.2 Practical Exercise: PhoneBook with Functions & Procedures

Using the PhoneBook database from Practice 7, implement the following:

1. A function that returns all records matching a pattern (part of name, surname, or phone number)
2. A procedure to insert a new user by name and phone; if the user already exists, update their phone
3. A procedure to insert many new users from a list of names and phones - use a loop and `IF` inside the procedure, validate phone correctness, and return all incorrect data
4. A function that queries data from the table with pagination (by `LIMIT` and `OFFSET`)
5. A procedure to delete data from the table by username or phone

---

### 3.3 Save Examples to GitHub

Organize your code and push to your repository.

Example repository structure:
```
Practice8/
├── phonebook.py
├── functions.sql
├── procedures.sql
├── config.py
└── connect.py
```

Commit instructions:
```bash
git add .
git commit -m "Add Practice8 - PhoneBook with functions and stored procedures"
git push origin main
```

---

## 4. What You Must Complete

To pass this practice you must:

- ✅ Implement a pattern-search function
- ✅ Implement an upsert procedure (insert or update)
- ✅ Implement a bulk-insert procedure with phone validation
- ✅ Implement a paginated query function
- ✅ Implement a delete procedure (by username or phone)
- ✅ Push code to GitHub with clear commit messages

**Deadline**: check MS Teams announcements

---

## 5. 🛠 Troubleshooting

- **"function does not exist"**: check that parameter types match exactly (e.g. `VARCHAR` vs `TEXT`)
- **Permission denied**: make sure you are connected as the table owner or a superuser
- **Procedure won't commit**: procedures manage their own transactions - avoid wrapping `CALL` in an explicit `BEGIN`/`COMMIT` from Python
- **Loop not terminating**: always include an `EXIT` condition or use `FOR ... IN` with a bounded range
- **psycopg2 and CALL**: use `cursor.execute("CALL procedure_name(%s, %s)", (arg1, arg2))` - `CALL` works like any other statement

---

## 6. Resources

- 📚 PostgreSQL PL/pgSQL Tutorial: https://neon.com/postgresql/postgresql-plpgsql
- 📚 PostgreSQL CREATE FUNCTION: https://www.postgresql.org/docs/current/sql-createfunction.html
- 📚 PostgreSQL CREATE PROCEDURE: https://www.postgresql.org/docs/current/sql-createprocedure.html
- 📚 psycopg2 Documentation: https://www.psycopg.org/docs/
- 📚 PostgreSQL Official Docs: https://www.postgresql.org/docs/
