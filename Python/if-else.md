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

## List:

```
myList=["a", "b", "c"]
print(myList)
print(len(myList))
list1=["apple", "banana", "cherry"]
list2=[1,2,3,4,5]
list3=[True, False, True]
print(list1)
print(list2)
print(list3)

list4=[True, 10,"Kavi", 20, "Padma"]
print(list4)

print(type(list1)) # <class 'list'>

thisList=list(("Apple", "banana", "cherry"))
print(thisList)

```

```
myList=("Apple", "banana", "cherry")
print(myList[1]) # banana
print(myList[-1]) # cherry , -1 refers to the last item
print(myList[-2]) # banana, -2 refers to the last second item
print(myList[-3]) # Apple
```

### age is odd or even
```
age=int(input())
if age%2==0:
    print("even")
elif age%2!=0:
    print("odd")
else:
    print("zero")
```
### grade calculation
```
def get_grade(score):
    if score >=90 and score<=100:
        return "A"
    elif score>=80 and score<=89:
        return "B"
    elif score>=70 and score<=79:
        return "C"
    elif score>=60 and score<=69:
        return "D"
    else:
        return "F"

score=float(input())
grade=get_grade(score)
print(f"{grade}")
```

### Leap year or not:
```
def isLeapYear(year):
    if (year%4==0 and year%100!=0) or (year%400==0):
        return True
    else:
        return False
        
year=int(input())
if isLeapYear(year):
    print("yes")
else:
    print("no")
```
### temperature converter:
```
def converted(temp, scale):
    if scale=="C":
        return (temp * 5/9) + 32
    elif scale=="F":
        return (temp - 32) * 5/9
    else:
        return "Invalid scale"

temp=float(input())
scale=input().upper()
celcius=converted(temp, scale)
print(f" {celcius}")
```
### printing in new line
```
print("padma\nkavi\namma")
```
