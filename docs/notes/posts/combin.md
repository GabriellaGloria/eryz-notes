---
date: 2024-12-14
categories:
    - Documentation
tags:
    - Random
---

# Combinatorics 🐠🫶
will dump more not-so-combinatorics 🤡 formulas here ..
## Basic Combinatorics ✨
Practice problems :</br>
1. [102 Combinatorics](https://rainymathboy.wordpress.com/wp-content/uploads/2011/01/102-combinatorial-problems.pdf)</br>
2. [AOPS](https://artofproblemsolving.com/?srsltid=AfmBOopK4VITMFbsChjGhXz-v05ljqJuoPFrqG4YwBQ64HOxi_vDlzk3)</br>


<h3>Permutations 🌸</h3>

The number of ways to arrange $$\(r\) objects from \(n\)$$ distinct objects (order matters) is called a permutation and is given by
:
$$
P(n, r) = \frac{n!}{(n - r)!}
$$

Where:</br>
- $$\(n\)$$ is the total number of objects. </br>
- $$\(r\)$$ is the number of objects to arrange. </br>

<h3>Combinations 🌺</h3>

The number of ways to choose $$\(r\) objects from \(n\)$$ distinct objects (order does not matter) is called a combination and is given by
:
$$
C(n, r) = \binom{n}{r} = \frac{n!}{r!(n - r)!}
$$

Where:</br>
- $$\(n\)$$ is the total number of objects.</br>
- $$\(r\)$$ is the number of objects to choose.</br>

<h3>Circular Permutations 🦢</h3>

For circular arrangements, the number of ways to arrange $$\(r\)$$ objects in a circle is given by
:
$$
C_{\text{circ}}(n, r) = \frac{(n - 1)!}{(n - r)!}
$$

Where: </br>
- $$\(n\)$$ is the total number of objects.</br>
- $$\(r\)$$ is the number of objects to arrange in a circle.</br>

<h3>Stars and Bars Theorem 🌻</h3>

The "Stars and Bars" theorem helps count the number of ways to distribute $$\(r\)$$ indistinguishable items (stars) into $$\(n\)$$ distinct groups (bins). The number of ways is given by
:
$$
\binom{r + n - 1}{n - 1}
$$

Where:</br>
- $$\(r\)$$ is the number of indistinguishable objects (stars).</br>
- $$\(n\)$$ is the number of distinct groups (bins).</br>

<h3>Multinomial Coefficients 🐾</h3>

The number of ways to arrange $$\(n\)$$ objects, where there are groups of indistinguishable objects (for example, $$\(r_1\)$$ objects of one type, $$\(r_2\)$$ of another type, etc.) is given by
:
$$
\binom{n}{r_1, r_2, \dots, r_k} = \frac{n!}{r_1! r_2! \dots r_k!}
$$

---

## Binomial Theorem 🐦‍🔥

Binomial theorem provides a way to expand powers of a binomial expression $$\( (x + y)^n \)$$ into a sum of terms involving coefficients, powers of $$\( x \)$$, and powers of $$\( y \)$$
    .
$$
(x + y)^n = \sum_{k=0}^{n} \binom{n}{k} x^{n-k} y^k
$$

Where:</br>
- $$\( n \)$$ is a non-negative integer.</br>
- $$\( \binom{n}{k} = \frac{n!}{k! (n-k)!} \)$$ is the binomial coefficient.

Example:</br>
For $$\( n = 3 \)$$:
$$
(x + y)^3 = \binom{3}{0} x^3 y^0 + \binom{3}{1} x^2 y^1 + \binom{3}{2} x^1 y^2 + \binom{3}{3} x^0 y^3
$$
Simplifies to:
$$
x^3 + 3x^2y + 3xy^2 + y^3
$$


---
## Bézout's Identity ☘️
Bézout's Identity states that for any two integers $$\( a \) and \( b \), there exist integers \( x \) and \( y \)$$ such that:
$$
ax + by = \text{gcd}(a, b)
$$
In other words, the greatest common divisor (gcd) of $$\( a \) and \( b \) can be expressed as a linear combination of \( a \) and \( b \)$$.

Example:</br>
For $$\( a = 30 \) and \( b = 12 \), we can find \( x \) and \( y \)$$ such that:
$$
30x + 12y = \text{gcd}(30, 12) = 6
$$

---
## Chinese Remainder Theorem 🎄

Chinese Remainder Theorem (CRT) allows solving systems of simultaneous congruences when the moduli are coprime.

Given integers $$\( n_1, n_2, \ldots, n_k \)$$ that are pairwise coprime (i.e., $$\( \text{gcd}(n_i, n_j) = 1 \)$$ for $$\( i \neq j \)$$), and integers $$\( a_1, a_2, \ldots, a_k \)$$, the system :
$$
x \equiv a_1 \pmod{n_1}, \quad x \equiv a_2 \pmod{n_2}, \quad \ldots, \quad x \equiv a_k \pmod{n_k}
$$
has a unique solution for $$\( x \) modulo \( N = n_1 \times n_2 \times \cdots \times n_k \)$$.

References :</br>
1. [Any youtube vids](https://www.youtube.com/watch?v=EHDEvFuYPRQ)</br>
2. [LibreText](https://math.libretexts.org/Bookshelves/Combinatorics_and_Discrete_Mathematics/Elementary_Number_Theory_(Barrus_and_Clark)/01%3A_Chapters/1.23%3A_Chinese_Remainder_Theorem)
---

## Diophantine Equation 🦤

Diophantine equation is an equation where integer solutions are sought.

A linear Diophantine equation is of the form:
$$
ax + by = c
$$
where $$\( a \), \( b \), and \( c \)$$ are integers, and $$\( x \) and \( y \)$$ are the unknowns.

A solution exists if and only if the greatest common divisor (gcd) of $$\( a \) and \( b \) divides \( c \)$$. If $$\( \text{gcd}(a, b) = d \)$$, then a solution exists if $$\( d \) divides \( c \)$$.

Example:</br>
Solve the equation $$\( 15x + 25y = 35 \)$$.
- The gcd of 15 and 25 is 5, and since 5 divides 35, integer solutions exist.

References : </br>
1. [hendrydext (IDN)](https://hendrydext.blogspot.com/2008/09/persamaan-diophantine.html)

---
## Euler's Theorem 🦈

Euler's Theorem is a generalization of Fermat's Little Theorem for numbers that are coprime to $$\( n \)$$.


If $$\( a \) and \( n \) are coprime (i.e., \( \text{gcd}(a, n) = 1 \))$$, then:
$$
a^{\phi(n)} \equiv 1 \pmod{n}
$$
Where $$\( \phi(n) \) is Euler's totient function, which counts the number of integers less than \( n \) that are coprime to \( n \)$$.

Example:</br>
For $$\( n = 10 \), \( \phi(10) = 4 \), and for \( a = 3 \)$$:
$$
3^4 = 81 \equiv 1 \pmod{10}
$$

---
## Euclid's Theorem 🦧
Euclid's theorem states that there are infinitely many prime numbers. The proof is by contradiction. 

Assume there is a finite number of primes $$\( p_1, p_2, \dots, p_n \), then consider the number \( N = p_1 p_2 \dots p_n + 1 \). \( N \) is either prime or divisible by some prime, which cannot be any of \( p_1, p_2, \dots, p_n \)$$, leading to a contradiction.

---
## Extended Euclid's Theorem 🦄
The extended Euclidean algorithm finds the greatest common divisor (GCD) of two numbers $$\( a \) and \( b \), and also finds integers \( x \) and \( y \)$$ such that:
$$
ax + by = \gcd(a, b)
$$


---
## Fermat's Little Theorem 🐞

Fermat's Little Theorem states that if $$\( p \) is a prime number and \( a \) is an integer such that \( a \) is not divisible by \( p \), then:$$
$$
a^{p-1} \equiv 1 \pmod{p}
$$

Example:</br>
For $$\( p = 5 \) and \( a = 2 \)$$:
$$
2^{5-1} = 2^4 = 16 \equiv 1 \pmod{5}
$$

---

## Fermat's Last Theorem 🦋

Fermat's Last Theorem states that no three positive integers \( x \), \( y \), and \( z \) can satisfy the equation:
$$
x^n + y^n = z^n
$$
for any integer value of $$\( n > 2 \).$$

Example: </br>
No integer solutions exist for $$\( n = 3 \) to the equation \( x^3 + y^3 = z^3 \).$$

---

## Wilson's Theorem 🐛
Wilson's Theorem states that for a prime number $$\( p \)$$, the following congruence holds:
$$
(p-1)! \equiv -1 \pmod{p}
$$
In other words, the factorial of $$\( p-1 \) is congruent to \( -1 \) modulo \( p \)$$.

Example:</br>
For $$\( p = 5 \)$$:
$$
4! = 24 \equiv -1 \pmod{5}
$$
---