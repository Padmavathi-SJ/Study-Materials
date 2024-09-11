### 01
```
a=10
b=10
if a>b:
    print("A is greater than b")
elif a==b:
    print("a and b are equal")
elif a<b:
    print("a is less than b")
else:
    print("nothing")
```

* if we have only one statement to execute, we can put it on the same line as the if statement:
```
a=10
b=5
if a>b: print("a is greater than b")
```

* If you have only one statement to execute, one for if, and one for else, you can put it all on the same line:
```
a=10
b=5
print("A") if a>b else print("B")
```

###  AND operator
```
a=100
b=50
c=200
if a>b and c>a:
    print("Both conditions are equal")
```

* We can also have multiple else statements on the same line
```
a=10
b=10
print("A") if a>b else print("equal") if a==b else print("B")
```

### OR operator
```
a=100
b=50
c=200
if a>b or a>c:
    print("Atlease one is true")
```

### Nested if:
```
a=41

if a>10:
    print("yes above 10")
if a>20:
    print("yes above 20 also")
else:
    print("but not above 20")
```
### NOT operator:
```
a=100
b=50
if not b>a:
    print("b is NOT greater than a")

output:
* yes above 10
* yes above 20 also
```

* if statement cannot be empty, but if you for some reason have an if statement with no content, put in the "pass" statement to avoid getting an error
```
a=10
b=200

if b>a:
    pass
```
