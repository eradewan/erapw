---
title: "A Complete Guide to Perfect Numbers"
date: 2021-12-28T21:36:43+01:00
draft: false
tags : [
    "math", "history",
]
---

*Note from the author:* I was bored during Winter Break 2021, so I just started reading about perfect numbers and compiled everything here. They are pretty cool because there are so many proofs related to them. The idea of studying “spoofs” (closely related numbers but not exactly perfect) is also valuable and could possibly be applied to other areas of study. Otherwise, they are effectively useless!

> One would be hard put to find a set of whole numbers with a more fascinating history and more elegant properties surrounded by greater depths of mystery—and more totally useless—than the **perfect numbers**.
> 
> 
> **Martin Gardner**, American Mathematician
> 

### What are Perfect Numbers?

---

**Perfect numbers** are numbers such that the sum of its factors (including 1 but excluding itself) is equal to itself.

Some Examples:

- Consider the number 6.
    - factors: 1, 2, 3, 6
    - 1 + 2 + 3 = 6
- Consider the number 28.
    - factors: 1, 2, 4, 7, 14, 28
    - 1 + 2 + 4 + 7 + 14 = 28

Therefore, 6 and 28 are perfect numbers.

### The Sum of Divisors Function

---

Before we can work to understand proofs involving perfect numbers, we define the following terms.

 
💡 The **sum of divisors** is the function $\sigma(n)=\sum_{d \mid n} d$ where $d \mid n$ refers to all positive divisors of $n$ including 1 and itself. For example, $\sigma(10)=\sum_{d \mid 10} d = 1 + 2 + 5 + 10 = 18$. With this definition, we can say that the number $N$ is **perfect** if $\sigma(N)= 2N$.

 

Note that this is the same as our previous definition that the sum of the factors (or the proper divisors) of $N$ is equal to $N$. This is because the sum of divisors includes the original number in the sum while the definition of perfect numbers excludes it. Although it seems confusing to have two slightly differing definitions, the sum of divisors function has special properties, two of which we will prove.

### Multiplicity of The Sum of Divisors Function

 
💡 The sum of divisors function is multiplicative: $\sigma(mn)=\sigma(m)\sigma(n)$ whenever $gcd(m,n) = 1$ (in other words, $m$ and $n$ are co-prime or relatively prime, so they share no common factors).

 

*Proof:* Let $\sigma(m) = 1 + m_1 + m_2 + ... + m_a$ and $\sigma(n) = 1 + n_1 + n_2 + ... + n_b$ where where $m_i$ and $n_j$ represent all factors other than 1.

We know that m and n are relatively prime integers, so they don't share any common factors except for 1.

Let $M = \sigma(m) - 1 = m_1 + m_2 + ... + m_a$ 

and similarly, $N = \sigma(n) - 1 = n_1 + n_2 + ... + n_b$. 

$M$ and $N$ represent the sum of all the factors of m that are not factors of n (in other words, $M$ and $N$ are sums made of up distinct numbers).

Consider $mn$. Its factors will be 1, the factors of $m$ which are $m_i$, the factors of $n$ which are $n_i$, or they will be in the form $m_in_j$ since $m_i$ divides $m$ and $n_j$ divides  $n$.  

Therefore, $\sigma(mn) = 1 + M + N + MN$ since

$MN = (m_1 + m_2 + ... + m_a)(n_1 + n_2 + ... + n_b) = \sum_{1 \leq i \leq a, 1 \leq j \leq b} m_in_j$.

$\sigma(mn) = 1 + M + N + MN = (1+M)(1+N) = (1+ \sigma(m) - 1 )(1+ \sigma(n) - 1 ) = \sigma(m)\sigma(n)$.

Therefore, we have proved the multiplicity of the sum of divisors function.

### **Sum of Divisors for Prime Powers**

 
💡 For any prime number $p$ with a positive integer exponent $a$:                                      $\sigma(p^a) = 1 + p + p^2+ ...+ p^a = \frac{p^{a+1}-1}{p-1}$.

 

*Proof:* $p^{a}$ is already in prime factorization since $p$ is prime, so all of its factors are just any combination of its prime factors. Therefore, its factors are $p^0, p^1, p^2, ..., p^{a}$. Taking the sum, we can say $\sigma(p^a) = 1 + p + p^2 +...+p^a$. Notice that $1 + p + p^2 +...+p^{a}$ is a geometric series in the form $1 + x + x^2 + ... + x^k = \sum_{i=0}^{k}x_i = \frac{x^{k+1}-1}{x-1}$ where $x = p$ and $k = a$. Therefore, $\sigma(p^a) =  1 + p + p^2 +...+p^{a} =  \frac{p^{a+1}-1}{p-1}$.

These results will be useful in understanding the proof of the Euclid-Euler Theorem.

### Euclid-Euler Theorem

---

The Euclid-Euler theorem relates perfect numbers perfect numbers to. 

 
💡 **Mersenne primes** are prime numbers that are in the form $M_n = 2^n - 1$ for some integer $n$.

 

The primes are named after 17th century monk Marin Mersenne, who worked with other notable figures like Descartes, Fermat, and Pascal. Mersenne studied these primes in 1644 and found that for $n = 2, 3, 5, 11, 13, 17, 19$ that $M_n = 2^n - 1$ is prime. He also conjectured that this was true for $n = 31, 67, 127, 257$, and it took over two centuries to confirm and test these numbers. The [search for more Mersenne primes](https://www.mersenne.org/primes/) (named *Great Internet Mersenne Prime Search (GIMPS)*)  continues and the most recent one was [found in 2018](https://www.mersenne.org/primes/press/M77232917.html).

 
💡 The **Euclid-Euler Theorem** states that an even number is perfect if and only if it has the form  $2^{p - 1} \times M_p$ , where $M_p = 2^p - 1$ is a Mersenne prime. With this theorem, the perfect number 6 is derived from $p = 2$ so that $2^{2-1} \times  M_2 = 2 \times 3 = 6$.

 

### Euclid’s Proof

**Euclid proved that if $2^p - 1$ is a Mersenne prime, then $N = 2^{p - 1} \times (2^p - 1)$ is an even perfect number.** He proved this in his book of mathematical proofs *Elements.*

Proof: The only prime divisors of  $N$ are  $2^p - 1$ (since we are given that it is a Mersenne prime) and $2$ (since $2$ divides $2^{p - 1}$). $\sigma(N) = \sigma(2^{p - 1})\sigma(2^p - 1)$ by the multiplicity of the sum of divisors function.

We now try to (1) ****find $\sigma(2^p - 1)$ and (2) find $\sigma(2^{p - 1})$.

1. Since $2^p - 1$ is prime, it's only factors are 1 and $2^p - 1$. Therefore, $\sigma(2^p - 1) = 1 + 2^p - 1 = 2^p$.
2. $2^{p-1}$ is a prime power (since 2 is prime), so we can use our result about the sum of divisors for prime powers: $\sigma(2^{p - 1}) = 1 + 2 + 2^2 +...+2^{p-1} = \frac{2^{p-1+1}-1}{2-1} = 2^p -1$.

From our results (1) and (2) conclude:

 $\sigma(N) = \sigma(2^{p - 1})\sigma(2^p - 1) = 2^p \times (2^p -1) = 2 (2^{p - 1} \times (2^p - 1)) = 2N$, so N is an even perfect number.

### Euler’s Proof

Twenty centuries years later, **Euler proved the other direction, that is, if $N = 2^{p - 1} \times (2^p - 1)$ is an even perfect number then $2^p - 1$ is a Mersenne prime.**

Proof: We are given an even perfect number $N = 2^{p - 1} \times (2^p - 1)$. Let $m = (2^p - 1)$, so  $N = 2^{p - 1}m$. We know $m$ is odd since $2^p$ is even. Therefore, $2^{p - 1}$ and $m$ are relatively prime (since $2$ doesn't divide $m$).

By the multiplicative property of the sum of divisors function:

  $\sigma(N) = \sigma(2^{p - 1}m) = \sigma(2^{p - 1})\sigma(m) = (2^p - 1)\sigma(m)$ (from the previous proof, result 2). 

Since $N$ is perfect, $\sigma(N) = 2N = 2(2^{p - 1}m) = 2^pm$. Therefore, $\sigma(N) = (2^p - 1)\sigma(m) = 2^pm$.

Let $s = \sigma(m)$.

- $(2^p - 1)s = 2^pm$.
- $m = (2^p - 1)\frac{s}{2^p}$
    - Since $2^p$ doesn't divide $2^p - 1$, it has to divide $s$ since m is an integer. Let  $q = \frac{s}{2^p}$.
- $m = (2^p - 1)q$

Now we have two cases.

- $q = 1$
    - $m = (2^p - 1)q = (2^p - 1)$ so $N = 2^{p - 1}m = 2^{p - 1} \times (2^p - 1)$, which is Euclid's form.
    - $q = \frac{s}{2^p} = 1$ implies that $s = 2^p$. Recall that $s = \sigma(m) = 2^p = (2^p -1 ) +1 = m + 1$. Since this is the sum of the divisors of m and the sum is $(m+1)$, that means that $m = 2^p - 1$ must be prime (since its only divisors are 1 and itself). We have proved the claim.
- $q > 1$
    - In this case, the factors of $m$ include (but are not limited to) $1, q, 2^n-1, m$ where $m = (2^p - 1)q$
    - $s = \sigma(m) \geq 1 + q + 2^n-1 + (2^p - 1)q = 2^n(1+q)$ (note the greater than or equal to sign accounts for the fact that these may not be the only divisors in the sum)
    - $\frac{m}{s} \leq \frac{(2^p - 1)q}{2^n(1+q)}$
        - $\frac{m}{s} \leq \frac{(2^p - 1)}{2^n}\frac{q}{q+1}$
        - since  $\frac{q}{q+1} < 1$, we know $\frac{m}{s} < \frac{(2^p - 1)}{2^n}$
        - However, we said $\sigma(N) = 2^pm = (2^p - 1)\sigma(m) = (2^p - 1)s$  which implies  $\frac{m}{s} = \frac{(2^p - 1)}{2^n}$, therefore we have a contradiction.
        - We conclude the case $q > 1$ is impossible.

I only go over Euler's original proof above, but there are 5 other proofs of the same fact that can be found [here](https://math.dartmouth.edu/~jvoight/notes/perfelem.pdf) under *Theorem 9*. This fact implies that the formula $N = 2^{p - 1} \times (2^p - 1)$ generates every even perfect number (that is, every even perfect number is of Euclid's type) and reduces the problem of finding even perfect numbers to finding Mersenne primes. It is unknown if there are a finite or infinite set of Mersenne primes, so equivalently by the above theorem, it is unknown whether the set of even perfect numbers is finite or infinite.

### Perfect Even Numbers are Triangular

---

 
💡 A **triangular number** is a number that can be arranged in an equilateral triangle, which is equivalent to  $T_n = \sum_{k=1}^{n} k$.

 

For example, 10 is triangular because $T_4 = \sum_{k=1}^{4} k = 1 + 2 + 3 + 4 = 10$ (see image below for how this sum forms a triangle).

![A visualization of triangular numbers.](https://upload.wikimedia.org/wikipedia/commons/thumb/1/1c/First_six_triangular_numbers.svg/1200px-First_six_triangular_numbers.svg.png)

     A visualization of triangular numbers.

 
💡 If $N$ is an even perfect number, then $N$ is a triangular number.

 

*Proof:* By the definition of triangular numbers, $\sum_{k=1}^{m-1} k = \frac{1}{2} \times m(m-1)$  (by the [sum of natural numbers formula](https://www.cuemath.com/sum-of-natural-numbers-formula/)). Note that the even perfect number:

  $N = 2^{p - 1} \times (2^p - 1) = (\frac{1}{2} \times 2) \times 2^{p - 1} \times (2^p - 1) = \frac{1}{2} \times 2^{p} \times (2^p - 1)$, which is equal to $\frac{1}{2} \times m(m-1)$for  $m = 2^p$. Therefore, $N$  is a triangular number.

# Unsolved Problem: Odd Perfect Number Conjecture

---

Everything discussed thus far has been about **even perfect numbers**, which begs the question:

 
💡 Do odd perfect numbers (OPNs) exist?

 

Nicomachus, a Greek mathematician, claimed that all perfect numbers must be even around 100 CE.

Descartes proposed that every even perfect number is of Euclid's form, and stated that he saw no reason why an odd perfect number could not exist in a letter he wrote to Mersenne in 1638. Descartes was one of the first to consider the existence of odd perfect numbers.

No one has been able to prove or disprove the claim, making this conjecture one of the most ancient unsolved problems in mathematics.

However, recent progress has been made on disproving the existence of an OPN.

1. In 1888, James Sylvester [proved](https://www.emis.de/journals/INTEGERS/papers/d16/d16.pdf) that no OPN could be divisible by 105.
2. In 1913, Leonard Dickson [showed](https://www.jstor.org/stable/pdf/2370405.pdf) that for each fixed natural number *k*, there are only finitely many odd perfect numbers  $N$ with at most $*k*$ distinct prime factors.
3. In 1953, Touchard [showed](https://www.jstor.org/stable/pdf/3072433.pdf?casa_token=te8ibzqzEtoAAAAA:NU93RfM3P9EqGuzzb_ic4BRoi6j-ZF8Zp91LL3-xDhJZIM_YDSmsE0sfLmVO2OLq-PSEkzt-LktTReJAtfm0l6du0Hx7O7qhf4Fv2Am6kVnHqtWmEDk) that if an odd perfect number exists it must be of the form    $12k+1$  or $36k+9$.
4. In 2003, Pace Neilson [showed](https://math.byu.edu/~pace/upper_bound_web.pdf) that the number of OPNs with *k* distinct prime factors is finite and that the size of the number must be smaller than  $2^{4^k}$.
5. **Bounds on number of prime factors:**
    1. [Carl Pomerance](https://en.wikipedia.org/wiki/Carl_Pomerance) (1974) proved that an OPN must have at least 7 distinct prime factors (proof [here](https://math.dartmouth.edu/~carlp/PDF/paper1.pdf)). He wrote this paper for his dissertation for his PhD from Harvard University.
    2. [Nielsen (2006)](https://www.ams.org/journals/mcom/2007-76-260/S0025-5718-07-01990-4/S0025-5718-07-01990-4.pdf) also showed that an OPN has at least 9 distinct prime factors.
    3. [Hare (2005)](https://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.90.1018&rep=rep1&type=pdf) has shown that any OPN has 75 or more prime factors.
    4. [Ochem and Rao (2012)](https://www.lirmm.fr/~ochem/opn/opn.pdf) subsequently showed that any odd perfect number has at least 101 not necessarily distinct prime factors.
    5. [Nielsen (2015)](https://www.ams.org/journals/mcom/2015-84-295/S0025-5718-2015-02941-X/home.html) also showed that an OPN has at least 10 distinct prime factors.
6. **Bounds on prime factors:**
    1. In 1998, the prime divisor of an OPN was bounded by 1 million by [Hagis and Cohen in 1998](https://www.ams.org/journals/mcom/1998-67-223/S0025-5718-98-00982-X/S0025-5718-98-00982-X.pdf).
    2. In 2003, Paul Jenkins improved on this by [proving](https://www.ams.org/journals/mcom/2003-72-243/S0025-5718-03-01496-0/S0025-5718-03-01496-0.pdf) that it exceeds 10 million.
    3. In 1999, the second and third largest prime divisors of an OPN were given by [Douglas Iannucci](https://www.ams.org/journals/mcom/1999-68-228/S0025-5718-99-01126-6/S0025-5718-99-01126-6.pdf) to be greater than than 10,000 and 100.
7. **Bounds on the OPN**:
    1. In 1908, Turcaninov proved that an odd perfect number is larger than $2 \times 10^6$
    2. It was improved to $10^{20}$ by Kanold in 1957,
    3. ...to $10^{36}$ by [Tukerman](https://www.ams.org/journals/mcom/1973-27-124/S0025-5718-1973-0325506-7/S0025-5718-1973-0325506-7.pdf) in 1973
    4. ...to $10^{50}$ by [Hagis](https://www.jstor.org/stable/2005530?seq=1#metadata_info_tab_contents) also in 1973
    5. Using computers, Brent, Cohen, and te Riele [showed](https://www.jstor.org/stable/2938723?seq=1#metadata_info_tab_contents) that it is greater than $10^{300}$ in 1991.
    6. [Ochem and Rao (2012)](https://www.lirmm.fr/~ochem/opn/opn.pdf) most recently proved it for $10^{1500}$ and later improved it to $10^{2000}$ 

With this many limitations, many mathematicians don't think an OPN exists.

> A prolonged meditation on the subject has satisfied me that the existence of any one such [odd perfect number]—its escape, so to say, from the complex web of conditions which hem it in on all sides—would be little short of a miracle.
> 
> 
> **James Joseph Sylvester**, English Mathematician
> 

### OPN Spoofs

---

 
💡 A **spoof** is a number that behaves like an odd perfect number but relaxes some of the rules. The idea is that studying spoofs might lead to more clues as to whether or not OPNs exist.

 

### **Descartes's Number**

Descartes was one of the first mathematicians to consider that an odd perfect number might exist. In his search for an OPN, Descartes found a spoof number in 1638. His number was $**198,585,576,189**$.

$198,585,576,189 = 3^2 × 7^2 × 11^2 × 13^2 × 22,021$

We can calculate $σ(198,585,576,189)$ using the multiplicity of the sum of divisors function and the sum of divisors for prime powers.

$= σ(3^2 × 7^2 × 11^2 × 13^2 × 22,021)$

$= (1 + 3 + 3^2)(1 + 7 + 7^2)(1 + 11 + 11^2)(1 + 13 + 13^2)(1 + 22,021^1)$

$= 397,171,152,378$

$= 2 (198,585,576,189)$

Since the sum of divisors equals twice the original number, this number behaves like an odd perfect number. However, 22,021 is not prime, so this can't be an OPN, but it's close enough to be considered a spoof.

### **Voight's Number**

361 years later, Voight found a second spoof. [Voight's spoof](https://math.dartmouth.edu/~jvoight/articles/opn-mass-rev-060211.pdf) was $**−22,017,975,903**$.

$−22,017,975,903 = 3^4 × 7^2 × 11^2 × 19^2 × (−127)^1$

$σ(−22,017,975,903)$

$= σ(3^4 × 7^2 × 11^2 × 19^2 × (−127)^1)$

$= (1 + 3 + 3^2+ 3^3+ 3^4)(1 + 7 + 7^2)(1 + 11 + 11^2)(1 + 19 + 19^2)(1 + (-127)^1)$

$= -44,035,951,806$

$= 2 (−22,017,975,903)$

This also behaves like an OPN, but $-127$  is negative, which isn't allowed.

Voight gave a seminar at BYU in December 2016, he discussed this number with Nielsen, Jenkins and other mathematicians who've made progress on the OPN problem. The BYU team started a systematic, computational search for more spoofs. Their computers would go through options for bases and exponents and check if that would result in a spoof OPN.

After running 20 parallel processors for 3 years, the team found all possible spoof numbers with factorizations of six or fewer bases — **21 spoofs** altogether, including the Descartes's and Voight's numbers — along with **2 extra spoofs** with seven bases. The spoofs had non-prime bases (like Descartes), negative numbers (like Voight), shared prime factors (like 72 and 75 written separately), or repeats (like 72 and 72 written separately).

These spoofs followed the rule that for any fixed number of bases, *k*, there is a finite number of spoofs, which is what Dickson showed is true for OPNs in 1913. They also found that if you let *k* go to infinity, the number of spoofs goes to infinity too.

**But how will spoofs help with the OPN problem?**

- spoof OPNs share all characteristics of an OPN except one
- OPNs must follow all the rules of spoofs plus more restrictions
- if we find a behavior of spoofs that doesn't apply to OPNs, we can say that OPNs don't exist
    - ex. if we find that spoofs have to be divisible by 105, then OPNs can't exist because [no OPN is divisible by 105](https://www.emis.de/journals/INTEGERS/papers/d16/d16.pdf)

However, we haven't found a feature of spoofs that disproves the existence of OPNs yet. Voight himself is not that optimistic: "I’m not sure we’re any closer to having a line of attack on the OPN problem. It is indeed a problem for the ages, perhaps it will remain so.”

> You have to think about the problem, maybe for a long while, and care about it. We are making progress. We’re chipping away at the mountain. And the hope is that if you keep chipping away, you might eventually find a diamond.
> 
> 
> **Pace Neilson**, BYU Math Professor
> 

# Extras

The above doesn't even come close to summarizing the results that have been proved about perfect numbers. Feel free to check out the proofs and papers below for even more facts about perfect numbers.

- Any even perfect number can be written as the sum of cubes. ([proof](https://math.dartmouth.edu/~jvoight/notes/perfelem.pdf))
- Perfect numbers have interesting binary representations: $6 = 110_2, 28 = 11100_2, 496 = 111110000_2$ written in binary. In general, if even perfect number  $N = 2^{p - 1} \times (2^p - 1)$ is written in base 2, then it has $2n-1$ digits where the first  $n$ are 1 and that last $n-1$ are 0. ([proof](https://math.dartmouth.edu/~jvoight/notes/perfelem.pdf))
- Every even number ends in 6 or 8. ([proof](https://math.dartmouth.edu/~jvoight/notes/perfelem.pdf))
- Terence Tao, one of the world's best mathematicians, published his first paper titled “Perfect Numbers” at the age of 8 in a journal for mathematics in Southern Australia. You can read an annotated version of the paper [here](https://fermatslibrary.com/s/perfect-numbers).

# Sources

- [Darthmouth's lecture notes on perfect numbers](https://math.dartmouth.edu/~jvoight/notes/perfelem.pdf)
- [Penguin math's proof on the sum of divisors multiplicity](https://penguinmaths.blogspot.com/2019/07/proof-sum-of-divisors-function-is.html)
- [Quanta Magazine's article on Professor Nielson's progress on spoof OPNs](https://www.quantamagazine.org/mathematicians-open-a-new-front-on-an-ancient-number-problem-20200910/)
- [Harvard's notes on the odd perfect number problem](https://people.math.harvard.edu/~knill/seminars/perfect/handout.pdf)
- [Wolfram's article on OPNs](https://mathworld.wolfram.com/OddPerfectNumber.html)
- [A math journal paper by Gimbel and Jaroma](https://www.emis.de/journals/INTEGERS/papers/d16/d16.pdf)
- [American Math Society's article on OPNs](https://blogs.ams.org/mathgradblog/2013/07/25/odd-perfect-numbers-exist/)
- [mersenne.org](https://www.mersenne.org/) (the search for Mersenne primes continues!)
