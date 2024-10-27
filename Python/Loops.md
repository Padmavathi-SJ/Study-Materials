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
1. for
2. while
3. break
4. continue
5. else

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

### complex num to string
```
complexNum=5+5j
word=str(complexNum)
print(word)
print(type(word).__name__)
"""
(5+5j)
str
"""
```

### Controll Flow Statements
```
num=6
if num > 5:
    print(num * num)
print("no")
"""
36
no
"""
```

```
password=input('enter password: ')
if password == "padma":
    print("correct")
else:
    print("incorrect")
"""
enter password: padma
correct
"""
```

```
l=input('enter a char: ')
if l.isdigit():
    print("yes")
elif l.isalpha():
    print("alphabet")
else:
    print("spl char")
"""
k
alphabet
"""
```

```
name=input().upper();
print(name)
print(name[1])
"""
padma
PADMA
A
"""
```

```
for i in range(1, 11):
    print(i, end=' ')
"""
1,2,3,4,5,6,7,8,9,10
"""
```

```
for i in range(1,10):
    print(i, end=' ')
    if i==5:
        print("\nloop stopped")
        break;

"""
1 2 3 4 5
loop stopped
"""
```

```
for i in range(3,8):
    if i==5:
        continue
    else:
        print(i)
"""
3
4
6
7
"""
```

```
months = ['Jan', 'feb', 'mar', 'apr']
for mon in months:
    pass
print(months)
"""
['Jan', 'feb', 'mar', 'apr']
"""
```

```
start=int(input())
end=int(input())
for i in range(start, end+1):
    square=i ** 2
    print("square of", i, "is:", square)
"""
1
5
square of 1 is: 1
square of 2 is: 4
square of 3 is: 9
square of 4 is: 16
square of 5 is: 25
"""
```

```
nums=list(input());
print(nums)
"""
12345
['1', '2', '3', '4', '5']
"""
```

```
nums=tuple(input().split())
print(nums)
"""
Hi I am padma
('Hi', 'I', 'am', 'padma')
"""
```

```
start,end=map(int, input().split())
evenCount,oddCount=0,0
for i in range(start, end+1):
    if i%2==0:
        evenCount +=1
    else:
        oddCount +=1
print("evenCount:",evenCount)
print("oddCount:",oddCount)
"""
1 10
evenCount: 5
oddCount: 5
"""
```

```
num=int(input())
for i in range(num, 0, -1): //num=start, 0=end, -1=increment/decrement part
    print(i)

"""
5
5
4
3
2
1
"""
```

### pattern printing
```
row=int(input())
for i in range(1, row+1):
    for j in range(1, i+1):
        print("*", end=' ')
    print('')
"""
5 //row
*
* *
* * *
* * * *
* * * * *
"""
```

```
nums=[1,2,3,4,5]
size=len(nums)
for i in range(size):
    print("index:", i, " ", "value:", nums[i])
"""
index: 0   value: 1
index: 1   value: 2
index: 2   value: 3
index: 3   value: 4
index: 4   value: 5
"""
```
### seperate characters of a word
```
name="Padma"
name=name.upper()
for i in name:
    print(i, end=' ')
"""
P A D M A
"""
```

### reverse letters of the word
```
name="Padma"
name=name.upper()
size=len(name)
for i in range(size, 0, -1): //size=start, 0=end, -1=decrement
    print(name[i-1], end=' ')
"""
A M D A P
"""
```
### sepeate words from a sentence by using split by *
```
sentence="Hi*mummy*I*will*make*you*happy*mummy!"
for word in sentence.split('*'):
    print(word)
"""
Hi
mummy
I
will
make
you
happy
mummy!
"""
```

### sepeate words from a sentence by using split by space
```
sentence="Hi mummy I will make you happy mummy!"
for word in sentence.split():
    print(word)
"""
Hi
mummy
I
will
make
you
happy
mummy!
"""
```

### Iterate through dictionary using for loop
```
dict1={1: "apple", 2: "banana", 3: "cherry"}
for key in dict1:
    print(key)
"""
1
2
3
"""
```

### print key with values:
```
dict1={1: "apple", 2: "banana", 3: "cherry"}
for key in dict1:
    print(key, "-->", dict1[key])
"""
1 --> apple
2 --> banana
3 --> cherry
"""
```

### print values only
```
dict1={1: "apple", 2: "banana", 3: "cherry"}
for value in dict1.values():
    print(value)
"""
apple
banana
cherry
"""
```


## while loop
```
c=0
num=int(input())
while num>10:
    num=num/3
    c=c+1
print(c)
"""
180 //num
3 //diving time
"""
```

```
while True:
    print("Hello")
"""
Hello
Hello
....infinity times
"""
```
### break if char is digit
```
name="Padma253vathi"
size=len(name)
i=0
while i<size:
    if name[i].isdecimal(): //we can use "char.isdigit()" also
        break
    print(name[i], end=' ')
    i=i+1
"""
p a d m a
"""
```

### print only if character
```
name="Padma253vathi"
size=len(name)
i=0
while i<size:
    if name[i].isalpha():
        print(name[i], end=' ')
    i=i+1
"""
p a d m a v a t h i
"""
```

### Pattern printing
```
i=1
while i<6:
    j=0
    while j<i:
        print("*", end=' ')
        j=j+1
    print('')
    i=i+1
"""
*
* *
* * *
* * * *
* * * * *
"""
```

### break statement
```
nums=[10,20,30,140,150]
for i in nums:
    if i>100:
        break;
    print(i)
"""
10
20
30
"""
```

### if space encountered break
```
name="Padma vathi"
size=len(name)
i=0
while i<size:
    if name[i].isspace():
        break;
    print(name[i], end=' ')
    i=i+1
"""
p  a d m a
"""
```

### Multiplication table
```
num=int(input())
i=1;
while i<11:
    print(i,"x",num,"=", num*i)
    i=i+1
"""
5 //num of table
1 x 5 = 5
2 x 5 = 10
3 x 5 = 15
4 x 5 = 20
5 x 5 = 25
6 x 5 = 30
7 x 5 = 35
8 x 5 = 40
9 x 5 = 45
10 x 5 = 50
"""
```

### remove leading and trailing spaces
```
name="  pa d  m a   vathi  "
size=len(name)
i=0;
while i<size:
    if name[i].isalpha():
        print(name[i], end='')
    i=i+1
"""
padmavathi
"""
```

```
for i in range(1,11):
    for j in range(1,11):
        print(i*j, end=' ')
    print()
"""
1 2 3 4 5 6 7 8 9 10 
2 4 6 8 10 12 14 16 18 20 
3 6 9 12 15 18 21 24 27 30 
4 8 12 16 20 24 28 32 36 40 
5 10 15 20 25 30 35 40 45 50 
6 12 18 24 30 36 42 48 54 60 
7 14 21 28 35 42 49 56 63 70 
8 16 24 32 40 48 56 64 72 80 
9 18 27 36 45 54 63 72 81 90 
10 20 30 40 50 60 70 80 90 100 
"""
```

### pattern 
```
row=5;
for i in range(1, row+1):
    for j in range(1, i+1):
        print("*", end=' ')
    print()
"""
*
* *
* * *
* * * *
* * * * *
"""
```

```
names=["padma", "kavi", "akil"]
for name in names:
    count=0;
    while count<5:
        print(name, end=' ')
        count=count+1
    print()
"""
padma padma padma padma padma 
kavi kavi kavi kavi kavi 
akil akil akil akil akil 
"""
```

### pattern
```
row=5
col=3
for i in range(1, row+1):
    for j in range(1, col+1):
        print("*", end='')
    print()
"""
***
***
***
***
***
"""
```

### print the multiples if not iand j equal
```
first=[2,4,6]
second=[2,4,6]
for i in first:
    for j in second:
        if i==j:
            continue
        print(i, '*', j, '=', i*j)
"""
2 * 4 = 8
2 * 6 = 12
4 * 2 = 8
4 * 6 = 24
6 * 2 = 12
6 * 4 = 24
"""
```

### merge two lists
```
first=[1,2,3,4,5]
second=[10,20,30,40,50]
final=[]
for i in first:
    for j in second:
        final.append(i+j)
print(final)

"""
[11, 21, 31, 41, 51, 12, 22, 32, 42, 52, 13, 23, 33, 43, 53, 14, 24, 34, 44, 54, 15, 25, 35, 45, 55]
"""
```

```
first=[1,2,3,4,5]
second=[10,20,30,40,50]
final=[i+j for i in first for j in second]
print(final)
"""
[11, 21, 31, 41, 51, 12, 22, 32, 42, 52, 13, 23, 33, 43, 53, 14, 24, 34, 44, 54, 15, 25, 35, 45, 55]
"""
```

```
final=[[x,y] for x in [10,20,30] for y in [30,10,50] if x!=y]
print(final)
"""
[[10, 30], [10, 50], [20, 30], [20, 10], [20, 50], [30, 10], [30, 50]]
"""
```

```
i=1;
while i<=5:
    j=1
    while j<=10:
        print(j, end='')
        j=j+1
    i=i+1
    print()
"""
12345678910 
12345678910 
12345678910 
12345678910 
12345678910
"""
```

```
a, b, c=input().split()
print(a)
print(b)
print(c)
print(b, "", c)
"""
hi padma how
hi
padma
how
padma  how
"""
```


## range() function
* range(start, stop[, step)
```
print(type(range(10)))
"""
<class 'range'>
"""
```
* examples:

```
for i in range(10):
    print(i, end=' ')
print()  

for i in range(10,16):
    print(i, end=' ')
print()  

for i in range(10,50,5):
    print(i,end=' ')
print() 

for i in range(1,10,2):
    print(i, end=' ')
print()

list1=['padma', 'kavi', 10,20,30]
for i in range(len(list1)):
    print(list1[i], end=' ')

"""
[?2004l
0 1 2 3 4 5 6 7 8 9 
10 11 12 13 14 15 
10 15 20 25 30 35 40 45 
1 3 5 7 9 
padma kavi 10 20 30 [?2004h
"""
```

```
for num in range(4):
    for i in range(num):
        print(num, end=' ')
    print()
"""
1
2 2
3 3 3
"""
```
### reverse the sequence using "reversed() function" by passing the range"
```
for i in reversed(range(10, 21)):
    print(i, end=' ')
"""
20 19 18 17 16 15 14 13 12 11 10
"""
```

```
for i in reversed(range(10, 21, 2)):
    print(i, end=' ')
print()

print(type(reversed(range(0,5))))

"""
20 18 16 14 12 10 
<class 'range_iterator'>
"""
```

```
list1=[10,20,30,40,50]
for i in range(len(list1) -1, -1, -1):
    print(list1[i], end=' ')
print()

for i in range(30,20, -2):
    print(i,end=' ')
print()

for i in range(-1, -11, -1):
    print(i, end=' ')
print()

for i in range(2 ,-5, -1):
    print(i, end=', ')

"""
50 40 30 20 10 
30 28 26 24 22 
-1 -2 -3 -4 -5 -6 -7 -8 -9 -10 
2, 1, 0, -1, -2, -3, -4, 
"""
```

### Convert range() to list
```
list1=list(range(2,10,2))
print(type(list1))

print(list1)

for item in list1:
    print(item, end=', ')
"""
<class 'list'>
[2, 4, 6, 8]
2, 4, 6, 8, 
"""
```
