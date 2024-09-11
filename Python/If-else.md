### 01. print a statement

```
print("Hello Mummy!")
```
### 02. if condition:
```
if 5>2:
    print("Five is greater than two!")
```
### 03. two if conditions:
```
if 5>2:
    print("Five is greater than two!")
if 2<5:
    print("two is less than five!")
```
### 04. 
**In python no need to declare a variable**
```
x=5
y="Hello, Mummy!"
```
## Variables:
```
x=100
y="Kavi"
print(x)
print(y)
```
**Variables do not need to be declared with any particular type, and can even change type after they have been set**
```
x=100
x="Padma"
x=500
print(x)
```
* output: 500

**If we want to specify the data type of a variabke, this can be done with typecasting**

```
x=str(3) # x will be 3
x=int(3) # x will be 3
x=float(3) # x wil be 3.0
```
* We can get the data type of a varibale with the "type()" function
```
x=5
y="Padma"
z=3.0
print(type(x)) # <class 'int'>
print(type(y)) # <class 'str'>
print(type(z)) # <class 'float'>
```
* String variables can be declared either by using single or double quotes
```
x="padma"
y='mummy'
print(x) # Padma
print(y) # Mummy
```
* Variables names are case-sensitive
```
a=4
A="Padma"
print(a) # 4
print(A) # Padma # A will not override a
```
## Data types:
```
x=50 # <class 'int'>
x=20.5 # <class 'float'>
x="Padma" # <class 'str'>
x=1j # <class 'complex'>
x=["apple", "banana", "cherry"] # <class 'list'>
x=("apple", "banana", "cherry") # <class 'tuple'>
x={"apple", "banana", "cherry"} # <class 'set'>
x={"name" : "padma", "age": 19} # <class 'dict'>
x=range(5) # <class 'range'>
x=True # <class 'bool'>
x=False # <class 'bool'>
```
```
x=int(20);
x=str("Padma")
x=float(20.5)
x=complex(1j);
x=list(("apple", "banana", "cherry"))
x=tuple(("apple", "banana", "cherry"))
x=set(("spple", "banana", "cherry"))
x=dict(name="Padma", age=19)
x=range(6)
x=bool(5)
```
### Numbers:
```
x=1
y=123456789456321
z=-12345678
print(type(x)) # <class 'int'>
print(type(y)) # <class 'int'>
print(type(z)) # <class 'int'>
```
### Float:
* Float can be scientific numbers with an 'e' to indicate the power of 10.
```
x=35e3
y=12E4
z=-87.7e100
print(type(x)) # <class 'float'>
print(type(y)) # <class 'float'>
print(type(z)) # <class 'float'>
```

### complex
* complex numbers are written with "j" as the imaginary part
```
x=3+5j
y=5j
z=-6j
print(type(x)) # <class 'complex'>
print(type(y)) # <class 'complex'>
print(type(z)) # <class 'complex'>
```
### Type Comversion:
```
x=1
y=5.2
z=5j

# convert to other datatypes

a=int(y)
b=float(x)
c=complex(x)

print(a) # 5
print(b) # 1.0
print(c) # 1+0j 

print(type(a)) # <class 'int'>
print(type(b)) # <class 'float'>
print(type(c)) # <class 'complex'>
```

### Random Number:
* Python does not have a random() function to make random number, but python has a built-in module calles "random" that can be used to make random numbers:
```
import random

print(random.randrange(1,20))
```
* it will print a random number from 1 to 20.

### Casting
```
x=str("s1");
y=str(2)
z=str(3.0)

print(x) # s1
print(y) # 2
print(z) # 3.0
```
