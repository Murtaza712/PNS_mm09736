# Probability and Statistics - Comprehensive Course Notes (PNS)
*Compiled by Muhammad Murtaza (mm09736)*

## Table of Contents
- [1. Core Fundamentals & Axioms (Weeks 1 & 2)](#1-core-fundamentals--axioms-weeks-1--2)
  - [Probabilistic Models](#probabilistic-models)
  - [The Three Axioms of Probability](#the-three-axioms-of-probability)
  - [Important Theorems & Proofs](#important-theorems--proofs)
- [2. Conditional Probability & The Multiplication Rule (Week 3)](#2-conditional-probability--the-multiplication-rule-week-3)
  - [Conditional Probability](#conditional-probability)
  - [The Multiplication (Product) Rule](#the-multiplication-product-rule)
- [3. Independence vs. Dependence (Week 4)](#3-independence-vs-dependence-week-4)
  - [Basic Independence (Two Events)](#basic-independence-two-events)
  - [Pairwise vs. Mutual Independence (Three Events)](#pairwise-vs-mutual-independence-three-events)
- [4. Bayes' Theorem & Total Probability](#4-bayes-theorem--total-probability)
  - [Deriving Bayes' Theorem](#deriving-bayes-theorem)
  - [The Law of Total Probability](#the-law-of-total-probability)
  - [Using Tree Diagrams (Dependent vs. Independent Events)](#using-tree-diagrams-dependent-vs-independent-events)
  - [Famous Examples of Bayes' Theorem](#famous-examples-of-bayes-theorem)
- [5. Counting, Permutations & Combinations (Week 5)](#5-counting-permutations--combinations-week-5)
  - [The Intuition Behind Permutations & Combinations](#the-intuition-behind-permutations--combinations)
  - [Binomial Probabilities](#binomial-probabilities)
  - [Partitions & Multinomial Coefficients](#partitions--multinomial-coefficients)
- [6. Random Variables & Expected Value (Weeks 6 & 7)](#6-random-variables--expected-value-weeks-6--7)
  - [Random Variables (RVs)](#random-variables-rvs)
  - [Probability Mass Function (PMF)](#probability-mass-function-pmf)
  - [Expected Value (Mean)](#expected-value-mean)
  - [Common Discrete Random Variables](#common-discrete-random-variables)
- [7. Continuous Random Variables](#7-continuous-random-variables)
  - [Example: The Romeo and Juliet Problem](#example-the-romeo-and-juliet-problem)
- [8. Vocabulary Glossary](#8-vocabulary-glossary)

## Index of Proofs
- [Proof 1 (De Morgan's Laws)](#proof-1)
- [Proof 2 (Probability of a Complement)](#proof-2)
- [Proof 3 (The Addition Rule)](#proof-3)
- [Proof 4 (The Union Bound)](#proof-4)

---

## 1. Core Fundamentals & Axioms (Weeks 1 & 2)

### Probabilistic Models
Every probabilistic model has an underlying *experiment* and involves:
*   **Sample Space ($\Omega$):** The set of all possible outcomes. These outcomes must be mutually exclusive and collectively exhaustive.
*   **Probability Law:** A rule that assigns a non-negative number $P(A)$ to an event $A$, representing its likelihood.

**Types of Sample Spaces:**
*   **Discrete and Finite:** e.g., rolling a die $\{1, 2, 3, 4, 5, 6\}$.
*   **Discrete and Infinite (Countably Infinite):** e.g., flipping a coin until you get a tail $\{1, 2, 3, \dots\}$.
*   **Continuous (Uncountably Infinite):** e.g., throwing a dart at a unit square.

### The Three Axioms of Probability
Everything in probability is built upon these three mathematical rules:
1.  **Nonnegativity:** $P(A) \geq 0$
2.  **Normalization:** $P(\Omega) = 1$ (The probability of *some* outcome occurring is 100%).
3.  **Additivity:** If events $A$ and $B$ are disjoint (mutually exclusive, meaning $A \cap B = \emptyset$), then $P(A \cup B) = P(A) + P(B)$.

### Important Theorems & Proofs

<a id="proof-1"></a><mark>Proof 1 (De Morgan's Laws):</mark>
**Statement 1:** $(A \cup B)^c = A^c \cap B^c$ (The complement of a union is the intersection of the complements).
*   <mark style="background-color: lightgreen;">Proof</mark> **(Subset definition):**
    To prove two sets are equal, we must show that they are subsets of each other.
    1.  Let $x \in (A \cup B)^c$. This means $x$ is not in $(A \cup B)$.
    2.  Therefore, $x$ is not in $A$ and $x$ is not in $B$.
    3.  This means $x \in A^c$ and $x \in B^c$, so $x \in (A^c \cap B^c)$. Thus, $(A \cup B)^c \subseteq (A^c \cap B^c)$.
    4.  Conversely, let $x \in (A^c \cap B^c)$. Then $x \in A^c$ and $x \in B^c$.
    5.  This means $x \notin A$ and $x \notin B$, so $x \notin (A \cup B)$. Thus $x \in (A \cup B)^c$.
    6.  Therefore, $(A^c \cap B^c) \subseteq (A \cup B)^c$. Since both are subsets of each other, $(A \cup B)^c = A^c \cap B^c$.

<a id="proof-2"></a><mark>Proof 2 (Probability of a Complement and $P(A) \leq 1$):</mark>
**Statement:** $P(A) = 1 - P(A^c)$
*   <mark style="background-color: lightgreen;">Proof:</mark>
    1.  For any event $A$, we can split the sample space $\Omega$ into two disjoint sets: $A$ and its complement $A^c$. Thus, $A \cup A^c = \Omega$.
    2.  Because $A$ and $A^c$ are disjoint, we apply the **Additivity Axiom**: $P(A \cup A^c) = P(A) + P(A^c)$.
    3.  By the **Normalization Axiom**, $P(\Omega) = 1$. Therefore, $P(A) + P(A^c) = 1$.
    4.  Rearranging our equation gives $P(A) = 1 - P(A^c)$.
    5.  *(Extension)* By the **Nonnegativity Axiom**, $P(A^c) \geq 0$. Since we are subtracting a positive number (or zero) from 1, $P(A)$ must be $\leq 1$.

<a id="proof-3"></a><mark>Proof 3 (The Addition Rule):</mark>
**Statement:** $P(A \cup B) = P(A) + P(B) - P(A \cap B)$
*   <mark style="background-color: lightgreen;">Proof</mark> **(Using disjoint sets):**
    We break the events into smaller disjoint sets so we can use the Additivity axiom.
    Let:
    *   $a = P(A \cap B^c)$ (The part of A not in B)
    *   $b = P(A \cap B)$ (The overlap)
    *   $c = P(B \cap A^c)$ (The part of B not in A)
    
    1.  $A$ is made of two disjoint pieces: $A = (A \cap B^c) \cup (A \cap B)$. So, $P(A) = a + b$.
    2.  $B$ is made of two disjoint pieces: $B = (B \cap A^c) \cup (A \cap B)$. So, $P(B) = c + b$.
    3.  The union $A \cup B$ is made of all three disjoint pieces: $P(A \cup B) = a + b + c$.
    4.  Now, let's calculate $P(A) + P(B) - P(A \cap B)$:
        $(a + b) + (c + b) - b = a + b + c$.
    5.  Because both sides equal $a + b + c$, we have proven that $P(A \cup B) = P(A) + P(B) - P(A \cap B)$.

<a id="proof-4"></a><mark>Proof 4 (The Union Bound):</mark>
**Statement:** $P(A \cup B) \leq P(A) + P(B)$
*   <mark style="background-color: lightgreen;">Proof:</mark>
    1.  From the Addition Rule proof above, we know $P(A \cup B) = P(A) + P(B) - P(A \cap B)$.
    2.  By the **Nonnegativity Axiom**, $P(A \cap B) \geq 0$.
    3.  If we remove a non-negative term from the right side of the equation, the right side becomes larger (or stays equal if the term was 0).
    4.  Therefore, $P(A \cup B) \leq P(A) + P(B)$.

---

## 2. Conditional Probability & The Multiplication Rule (Week 3)

### Conditional Probability
This is the probability of an event $A$ happening, *given* that we already know event $B$ has happened. When we know $B$ occurred, our sample space shrinks to just $B$.
*   <mark style="background-color: lightblue;">**Formula:**</mark> $P(A|B) = \frac{P(A \cap B)}{P(B)}$ (assuming $P(B) \neq 0$)

### The Multiplication (Product) Rule
By rearranging the conditional probability formula, we can find the probability of multiple events happening sequentially.
*   **For two events:** $P(A \cap B) = P(A) \cdot P(B|A)$
*   **For three events:** $P(A \cap B \cap C) = P(A) \cdot P(B|A) \cdot P(C|A \cap B)$
    *   *Algebraic Intuition:* You start with the probability of the first event $P(A)$. Then, you multiply it by the probability of the second event happening *given* the first occurred $P(B|A)$. Finally, multiply by the probability of the third event happening *given* both the first and second occurred $P(C|A \cap B)$.
*   **For $n$ events (General Multiplication Rule):** 
    <mark style="background-color: lightblue;">$$P(A_1 \cap A_2 \cap \dots \cap A_n) = P(A_1) \cdot P(A_2|A_1) \cdot P(A_3|A_1 \cap A_2) \cdots P(A_n|A_1 \cap A_2 \cap \dots \cap A_{n-1})$$</mark>
    *   *Intuition:* You just keep chaining the probabilities. Each new event is conditioned on *all* the previous events having already happened.

---

## 3. Independence vs. Dependence (Week 4)

### Basic Independence (Two Events)
Two events are **independent** if the occurrence of one doesn't change the probability of the other. 
*   **Mathematical Definition:** $P(A|B) = P(A)$. In plain English: "The probability of A happening, even if I tell you B just happened, is still just the normal probability of A."
*   **Intersection of Independent Events:** If they are independent, finding the chance of both happening is simple multiplication: $P(A \cap B) = P(A) \cdot P(B)$.
*   **Example:** Flipping a coin (Event A) and rolling a die (Event B). The coin landing on Heads doesn't physically change the die to make rolling a 6 more or less likely. They are independent.

### Pairwise vs. Mutual Independence (Three Events)
Why isn't it enough for 3 events to just be independent in pairs? Let's use a classic trick question.

Imagine flipping **two normal coins**:
*   **Event A:** The 1st coin is Heads. ($P(A) = 0.5$)
*   **Event B:** The 2nd coin is Heads. ($P(B) = 0.5$)
*   **Event C:** The two coins **match** (both Heads or both Tails). ($P(C) = 0.5$)

**1. Checking Pairwise Independence:**
*   **A and B:** The first coin doesn't affect the second coin. (Independent)
*   **A and C:** If the 1st coin is Heads, the 2nd coin still has a 50/50 chance of landing on Heads to make a match. The chance of a match is still 50%. (Independent)
*   **B and C:** Same logic. The 2nd coin being Heads doesn't change the 50/50 chance of a match. (Independent)
*   *Conclusion:* In pairs, these events are perfectly independent!

**2. Checking Mutual (Full) Independence:**
What happens if we look at all three together? Suppose both **A and B happened** (1st is Heads AND 2nd is Heads).
What is the probability of **C** (the coins match) now? It is exactly **100%**.

Suddenly, Event C is completely dependent on A and B happening together. If they were truly mutually independent, knowing A and B wouldn't give you any clues about C.

**The Math Check for Mutual Independence:**
To be fully independent, this equation must hold true: $P(A \cap B \cap C) = P(A) \cdot P(B) \cdot P(C)$
*   **Left side (Reality):** The probability of A, B, and C all happening (1st Heads, 2nd Heads, AND they match) is just the probability of getting (Heads, Heads) = $1/4$.
*   **Right side (Multiplication):** $P(A) \cdot P(B) \cdot P(C) = (1/2) \cdot (1/2) \cdot (1/2) = 1/8$.

Because $1/4 \neq 1/8$, they are **not** fully mutually independent, even though they were pairwise independent!

---

## 4. Bayes' Theorem & Total Probability

Bayes' Rule allows us to "reverse" conditional probabilities. It is used to update the probability of a hypothesis after observing new evidence.

### Deriving Bayes' Theorem
We know from the Multiplication Rule that:
1.  $P(A \cap B) = P(A|B) \cdot P(B)$
2.  $P(B \cap A) = P(B|A) \cdot P(A)$

Since $P(A \cap B) = P(B \cap A)$, we can equate the right sides:
$P(A|B) \cdot P(B) = P(B|A) \cdot P(A)$

Dividing by $P(B)$ gives us **Bayes' Theorem**:
<mark style="background-color: lightblue;">$$P(A|B) = \frac{P(B|A) \cdot P(A)}{P(B)}$$</mark>

### The Law of Total Probability
To find the denominator $P(B)$ in Bayes' Theorem, we often use the Law of Total Probability. If we partition our sample space into disjoint events (like $A$ and $A^c$), then:
<mark style="background-color: lightblue;">$$P(B) = P(B \cap A) + P(B \cap A^c)$$</mark>
<mark style="background-color: lightblue;">$$P(B) = P(B|A)P(A) + P(B|A^c)P(A^c)$$</mark>

### Using Tree Diagrams (Dependent vs. Independent Events)
Tree diagrams are the best visual tool for calculating the Law of Total Probability and solving Bayes' Theorem problems. 
*   **The Rules of the Tree:** 
    1.  Multiply the probabilities *along* the branches to find the intersection (Multiplication Rule).
    2.  Add the results of different branch paths *together* to find the total probability of an outcome (Law of Total Probability).
*   **Visualizing Independence vs. Dependence:**
    *   **Independent Events:** If events are independent, the probabilities on the 2nd layer of branches will be *exactly the same* no matter which branch you took on the 1st layer. 
    *   **Dependent Events:** If events are dependent, the probabilities on the 2nd layer of branches will *change* based on the outcome of the 1st layer. 

### Famous Examples of Bayes' Theorem
**1. Medical Testing (False Positives):**
*   **The Scenario:** A disease affects 1% of the population. A test for the disease is 99% accurate. If you test positive, what is the probability you actually have the disease?
*   **The Intuition:** Most people guess 99%. But using Bayes' rule, the real answer is around 50%! Why? Because the disease is so rare. Out of 10,000 people, only 100 are sick. But 1% of the 9,900 healthy people will get false positives (99 people). So if you get a positive test, you are just as likely to be one of the 99 healthy people with a false positive as you are to be one of the 99 sick people with a true positive.
*   **The Math:** $P(\text{Sick}|\text{Pos}) = \frac{P(\text{Pos}|\text{Sick}) \cdot P(\text{Sick})}{P(\text{Pos})}$ (Where $P(\text{Pos})$ is found using a tree diagram/Total Probability).

**2. The Fire Alarm:**
*   **The Scenario:** A fire alarm goes off. What is the probability there is actually a fire? 
*   **The Intuition:** You must weigh the evidence. Fires are very rare ($P(\text{Fire})$ is low). False alarms (due to burnt toast or pranks) are relatively common. Bayes' theorem balances the high probability of the alarm going off *if* there's a fire $P(\text{Alarm}|\text{Fire})$ against the base rate of fires occurring vs. false alarms occurring.

---

## 5. Counting, Permutations & Combinations (Week 5)

### The Intuition Behind Permutations & Combinations
Instead of just memorizing the formulas, it is incredibly helpful to understand *why* they work from the ground up, using real-world scenarios. 
*(These examples are drawn from this highly recommended [video on Permutations and Combinations](https://youtu.be/s_LfN4ItCs4?si=UZarpyPeuJbLF8zs))*

**1. The Fundamental Counting Principle (Repetitive Permutations)**
<mark style="background-color: lightgreen;">Example: Outfits and Shoes</mark>
*   Imagine you have 3 pants and 4 shirts. Because each shirt can be worn with each pair of pants, you multiply the options together: $3 \times 4 = 12$ different outfits.
*   If you add 2 pairs of shoes, you multiply again: $12 \times 2 = 24$ possible outfits. This multiplying out of possibilities is the **counting principle**.

<mark style="background-color: lightgreen;">Example: Combination Lock</mark>
*   Consider a lock with 5 slots, where each slot has 10 possible numbers (0-9).
*   Because you *can* repeat numbers (e.g., 1-1-1-1-1 is valid), you use the counting principle: $10 \times 10 \times 10 \times 10 \times 10 = 10^5 = 100,000$ possible combinations.

**2. Permutations Without Repetition (Factorials)**
<mark style="background-color: lightgreen;">Example: Drawing Cards</mark>
*   Once a card is drawn from a deck and placed elsewhere, it cannot be drawn again. Every time you make a choice, you have *one less option* than the previous time. This pattern looks like: $n \times (n-1) \times (n-2) \dots$

<mark style="background-color: lightgreen;">Example: Computer Password</mark>
*   Suppose you are making a 4-space computer password using the 26 letters of the alphabet, and you *cannot* repeat letters.
*   **Slot 1:** 26 choices
*   **Slot 2:** 25 choices
*   **Slot 3:** 24 choices
*   **Slot 4:** 23 choices
*   The total number of choices is $26 \times 25 \times 24 \times 23 = 358,800$.

**3. Deriving the Permutation Formula**
*   Writing out $26 \times 25 \times 24 \times 23$ is tedious. We could use $26!$ (26 factorial), but that multiplies all the way down to 1 ($26 \times 25 \times \dots \times 1$). We only want the first 4 numbers!
*   To get rid of the remaining numbers ($22 \times 21 \times \dots \times 1$), we simply **divide them out**.
*   <mark style="background-color: lightblue;">$$\frac{26 \times 25 \times 24 \times 23 \times 22 \dots \times 1}{22 \times 21 \dots \times 1} = \frac{26!}{22!}$$</mark>
*   Where did 22 come from? It is the total number of choices (26) minus the number of slots (4). So, $22 = 26 - 4$.
*   <mark style="background-color: lightblue;">**Formula:**</mark> $_nP_r = \frac{n!}{(n-r)!}$ (where $n$ is the total items, $r$ is the number of slots).

**4. Combinations Without Repetition**
<mark style="background-color: lightgreen;">Example: Labeled Balls</mark>
*   **Permutations vs. Combinations:** In permutations, the order matters. In combinations, order does not matter.
*   Suppose you draw 3 balls labeled 1, 2, and 3. The sequence $3, 2, 1$ is a *different permutation* than $2, 3, 1$. However, they represent the *exact same combination* of balls.
*   *How many times did we overcount?* We overcounted by the number of ways you can arrange those $r$ specific balls. $r$ balls can be arranged in $r!$ ways (e.g., 3 balls arrange in $3! = 6$ ways).
*   To get the true number of unique combinations, we take our permutations formula and **divide it by $r!$** to remove the redundant orderings.
*   <mark style="background-color: lightblue;">**Formula:**</mark> $_nC_r = \frac{n!}{r!(n-r)!}$

### Binomial Coefficients & Probabilities
*(These examples and explanations are based on this [video on Binomial Coefficients](https://youtu.be/EKN51vLKves?si=hWpKSUyxN9hBS-3q))*

**The Binomial Coefficient Formula**
The formula for the binomial coefficient $\binom{n}{r}$, read as '$n$ choose $r$' or '$n$ above $r$', is:
<mark style="background-color: lightblue;">$$\binom{n}{r} = \frac{n!}{r!(n - r)!}$$</mark>
where $n \ge r$ and both are non-negative integers.

**Step-by-step Examples:**
1. **$\binom{8}{3}$**:
   *   Formula: $\frac{8!}{3!(8-3)!} = \frac{8!}{3!5!}$
   *   Calculation: $\frac{8 \times 7 \times 6 \times 5!}{ (3 \times 2 \times 1) \times 5!} = \frac{336}{6} = 56$
2. **$\binom{4}{0}$**:
   *   Formula: $\frac{4!}{0!(4-0)!} = \frac{4!}{0!4!}$
   *   Calculation: $\frac{4!}{1 \times 4!} = 1$
   *   *Note: Any binomial coefficient with $r=0$ equals 1.*
3. **$\binom{7}{5}$**:
   *   Formula: $\frac{7!}{5!(7-5)!} = \frac{7!}{5!2!}$
   *   Calculation: $\frac{7 \times 6 \times 5!}{5! \times (2 \times 1)} = \frac{42}{2} = 21$
4. **$\binom{9}{9}$**:
   *   Formula: $\frac{9!}{9!(9-9)!} = \frac{9!}{9!0!}$
   *   Calculation: $\frac{9!}{9! \times 1} = 1$
   *   *Note: When $n = r$, the result is always 1.*
5. **$\binom{9}{8}$**:
   *   Formula: $\frac{9!}{8!(9-8)!} = \frac{9!}{8!1!}$
   *   Calculation: $\frac{9 \times 8!}{8! \times 1} = 9$
6. **$\binom{5}{4}$**:
   *   Formula: $\frac{5!}{4!(5-4)!} = \frac{5!}{4!1!}$
   *   Calculation: $\frac{5 \times 4!}{4! \times 1} = 5$
   *   *Note: When $n$ is exactly one unit above $r$ (i.e. $n - r = 1$), the result is simply $n$.*

### Applying it to Binomial Probabilities
*(These examples are based on this [video on Binomial Distribution Probabilities](https://youtu.be/3PWKQiLK41M?si=LCJOI1t98GidKfiE))*

Used when you have $n$ independent trials (like coin tosses), and you want exactly $x$ successes.
<mark style="background-color: lightblue;">$$P(x \text{ successes}) = \binom{n}{x} p^x (1-p)^{n-x}$$</mark>
*   $\binom{n}{x}$: (or $_nC_x$) The number of different ways/sequences those $x$ successes can be arranged.
*   $p^x$: The probability of $x$ successes happening ($p$ is the probability of success).
*   $q^{n-x}$ or $(1-p)^{n-x}$: The probability of the remaining failures happening ($q = 1-p$ is the probability of failure).

**Example 1: Die Roll Probability**
*   **Scenario:** A 6-sided die is rolled 12 times. What is the probability of rolling a '4' exactly 5 times?
*   **Variables:** $n = 12$ (trials), $x = 5$ (successes), $p = 1/6$ (probability of rolling a 4), $q = 5/6$ (probability of not rolling a 4).
*   <mark style="background-color: lightblue;">**Formula:**</mark> $P(5) = \binom{12}{5} (1/6)^5 (5/6)^{12-5}$
*   **Calculation:** $792 \times (1/6)^5 \times (5/6)^7 \approx 0.0284$ or $2.84\%$.

**Example 2: Multiple-Choice Test**
*   **Scenario:** A test has 20 questions with choices A, B, C, D. Probability of guessing exactly 6 correct?
*   **Variables:** $n = 20$, $x = 6$, $p = 1/4 = 0.25$, $q = 3/4 = 0.75$.
*   <mark style="background-color: lightblue;">**Formula:**</mark> $P(6) = \binom{20}{6} (0.25)^6 (0.75)^{14} \approx 16.86\%$.

**Example 3: Inequality ("Fewer Than")**
*   **Scenario:** 25% of students take algebra. Out of 30 students, what is the probability that *fewer than 5* are taking algebra?
*   **Logic:** "Fewer than 5" means calculating the exact probability for $x=0, 1, 2, 3,$ and $4$ students. *(Note: The video explicitly calculates for $x=1, 2, 3, 4$, but remember that $0$ is also fewer than 5! Always include $P(0)$ in these ranges).*
*   **Calculation:** You must find $P(0) + P(1) + P(2) + P(3) + P(4)$ by plugging each into the formula and adding them up.

**Mean and Standard Deviation of a Binomial Distribution**
If you know $n$ and $p$, you can quickly find the mean and standard deviation of the entire distribution:
*   **Mean ($\mu$):** $\mu = n \cdot p$ (e.g., $30 \times 0.25 = 7.5$)
*   **Standard Deviation ($\sigma$):** $\sigma = \sqrt{n \cdot p \cdot q}$ (e.g., $\sqrt{30 \times 0.25 \times 0.75} \approx 2.37$)

### Binomial Expansion & Pascal's Triangle
*(This section is based on this [video on Binomial Expansion and Pascal's Triangle](https://youtu.be/s19dWIHficY?si=hg_6FuOgwCO6luvn))*

**Pascal's Triangle**
Pascal's Triangle provides a quick way to find the coefficients for expanding binomials like $(a+b)^n$. Each number is the sum of the two numbers directly above it:
*   **Row 0:** 1
*   **Row 1:** 1, 1
*   **Row 2:** 1, 2, 1
*   **Row 3:** 1, 3, 3, 1
*   **Row 4:** 1, 4, 6, 4, 1
*   **Row 5:** 1, 5, 10, 10, 5, 1
*   **Row 6:** 1, 6, 15, 20, 15, 6, 1

**The Binomial Theorem (General Formula)**
*(From the [Khan Academy video](https://youtu.be/iPwrDWQ7hPc?si=GvL_eNmd--P4iXGM))*
While Pascal's triangle is great for small powers, the **Binomial Theorem** gives us the general mathematical formula to expand any binomial $(a+b)^n$ without needing to write out the whole triangle:
<mark style="background-color: lightblue;">$$(a+b)^n = \sum_{k=0}^{n} \binom{n}{k} a^{n-k} b^k$$</mark>
This formula simply says: add up all the terms from $k=0$ to $n$, where each term's coefficient is $\binom{n}{k}$ and the exponents on $a$ and $b$ always sum to $n$.

**Binomial Expansion Examples**
When expanding $(a+b)^n$, the exponent on $a$ starts at $n$ and decreases to $0$, while the exponent on $b$ starts at $0$ and increases to $n$. The coefficients can come either from the $n^{th}$ row of Pascal's triangle or by calculating $\binom{n}{k}$ for each term using the Binomial Theorem.

1.  **Expanding $(x + y)^5$ (Using the Binomial Theorem)**
    *   Here, $n=5$, $a=x$, $b=y$.
    *   We calculate the coefficients $\binom{5}{k}$ for $k=0$ through $5$:
        *   $k=0: \binom{5}{0} = 1$
        *   $k=1: \binom{5}{1} = 5$
        *   $k=2: \binom{5}{2} = 10$
        *   $k=3: \binom{5}{3} = 10$
        *   $k=4: \binom{5}{4} = 5$
        *   $k=5: \binom{5}{5} = 1$
    *   Result: $(x+y)^5 = 1x^5y^0 + 5x^4y^1 + 10x^3y^2 + 10x^2y^3 + 5x^1y^4 + 1x^0y^5$
    *   Simplified: $x^5 + 5x^4y + 10x^3y^2 + 10x^2y^3 + 5xy^4 + y^5$

2.  **Expanding $(x - 2)^3$**
    *   Uses Row 3 coefficients: 1, 3, 3, 1
    *   Expansion: $1(x)^3(-2)^0 + 3(x)^2(-2)^1 + 3(x)^1(-2)^2 + 1(x)^0(-2)^3$
    *   Result: $x^3 - 6x^2 + 12x - 8$

2.  **Expanding $(2x + 3y)^4$**
    *   Uses Row 4 coefficients: 1, 4, 6, 4, 1
    *   Expansion: $1(2x)^4(3y)^0 + 4(2x)^3(3y)^1 + 6(2x)^2(3y)^2 + 4(2x)^1(3y)^3 + 1(2x)^0(3y)^4$
    *   Result: $16x^4 + 96x^3y + 216x^2y^2 + 216xy^3 + 81y^4$

**Finding the $r^{th}$ Term Directly (Using the Binomial Theorem)**
Instead of writing out the entire expansion, you can find any specific term directly using the combinations formula:
<mark style="background-color: lightblue;">$$\text{Term} = \binom{n}{r} \times a^{(n-r)} \times b^r$$</mark>
*Note: In this specific formula for the term sequence, $r = (\text{term number} - 1)$. For example, to find the 4th term, $r = 3$.*

3.  **Finding the 4th term of $(3x - 4y)^6$**
    *   Here, $n=6$. Since we want the 4th term, $r = 4 - 1 = 3$.
    *   $a = 3x$ and $b = -4y$
    *   Formula: $\binom{6}{3} \times (3x)^{6-3} \times (-4y)^3$
    *   Calculation: $20 \times (27x^3) \times (-64y^3) = -34,560x^3y^3$

4.  **Finding the 5th term of $(3x - 4y)^6$**
    *   Here, $n=6$. Since we want the 5th term, $r = 5 - 1 = 4$.
    *   Formula: $\binom{6}{4} \times (3x)^{6-4} \times (-4y)^4$
    *   Calculation: $15 \times (9x^2) \times (256y^4) = 34,560x^2y^4$

### Partitions & Multinomial Coefficients
*(These examples and formulas are based on this [video on Multinomial Coefficients and Partitions](https://youtu.be/VGcx54CuNYc?si=snpCGIuH5PJByOTX))*

While the Binomial Theorem and binomial coefficients deal with splitting objects into *two* groups (chosen vs. not chosen), **multinomial coefficients** count the ways to split distinct objects into *any number* of groups.

**The General Multinomial Coefficient Formula:**
Suppose we have $n$ distinct objects and we want to split them into $m$ groups of sizes $k_1, k_2, \dots, k_m$. 
(Note: The group sizes must add up to the total number of objects: $\sum_{i=1}^{m} k_i = n$).
The number of ways to make such a selection is:
<mark style="background-color: lightblue;">$$\binom{n}{k_1, k_2, \dots, k_m} = \frac{n!}{k_1! \times k_2! \times \dots \times k_m!}$$</mark>

*   **Intuition:** The numerator $n!$ counts all possible ways to line up the $n$ distinct objects. The denominator divides out by the factorials of the group sizes because the order of the items *inside* any specific group does not matter.

**Example 1: Distributing Distinct Presents**
*   **Scenario:** You have 12 distinct presents and you want to give 3 to Person A, 4 to Person B, and 5 to Person C.
*   **Long Way (Combinations Product):** First choose 3 out of 12 for A: $\binom{12}{3}$. Then choose 4 out of the remaining 9 for B: $\binom{9}{4}$. The last 5 go to C: $\binom{5}{5}$. Total = $\binom{12}{3} \times \binom{9}{4} \times \binom{5}{5}$.
*   **Fast Way (Multinomial Formula):** $\frac{12!}{3! \times 4! \times 5!} = 27,720$ ways.

**Example 2: Anagrams with Identical Items ("Mississippi")**
*   **Scenario:** How many distinct rearrangements are there of the 11 letters in the word MISSISSIPPI?
*   **Logic:** There are 11 total blanks to fill. We need to choose 4 to be 'I's, 4 to be 'S's, 2 to be 'P's, and 1 to be the 'M'.
*   **Calculation:** $\frac{11!}{4! \times 4! \times 2! \times 1!} = 34,650$ distinct anagrams.

**The General Multinomial Theorem**
Just like binomial coefficients appear when expanding $(x+y)^n$, multinomial coefficients appear when expanding polynomials with more than two terms (like $(x+y+z)^n$).
<mark style="background-color: lightblue;">$$(x_1 + x_2 + \dots + x_m)^n = \sum \binom{n}{k_1, k_2, \dots, k_m} x_1^{k_1} x_2^{k_2} \dots x_m^{k_m}$$</mark>
*(The sum iterates over all possible non-negative integer values for the $k$'s that sum to $n$)*.

*   **Example Application:** Expanding $(x + y + z)^5$. What is the coefficient of the $x^2 y^2 z$ term?
*   **Calculation:** We need to choose 2 factors to contribute an $x$, 2 to contribute a $y$, and 1 to contribute a $z$. We use the formula with $n=5$, and $k_1=2, k_2=2, k_3=1$.
*   **Result:** The coefficient is $\binom{5}{2, 2, 1} = \frac{5!}{2! \times 2! \times 1!} = \frac{120}{4} = 30$.

---

## 6. Random Variables & Expected Value (Weeks 6 & 7)

### Random Variables (RVs)
A random variable is not a traditional algebra variable. Mathematically, it is a **function** that assigns a real number to every possible outcome in a sample space ($\Omega \rightarrow \mathbb{R}$). 
*   **Discrete RV:** Takes on a finite or countably infinite number of values (e.g., Number of heads in 5 coin tosses).
*   **Continuous RV:** Takes on an uncountably infinite number of values (e.g., The exact time it takes to commute).

### Probability Mass Function (PMF)
The PMF characterizes a Discrete Random Variable by detailing the probability of each specific value it can take.
<mark style="background-color: lightblue;">$$p_X(x) = P(X = x)$$</mark>
*   **Properties:** $p_X(x) \geq 0$ and $\sum p_X(x) = 1$.

### Expected Value (Mean)
The Expected Value ($E[X]$ or $\mu$) represents the "center of gravity" of the PMF. It is the weighted average of all possible values, weighted by their probabilities.
<mark style="background-color: lightblue;">$$E[X] = \sum x \cdot p_X(x)$$</mark>
*   **Linearity of Expectation:** $E[aX + b] = aE[X] + b$.
*   **Functions of RVs:** If you have a function $g(X)$, its expected value is $E[g(X)] = \sum g(x) \cdot p_X(x)$. Note: $E[g(X)]$ does NOT generally equal $g(E[X])$.

### Common Discrete Random Variables
*   **Bernoulli RV:** Models a single trial with two outcomes (Success/Failure). 
    *   $P(X=1) = p$, $P(X=0) = 1-p$.
    *   Mean $E[X] = p$.
*   **Binomial RV:** Models the number of successes in $n$ independent Bernoulli trials.
*   **Geometric RV:** Models the number of independent trials needed *until* the first success.
*   **Discrete Uniform RV:** Models a scenario where a contiguous range of integers are all equally likely.
    *   Mean $E[X] = \frac{a+b}{2}$ (the exact middle of the range).

---

## 7. Continuous Random Variables

When dealing with continuous random variables (like time, distance, etc.), the probability of a single exact point is zero. Instead, we calculate probability over a range using **Area**.

### Example: The Romeo and Juliet Problem
*   **Scenario:** Romeo and Juliet agree to meet at a specific location between a given time frame (e.g., 12:00 and 1:00). Whoever arrives first will wait for exactly 15 minutes before leaving. What is the probability that they will meet?
*   **Solution Strategy:** 
    1.  Let $x$ be Romeo's arrival time and $y$ be Juliet's arrival time.
    2.  This creates a continuous 2D sample space (a square representing all possible arrival times).
    3.  The condition for them meeting is $|x - y| \leq 15$ minutes.
    4.  Graphically, this represents the area between two diagonal lines ($y = x + 15$ and $y = x - 15$).
    5.  The probability is found by calculating the area of this specific region and dividing it by the total area of the sample space. We cannot simply multiply independent discrete probabilities here.

---

## 8. Vocabulary Glossary
Here is a master list of all the terminology introduced in this document:

*   **Sample Space ($\Omega$):** The set of all possible outcomes of an experiment.
*   **Probability Law:** A rule that assigns a non-negative number $P(A)$ to an event $A$, representing its likelihood.
*   **Disjoint (Mutually Exclusive) Events:** Events that cannot happen at the same time ($A \cap B = \emptyset$).
*   **Conditional Probability:** The probability of an event $A$ happening, *given* that we already know event $B$ has happened.
*   **Independent Events:** Events where the occurrence of one doesn't change the probability of the other ($P(A|B) = P(A)$).
*   **Mutually Independent Events:** Three or more events where any combination is independent of the others (e.g., $P(A \cap B \cap C) = P(A)P(B)P(C)$).
*   **Bayes' Theorem:** A formula used to "reverse" conditional probabilities or update the probability of a hypothesis based on new evidence.
*   **Law of Total Probability:** A rule that expresses the total probability of an outcome, which can be realized via several distinct events, by combining the probabilities of those distinct events.
*   **Continuous Random Variable:** A random variable where the data can take infinitely many values (like time or distance), meaning the probability of an exact point is zero and area is used instead.
*   **Discrete Random Variable:** A random variable whose possible values are finite or countably infinite (like counting numbers).
*   **Probability Mass Function (PMF):** A function that gives the exact probability that a discrete random variable is equal to a specific value.
*   **Expected Value (Mean):** The weighted average of all possible values of a random variable, weighted by their probabilities.
