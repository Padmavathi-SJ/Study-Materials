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
