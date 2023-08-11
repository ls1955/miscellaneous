Suppose there is this project structure in a Window machine:
```
some_directory/
  foo.py
  module_name/
    bar.py
```
Where bar.py import something from foo via something like: ```from some_directory.foo import potato```

If Python could not find the module, try:
```
cd some_directory
set PYTHONPATH=%PYTHONPATH%;.
python module_name/bar
```

If Python still could not find the damn thing, try backing to an upper directory.
