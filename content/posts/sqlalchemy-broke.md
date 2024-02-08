+++
title = 'Did SQLAlchemy Break?'
date = 2023-05-04
draft = false
tags = ['python']
description = 'Why did the SQLAlchemy ORM go to therapy? Because it had relationship issues!'
+++

### TL;DR 
- The new version of SQLAlchemy has caused a compatibility issue with the `read_sql_query()` function in pandas. 
- When calling `read_sql_query()` and utilizing an SQLAlchemy engine to read an SQL query into a DataFrame, an `AttributeError` is raised.
- To resolve this error, you can rectify it by enclosing the query string within SQLAlchemy's `text()` function and passing a connection object instead of an engine object.

```py
import pandas as pd
from sqlalchemy import create_engine, text

engine = create_engine("<Connection String>")
query = "SELECT * FROM table"

df = pd.read_sql_query(text(query), engine.connect())
```

## SQLAlchemy broke! 

A little while ago, I was trying to read data from an SQL database using SQLAlchemy in Python.  

SQLAlchemy is a Python library that facilitates working with databases using Python code.

I was attempting to retrieve data from a database by utilizing Pandas' `read_sql_query()` function along with an SQLAlchemy engine.

```py
import pandas as pd
from sqlalchemy import create_engine

engine = create_engine("connection string")
query = f"SELECT * FROM table"
df = pd.read_sql_query(query, engine)
```

I kept getting an `AttributeError`.
```py
AttributeError: 'OptionEngine' object has no attribute 'execute'
```

I felt devastated initially because I am a big fan of SQLAlchemy, and I thought it was no longer compatible with Pandas.

However, my assumption was incorrect. It turned out that the latest version of SQLAlchemy removed the `engine.execute()` function that the `read_sql_query()` function in Pandas relied on.

To address this issue, I discovered a helpful workaround. I created a `TextClause` for the SQL query string using SQLAlchemy's `text()` function. Then, instead of using the engine object, I utilized a connection object.

```py
# fix
import pandas as pd
from sqlalchemy import create_engine, text

engine = create_engine("connection string")
query = f"SELECT * FROM table"
df = pd.read_sql_query(text(query), engine.connect())
```

**Note:** Pandas 2.0.0 is now available, and the recommended fix is actually to upgrade to the latest Pandas version.
