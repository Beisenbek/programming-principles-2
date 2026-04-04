# TSIS 1: PhoneBook — Extended Contact Management

## 1. Objective

Extend the PhoneBook application from Practice 7 and Practice 8 with an enriched data model, advanced console interactions, and new database-side logic. The goal is to go beyond basic CRUD and stored procedures by introducing relational schema design, multi-field search, and file-based data exchange.

---

## 2. Base (already done in Practice 7–8)

| Done in | Feature |
|---|---|
| Practice 7 | CRUD operations via psycopg2 |
| Practice 7 | CSV import, console-based data entry |
| Practice 7 | Query by name / phone prefix, update, delete |
| Practice 8 | Pattern-search function (name / phone) |
| Practice 8 | Upsert procedure, bulk-insert with validation |
| Practice 8 | Paginated query function (LIMIT / OFFSET) |
| Practice 8 | Delete procedure by username or phone |

**Do not re-implement anything from the list above.**

---

## 3. Tasks

### 3.1 Extended Contact Model

Update the database schema to support richer contact data:

1. **Multiple phone numbers per contact** — create a separate `phones` table with a foreign key to `contacts` (1-to-many). Each phone has a type: `home`, `work`, or `mobile`.
2. **Email address** — add an `email` field to the contacts table.
3. **Birthday** — add a `birthday` field (`DATE` type).
4. **Contact group/category** — create a `groups` table (`Family`, `Work`, `Friend`, `Other`) and link each contact to a group via a foreign key.

Example schema extension:
```sql
CREATE TABLE groups (
    id   SERIAL PRIMARY KEY,
    name VARCHAR(50) UNIQUE NOT NULL
);

ALTER TABLE contacts
    ADD COLUMN email    VARCHAR(100),
    ADD COLUMN birthday DATE,
    ADD COLUMN group_id INTEGER REFERENCES groups(id);

CREATE TABLE phones (
    id         SERIAL PRIMARY KEY,
    contact_id INTEGER REFERENCES contacts(id) ON DELETE CASCADE,
    phone      VARCHAR(20)  NOT NULL,
    type       VARCHAR(10)  CHECK (type IN ('home', 'work', 'mobile'))
);
```

---

### 3.2 Advanced Console Search & Filter

Extend the console interface to support:

1. **Filter by group** — show only contacts belonging to a selected category.
2. **Search by email** — partial match (e.g. searching `gmail` returns all Gmail contacts).
3. **Sort results** — allow the user to sort the output by: name, birthday, or date added.
4. **Paginated navigation** — the existing pagination function from Practice 8 is already in the DB; now build a console loop that lets the user navigate pages with `next` / `prev` / `quit`.

---

### 3.3 Import / Export

1. **Export to JSON** — write all contacts (including phones and group) to a `.json` file.
2. **Import from JSON** — read contacts from a `.json` file and insert them into the DB. On duplicate (same name), ask the user: skip or overwrite.
3. **Extend CSV import** — update the existing CSV importer from Practice 7 to handle the new fields (`email`, `birthday`, `group`, phone type).

---

### 3.4 New Stored Procedures (PL/pgSQL)

Add the following server-side objects (do not duplicate procedures from Practice 8):

1. **Procedure** `add_phone(p_contact_name VARCHAR, p_phone VARCHAR, p_type VARCHAR)` — adds a new phone number to an existing contact.
2. **Procedure** `move_to_group(p_contact_name VARCHAR, p_group_name VARCHAR)` — moves a contact to a different group; creates the group if it does not exist.
3. **Function** `search_contacts(p_query TEXT)` — extends the Practice 8 pattern-search to also match against `email` and all phones in the `phones` table (since the schema now has multiple phones in a separate table).

---

### 3.5 Save to GitHub

Example repository structure:
```
TSIS1/
├── phonebook.py
├── config.py
├── connect.py
├── schema.sql
├── procedures.sql
└── contacts.csv
```

---

## 4. What You Must Complete

- ✅ Updated schema: `phones` table, `groups` table, `email` and `birthday` fields
- ✅ Console: filter by group, search by email, sort by name / birthday / date
- ✅ Console: paginated navigation using the existing DB function
- ✅ Export contacts to JSON
- ✅ Import contacts from JSON with duplicate handling
- ✅ Procedure `add_phone`
- ✅ Procedure `move_to_group`
- ✅ Function `search_contacts` covering all fields and all phone numbers
- ✅ Push to GitHub with clear commit messages
