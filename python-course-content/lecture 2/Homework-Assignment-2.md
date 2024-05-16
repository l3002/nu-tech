### Assignment 2

1. Find the output of the following code (find out the output manually, do not execute these using the python interpreter):

  ```
  x = 700

  y = x + 1333

  x += 7

  print (x, y)
  ```
------
  ```
  x,y = 3 + 7j,5

  x = -2

  y -= 6

  x+=y

  y-=x

  print(x,y)
  ```
------

  ```
  a = -5

  b = 2*a

  a += a+b

  b *= a + b

  print (a,b)
  ```
-------

  ```
  p = 5 * 2

  q=p**4

  print(p,q)
  ```
---------
  ```
  p = 10+5j

  q = 20

  p *= q/3

  q += p+q*2

  print(p,q)
  ```
----------
  ```
  p = 21//5

  r -= p//q

  p -= p+q+r

  r += p+q+r

  q -= p+q*r

  print(p,q,r)
  ```

2. What is the problem with the following code fragments?

```
  a = 3 
  print(a) 
  s = a + b 
  print(s)
  b = 4
  print (b)
```
------------
```
  import = "Prateek"

  Age = 26

  Print ("your name & age are", Name + Age)
```
-------------
```
  A = 3

  S = A + 10

  A = "New"

  Q = A / 10
```
-------------

3. List all the tokens in the given program and categorize them:

```
import math

a = 1000
b = 342
c = 22
b -= 190
c += 1000-2000
a **= 3
print(a,b)

```

4. Explain why does `id()` function return same value for the given variable and what does the `id()` return?

```
  a = 100
  b = 100
  print(id(a),id(b))

```
