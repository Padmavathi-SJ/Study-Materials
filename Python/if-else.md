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
