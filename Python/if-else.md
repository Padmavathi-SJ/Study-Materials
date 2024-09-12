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

### printing 2 or 3 decimal points
```
num=float(input())
print(num) #12.32456987
print(f"{num:.2f}") #12.32
print(f"{num:.4f}") #12.3246
print(f"{num:.1f}") #12.3
```

###
```
num=float(input())
print(num) #12.32456987
print("%.2f" %num) # 12.37
print("%.3f" %num) # 12.365

```
* using formatr() method:
```
  num=float(input())
print(num) #12.32456987
print("{:.2f}".format(num))
print("{:.3f}".format(num))
print("{:.1f}".format(num))
```

```
num=float(input())
print(num) #12.32456987
print("{:.2f}".format(num)) # 12.33
print("{:.3f}".format(num)) # 12.325
print("{:.1f}".format(num)) # 12.3
print("%.2f is the result" %num) # 12.33 is the result
```

### Divisibility Check
```
def check(num):
    if num%5==0 and num%3==0:
        return "Yes both"
    elif num%5==0 or num%3!=0:
        return "only by 5"
    else:
        return "not both"

num=int(input());
print(check(num))
```

### Largest of Three Numbers
```
def largest(num1, num2, num3):
    if num1>=num2 and num1>=num3:
        return num1
    elif num2>=num1 and num2>=num3:
        return num2
    else:
        return num3

num1=int(input())
num2=int(input())
num3=int(input())

print(largest(num1, num2, num3))
```

### Vowel or Consonant
```
def check(char):
    if char.lower() in 'aeiou':
        return "vowel"
    else:
        return "consonant"

char=input()
print(check(char))
```
### Triangle Type
```
def check(a,b,c):
    if a+b > c and a+c>b and b+c>a:
        if a==b==c:
            return "Equilateral"
        elif a==b or b==c or a==c:
            return "Isosceles"
        else:
            return "Scalene"
    else:
        return "Not a traingle"

a=int(input())
b=int(input())
c=int(input())

print(check(a,b,c))
```
###  Month Days
```
def check(m,y):
    if m in [1,3,5,7,8,10,12]:
        return "31 days"
    elif m in [4,6,9,11]:
        return "30 days"
    elif m==2 and ((y%4==0 and y%100!=0) or (y%400==0)):
        return "29 days"
    else:
        return "28 days"

m=int(input())
y=int(input())
print(check(m,y))
```
### simple interest:
```
def interest(p,r,t):
    r=r*100
    if p>0 and r>0 and t>0:
        interest=p * r * t /100
        return interest
    else:
        return "Invalid input"

p=int(input())
r=float(input())
t=int(input())

result=interest(p,r,t)
print("%.2f" %result)

```

### getting inputs as list, tuple, set
```
thisList=list(input().split())
thisTuple=tuple(input().split())
thisSet=set(input().split())

print(thisList) 
print(thisTuple)
print(thisSet)

"""
['2', '3', '4']
('2', '3', '4')
{'sky', 'kavi'}
"""
```
### dict:
```
a=input()
pairs=a.split(',')
mydict={}
for pair in pairs:
    key, value=pair.split(':')
    mydict[key.strip()]=int(value.strip())
print(mydict)

"""
a:2,b:45
{'a': 2, 'b': 45}
"""
```

```
a=range(1,10)
print(list(a))
print(tuple(a))
print(set(a))

b=range(1,10,2)
for num in b:
    print(num)

c=range(1,10,3)
for num in c:
    print(num)

"""
[1, 2, 3, 4, 5, 6, 7, 8, 9]
(1, 2, 3, 4, 5, 6, 7, 8, 9)
{1, 2, 3, 4, 5, 6, 7, 8, 9}
1
3
5
7
9
1
4
7
10
"""
```
### char is vow or consonant
```
a=input()
if len(a)!=1:
    print("enter only one character")
elif a in 'aeiouAEIOU':
    print(f"{a} is vowel")
else:
    print(f"{a} is consonant")
```
```
num=int(input())
if num%2==0:
    print(f"{num} is even")
else:
    print(f"{num} is odd")
```

### alpha or digit or spl char:
```
a=input()
if a.isalpha():
    print(f"{a} is alpha")
elif a.isdigit():
    print(f"{a} is digit")
else:
    print(f"{a} is spl char")
```

### discount
```
age=int(input())
if age<=12:
    discount=0.50
elif age >=13 and age<=19:
    discount=0.30
elif age>=20 and age<=65:
    discount=0.1
else:
    discount=0.0

ticketPrice=50
totalPrice=ticketPrice * (1-discount)
print(totalPrice)
```

### power of (**):
```
num=int(input()) # 2
power=num ** 2 + num ** 2
print(power) # 8
```

### Compound interest:
```
p=float(input())
r=float(input())
t=int(input())
y=float(input())

r=r/100
amount=p*(1+r/t) ** (t*y)
compoundInterest=amount-p
print("%.2f" %compoundInterest)

```
