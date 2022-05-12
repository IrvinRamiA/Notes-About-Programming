# Table of Contents
* [List Comprehensions](#list-comprehensions)

## List Comprehensions
***
List comprehensions offers a shorter syntax when you want to create a new list based on the values of an existing list.

```python
fruits = ["apple", "banana", "cherry", "kiwi", "mango"]
new_list = []

for x in fruits:
    if "a" in x:
        new_list.append(x)

print(new_list)

# OR

new_list2 = [x for x in fruits if "a" in x]
print(new_list2)
```

### Syntax
***
> new_list = [expression for item in iterable if condition == True]