>Initializing a database 

```python
import sqlite
db = sqlite.connect("database.db")
cursor = db.cursor()
# Every sqlite command here
db.commit()
db.close()
```

> Data Types in SQLite3
1. NUMERIC
2. TEXT
3. INTEGER
4. REAL
5. BLOB
6. NULL (Default if value not added)

> Create a Table

```python

cursor.execute("""
    CREATE TABLE customer (
        first_name TEXT,
        last_name TEXT,
        email TEXT,
        age INTEGER
    )
""")
```

> CREATE

1. Add one data into Database TABLE
```python
cursor.execute("""
    INSERT INTO customer VALUES 
    ("Saniya", "Akter", "saniya@gamil.com",9)
