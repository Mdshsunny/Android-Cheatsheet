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
""")
```

2. Add multiple data into Database TABLE
```python
multiple_data = [
("Sajeda", "Khatun", "sajeda@gamil.com",35),
("Abdus", "Satter", "satter@gamil.com",43),
("Abdul", "Alim", "alim@gamil.com",26)
]
cursor.executemany("INSERT INTO customer VALUES (?,?,?,?)", multiple_data)
```

> READ

1. Read data from db
```python
cursor.execute("SELECT rowid, * FROM customer")
```

> UPDATE

```python
cursor.execute("UPDATE customer SET first_name='Md. Sajjad Hossain' WHERE rowid=1")
cursor.execute("UPDATE customer SET first_name='Md. Sajjad Hossain', age=18 WHERE rowid=1")

```

> DELETE

```python
cursor.execute("DELETE FROM customer WHERE rowid=3")
```

> Where Clause

```python
cursor.execute("SELECT rowid, * FROM customer WHERE rowid>=3")
cursor.execute("SELECT rowid, * FROM customer WHERE last_name='Sunny'")
```

>LIKE Clause

```python
cursor.execute("SELECT rowid, * FROM customer WHERE last_name LIKE 'S%'")
cursor.execute("SELECT rowid, * FROM customer WHERE email LIKE '%gamil.com'")
cursor.execute("SELECT rowid, * FROM customer WHERE last_name LIKE '%te%'")
```

> AND OR Clause

```python
cursor.execute("SELECT rowid, * FROM customer WHERE rowid>=3 AND first_name='Abdus'")
cursor.execute("SELECT rowid, * FROM customer WHERE rowid>=3 OR first_name='Md.'")
```

> ORDER BY
1) ASC 
2) DESC
```python
cursor.execute("SELECT rowid, * FROM customer ORDER BY age DESC")
```

> LIMIT

```python
cursor.execute("SELECT rowid, * FROM customer LIMIT 3")
```

> DROP TABLE

```python
cursor.execute("DROP TABLE customer")
```
