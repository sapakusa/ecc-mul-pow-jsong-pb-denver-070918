#### 2.1. Solve these equations in \\(F_{31}\\):

\\(24\cdot19=?\\)

\\(17^3=?\\)

\\(5^5\cdot18=?\\)

#### 2.2. Write a program to calculate \\(0k, 1k, 2k, 3k, ... 30k\\) for some k in \\(F_{31}\\).  Notice anything about these sets?

#### 2.3. Write a program to calculate \\(k^{30}\\) for all k in \\(F_{31}\\). Notice anything?

#### 2.4. Make [these tests](/edit/session1/ecc.py) pass:
```
ecc.py:FieldElementTest:test_mul
ecc.py:FieldElementTest:test_pow
```


```python
# Exercise 2.1

# remember that ** is the exponentiation operator
prime = 31
# 24*19=?
# 17^3=?
# 5^5*18=?
```


```python
# Exercise 2.2

from random import randint

prime = 31
k = randint(1,prime)

# use range(prime) to iterate over all numbers from 0 to 30 inclusive
```


```python
# Exercise 2.3

prime = 31

# use range(1, prime) to iterate over all numbers from 1 to 30 inclusive
```


```python
# Exercise 2.4

reload(ecc)
run_test(ecc.FieldElementTest('test_mul'))
run_test(ecc.FieldElementTest('test_pow'))
```
