# mypy_ty_diffs
document differences between ty (version 0.0.12) and mypy checks

Issues  of interest
* https://github.com/astral-sh/ty/issues/2111

---
```
def variable_change_type()-> None:
    a = 10
    a = "now a string"    
    print(a)
```
* mypy: `Incompatible types in assignment (expression has type "str", variable has type "int")`
* ty: nothing

---
```
def no_annotation(a):
    print("hello")
```
* mypy with `disallow_untyped_defs = True` : `Function is missing a type annotation`
* ty: nothing
Note: can be covered by ruff ANN rules
