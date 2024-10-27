* Python Loops, list
### Print first 10 numbers using a for loop
```
num=int(input());
for i in range(num):
    print(i)
"""
11
0
1
2
3
4
5
6
7
8
9
10
"""
```

### Print sum of all even numbers from 2 to 20
```
sum=0
for i in range(2,22,2): //2 --> start,  22 --> end (exclusive), 2--> increments by 2
    sum=sum+i
print(sum)
"""
110 //sum
"""
```

### Print sum of all even numbers from 1 to 10
```
sum=0
for i in range(1,10,2):
    sum=sum+i
print(sum)
"""
25 //sum of odd
"""
```

```
1. import keyword
   print(keyword.kwlist)

2. print(help('if'))

3. import keyword
   print(keyword.iskeyword('if'))
   output: True
```
* keyword.kwlist: It return a sequence containing all the keywords defined for the interpreter.
* keyword.issoftkeyword(s): Return True if s is a Python soft keyword. New in version 3.9
* keyword.softkwlist: Sequence containing all the soft keywords defined for the interpreter. New in version 3.9

## Types of keywords:
* Python h\has 36 keywords

### Value keywords
1. True
2. False
3. None

### Operator keywords:
1. and
2. or
3. not
4. is (compare as equal or not)
5. in

### Conditional keywords:
1. if, elif, else

### Iterative and transfer keywords:
for, while, break, continue, else

### Structure keywords:
1. def
2. pass



### Returning keyword:
1. return
2. yeild

```
x = 10
y = 11 
z = 10
print(x is y) 
print(x is z)
"""
False
False
"""
```

```
list=[1,2,3,4,5,6]
num=40
if num in list:
    print("Yes")
else:
    print("No")
"""
No
"""
```

### for loop
```
for i in range(5):
    print(i, end=' ')
"""
0 1 2 3 4
"""
```

### while loop
```
n=0
while n<5:
    print(n, end=' ')
    n+=1
"""
0 1 2 3 4
"""
```
### pass keyword
* pass keyword: create syntactically empty function
```
def add(n1, n2):
    pass
add(10,20)
"""

"""
```

### return keyword
```
def add(n1, n2):
    return n1+n2
print('sum:', add(10,20))
"""
sum: 30
"""
```

```
name = "padma "
print(name*3)
"""
padma padma padma
"""
```

### floor division to get output as integer:
```
a=5;
b=2;
print(a/b)
print(a//b)
"""
2.5
2
"""
```

### Exponentiation
```
a=2
print(a**3)
print(a**4)

"""
8
16
"""
---> ais base 3, 4 are exponents
```

```
a=True
if not a:
    print(a)
else:
    print("do nothing")
"""
do nothing
"""
```

### "is not" operator
```
x=10
y=20
z=20
print(x is not y)
print(y is not z)
print(z is not x)
"""
True
False
True
"""
```

### Type casting
* int to complex
```
num=10;
print(type(num).__name__)
complexNum=complex(num)
print(complexNum)
print(type(complexNum).__name__)

"""
int
10+0j
complex
"""
```

* boolean to complex
```
boolT, boolF=True, False
print(type(boolT).__name__, type(boolF).__name__)
ComplexT, ComplexF = complex(boolT), complex(boolF)
print(type(ComplexT).__name__, type(ComplexF).__name__)

"""
bool bool
complex complex
"""
```
