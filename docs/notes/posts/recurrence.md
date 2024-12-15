---
date: 2024-12-15
categories:
    - Documentation
tags:
    - Random
---

# Recurrence Relation / DP 🐬

Given a finite set $$\( S = \{s_1, s_2, \dots, s_k\} \) where each element \( s_i \) has an associated cost \( c_i \), and a total budget \( B \), determine the number of ways to select elements from \( S \) such that the total cost does not exceed \( B \)$$.

For each item $$\( s_i \)$$, the generating function is
:
$$
G_i(x) = \sum_{m=0}^{\infty} x^m \cdot c_i
$$

This represents the selection of $$\( m \) items of \( s_i \), where \( c_i \)$$ is the cost of each item. The overall generating function is then the product of the individual item generating functions
:
$$
G(x) = \prod_{i=1}^{k} G_i(x) = \prod_{i=1}^{k} \sum_{m=0}^{\infty} x^m \cdot c_i
$$

To find the number of ways to select items with a total cost $$\( B \), you would look for the coefficient of \( x^B \) in the expansion of \( G(x) \)$$.

<br>
<!-- $$
\textbf{Problem Example:}
$$ 
Problem Reference : IDN OSK Informatika 2015 <br>
Given a set of items, each with a specific cost, determine the number of ways to select a combination of items with a budget constraint. Let the items be burgers (cost 3), fish (cost 4), rice (cost 2), and the budget be 13. Model the problem using the generating function
:
$$
(x^3 + x^4 + x^2)^5
$$

<!-- where each term represents the potential cost of an item, and the exponent corresponds to the number of items selected.

$$
\textbf{Solution Approach:}
$$
Find the coefficient of $$\( x^{13} \)$$ in the expanded generating function, which corresponds to the number of ways to select items such that the total cost is exactly 13. --> 


$$
\textbf{Problem Example:}
$$ 
Problem Reference : IDN OSK Informatika 2015 <br>

There are 5 adventurers, and they are hungry. They decide to eat at TOKI Fried Kitchen, which offers the following menu with prices in thousands of rupiah:

- Nasi: 4
- Burger: 5
- Paket Lauk: 2
- Es Cendol: 1

They have a total budget of 30 thousand rupiah. The rules are:

- Each person must order either nasi (with paket lauk) or a burger.
- Anyone who orders nasi must also order paket lauk.
- Each person may order at most one es cendol.

Determine how many ways they can divide their lunch menu while staying within the budget
.
## Dynamic Programming Approach 🎁
<br>
$$
\textbf{Solution Approach 0 (DP):}
$$


```python
def find_ways(money_left, people_left, memo):
    # Base case: if no more people, check if money is non-negative
    if people_left == 0:
        return 1 if money_left >= 0 else 0
    if money_left < 0:
        return 0

    # Check memoization
    if (money_left, people_left) in memo:
        return memo[(money_left, people_left)]

    # Recursive relation
    result = find_ways(money_left - 5, people_left - 1, memo) + 2 * find_ways(money_left - 6, people_left - 1, memo) + find_ways(money_left - 7, people_left - 1, memo)
    
    # Store the result in the memo dictionary
    memo[(money_left, people_left)] = result
    return result

# Initialize memoization dictionary
memo = {}
# Call the function with initial parameters (30, 5)
print(find_ways(30, 5, memo))

```
`money_left` represents the remaining money.<br>
`people_left` represents the number of people left to assign meals to.<br>
`memo` is used for memoization to avoid recalculating the same values multiple times.
<br>

---

## Using Generating Function 🎈
<br>
$$
\textbf{Solution Approach 1:}
$$

The generating function for each person’s choices is
:
$$
(1 + x) \cdot x^6 \quad \text{for nasi (with lauk)} \quad \text{and} \quad (1 + x) \cdot x^5 \quad \text{for burger}.
$$

The total generating function for 5 people is
:
$$
\left( (1 + x) \cdot x^6 \right)^a \cdot \left( (1 + x) \cdot x^5 \right)^b
$$

where $$\( a + b = 5 \), \( a \) is the number of people choosing nasi, and \( b \)$$ is the number of people choosing burgers.

We are interested in the coefficient of $$\( x^{30} \)$$ in the expanded generating function 
.</br>

---

## My Preferred Approach 🎀
<br>
$$
\textbf{Solution Approach 2:}
$$

We model the choices of each person based on the menu options:</br>

- Nasi + Lauk (cost 6) corresponds to $$\( x^6 \)$$</br>
- Burger (cost 5) corresponds to $$\( x^5 \)$$</br>
- Nasi + Lauk + Es Cendol (cost 7) corresponds to $$\( x^7 \)$$</br>
- Burger + Es Cendol (cost 6) corresponds to $$\( x^6 \)$$</br>

Thus, the generating function for each person is
:
$$
(x^6 + x^5 + x^7 + x^6) = (x^5 + 2x^6 + x^7)
$$

Since there are 5 people, the total generating function is
:
$$
(x^5 + 2x^6 + x^7)^5
$$

Expanding this, we get the series
:
$$
x^{25} + 10x^{26} + 45x^{27} + 120x^{28} + 210x^{29} + 252x^{30} + 210x^{31} + 120x^{32} + 45x^{33} + 10x^{34} + x^{35}
$$

To determine the number of ways they can divide the menu within the budget of 30, we sum the coefficients for all terms where the exponent $$\( y \leq 30 \)$$, which are
:
$$
1 + 10 + 45 + 120 + 210 + 252 = 638
$$

Thus, the total number of ways to allocate the menu is $$638$$.

</br>
</br>