# Python Common Practices

## Read files from a package directory

Sometime you need to load some static files (html template, sql template, etc.) from a directory. 

Suppose you have a file structure as:
```bas
.
└── src
    ├── services.py
    ├── templates
        ├── __init__.py
        ├── sql_1.sql
        └── sql_2.sql
```

In order to load the sql file content in `services.py`:

```python
from importlib.resources import files
import templates as templates_path

sql = files(templates_path).joinpath('sql_1.sql').open('r', encoding=encoding).read()
```


