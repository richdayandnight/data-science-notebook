# Apriori Algorithm

A -> B
IF -> THEN
Antecedent -> Consequent

Association Rule Mining

Measure Association
1. Support
    - $$ Support = \frac{freq(A,B)}{N} $$
    - Frequency of Item A or B
2. Confidence
    - $$ Confidence = \frac{freq(A,B)}{freq(A)} $$
    - How often the items A and B occur together
3. Lift
    - $$ Lift = \frac{Support(A \cup B)}{Supp(A) x Supp(B)}
- 
- If the denominator of lift is more, means the accurrance of randomness is more than the accurrance of any association
- The likelihood of buying a Burger and Ketchup together is 3.33 times more than the likelihood of just buying the ketchup.

Example:
Given set of transactions
T1: A, B, C  
T2: A, C, D  
T3: B, C, D  
T4: A, D, E  
T5: B, C, E  

N = 5 (A, B, C, D, E)

Rules
1. A => D
2. C => A
3. A = >C
4. B & C => A

| Rule    |Support  |Confidence| Lift    |
|---------|---------|---------|---------|
| A => D | 2/5  | 2/3 | 10/9 |
| C => A | 2/5  | 2/4 | 5/6 |
| A => C | 2/5  | 2/3 | 5/6 |
| B & C => A| 1/5  | 1/3 | 5/9 |


## Apriori Algorithm
- uses frequent item sets to generate association rules
- based on the concept that a subset of a frequent itemset must also be a frequent itemset

Terms:
Frequent Item Set
- an itemset whose support value is greater than a threshold value