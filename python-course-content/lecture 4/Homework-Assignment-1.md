### Assignment 1

1. Find the output of the following programs (manually):

> Note: Please do this exercise manually do not use python interpreter to get your answers

```
x = 7
if x > 2 or x%7 == 0:
  print("value is ok")
else:
  print("invalid value")
```

---------------------------------------

```
x,y = [2,4]
if (x+y)%2 == 0:
  print("Sum of values is even")
elif x%2 == 0:
  print("x is even")
elif y%2 == 0:
  print("y is even")
else:
  print("nothing is even")
```


----------------------------------------

```
x,y = ["hello","ok"]
if x<y:
  print("x is lexicographically smaller than y")
print("Done")
```

----------------------------------------

```
x = 12
y = 23
z = 5
if x <= z and y <= z and z > 5:
  print("valid")
if x < 40:
  print("valid again")
if z == 4:
  print("valid once again")

print("Done!!")
```

2. Find the error in the following program.

```
# This program should print the greatest number of all the three numbers entered

a = int(input("Enter the first number:\n"))
b = int(input("Enter the second number:\n"))
c = int(input("Enter the third number:\n"))

if a > b and a > c:
  print("a is greatest of all")
elif b > a:
  print("b is greatest of all")
else:
  print("c is greatest of all")

```

3. Write a menu based program which takes two integer values as input and performs the operation selected by the user.

```

Menu:

1. find average of numbers
2. find smallest value
3. sum of both the values

```

4. Create a flow chart for the following programs.


```
name = input("Enter your name:")
print("Hello",name,sep=\n)
```

---------------------------------------

```

x = 2 
if x < 2:
  print("x is smaller")
else:
  print("x is not smaller than 2")

```

5. Find & Explain the output of the following program, when the specified values are given as input:

```
x = input("Enter a vegetable name")
y = input("Enter the color of the vegetable")

if(y == "red"):
  if(x == "pepper"):
    print("red pepper")
  print("the color was red")
if(y == "blue"):
  print("the color was blue")
  if(x == "eggplant"):
    print("the vegetable was eggplant")
  else:
    print(x);
else:
  print("can't do anything!!")




# first input: y = red, x = pepper
# second input: y = red, x = cabbage
# third input: y = blue, x = onion
# fourth input: y = blue, x = eggplant
# fifth input: y = green, x = broccoli

```

6. Fix the following program in such a way that it correctly prints if a number is divisible by 3:

```
# This program should print if a value is divisible by 3, if not, then should print that value is not divisible by 3

a = int(input("Enter a value"))

if value%6 == 0:
  print(a,"is divisible by 3")

print(a,"is not divisible by 3")

```
