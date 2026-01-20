# mypy_ty_diffs
document differences between ty and mypy checks


---
```
def variable_change_type()-> None:
    a = 10
    a = "now a string"    
    print(a)
```
* mypy: `Incompatible types in assignment (expression has type "str", variable has type "int")`
* ty: nothing

```
def no_annotation(a):
    print("hello")
```
* mypy with `disallow_untyped_defs = True` : `Function is missing a type annotation`
* ty: nothing
