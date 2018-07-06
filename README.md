
# Finite Field Multiplication and Exponentiation

Just as we defined a new addition ($+~f~$) for Finite Fields that was _closed_, we can also define a new multiplication for Finite Fields that's also closed. By multiplying the same number many times, we can also define exponentiation or power. In this section, we'll go through exactly how to define this using modulo arithmetic.

As you most likely learned in elementary school, multiplication is simply adding a number many times.

5⋅3 = 5+5+5 = 15

8⋅17 = 8+8+8+...(17 total 8's)...+8 = 136

We can define multiplication on a Finite Field the same way. Operating in $F~19~$ once again,

$5⋅~f~3 = 5+~f~5+~f~5$

$8⋅~f~17 = 8+~f~8+~f~8+~f~...(17 total 8's)...+~f~8$

We already know how to do the right side, and that yields a number within the F~19~ set:

$5⋅~f~3 = 5+~f~5+~f~5 = 15 % 19 = 15$

$8⋅~f~17 = 8+~f~8+~f~8+~f~...(17 total 8's)...+~f~8 = (8⋅17) % 19 = 136 % 19 = 3$

Note that the second result is pretty unintuitive. We don't normally think of 8⋅17 as 3, but that's part of what's necessary in order to define multiplication in a way that's closed. That is, the result of field multiplication is always in the set {0,1,...18}.

Exponentiation is simply multiplying a number many times.

7^3 = 7⋅7⋅7 = 343

In a finite field, we can do exponentiation using modulo arithmetic as before.

In $F~19~$:

7^3 = 343 % 19= 1

9^12 = 7

Exponentiation again gives us counter-intuitive results. We don't normally think 7^3^=1 or 9^12^=7. Again, part of why Finite Fields work is because the operations *always* result in a number within the field.

### Try solving these equations in \\(F_{31}\\):

\\(24\cdot19=?\\)

\\(17^3=?\\)

\\(5^5\cdot18=?\\)


```python
# remember that ** is the exponentiation operator
prime = 31
# 24*19=?
# 17^3=?
# 5^5*18=?
```

#### Write a program to calculate \\(0k, 1k, 2k, 3k, ... 30k\\) for some k in \\(F_{31}\\).  Notice anything about these sets?


```python
from random import randint

prime = 31
k = randint(1,prime)

# use range(prime) to iterate over all numbers from 0 to 30 inclusive
```

#### Write a program to calculate \\(k^{30}\\) for all k in \\(F_{31}\\). Notice anything?


```python
prime = 31

# use range(1, prime) to iterate over all numbers from 1 to 30 inclusive
```

### Test Driven Exercise

Create the `__mul__` and `__pow__` methods for your library:


```python
from ecc import FieldElement

class FieldElement(FieldElement):

    def __mul__(self, other):
        if self.prime != other.prime:
            raise RuntimeError('Primes must be the same')
        # self.num and other.num are the actual values
        # self.prime is what you'll need to mod against
        # You need to return an element of the same class
        # use: self.__class__(num, prime)
        pass

    def __pow__(self, n):
        # remember fermat's little theorem:
        # self.num**(p-1) % p == 1
        # you might want to use % operator on n
        pass
```
