---
title: "The Intersection of Management and Technology"
date: 2022-09-03T15:35:08+01:00
draft: false
tags : [
    "business",
    "technology",
]
---

Ignore the cringe title, but I noticed a similarity in FNCE207 (Corporate Valuations) and CIS320 (Algorithms) during the first week of school. 

## FNCE207: Creating a Distinctive Advantage Through Choice

In 207, we were talking about creating a distinctive advantage through choice. The case study was about how parents are skipping proper car seats in ride-shares like Uber. 

> 🎯 The question was: should Uber invest to install car seats in cars?

> 👉🏾 To analyze this, we identified two choice point factors: (1) the percentage % > of Uber’s market that identify as parents (2) the cost of the car seat.



Then, we fixed one variable and took the other variable to the extreme.

1. Assume car seats were priced fairly and the percentage % of Uber’s market that identifies as parents is arbitrary. What if 100% were parents? Then Uber would probably want to invest to install car seats. What if 100% were teenagers? No. 
2. Similarly, assume the percentage % of Uber’s market that identify as parents is significant and the price of the car seats are arbitrary. What if they were free? Uber would lose nothing by installing car seats, so they should do it. What if the car seats costed $1,000,000 each? No, they would probably lose too much money.

What’s the answer? It depends on the blend of the two choice point factors. We would have to do more analysis: How much profit can we expect to make from parents? Is this profit greater than the cost of installing car seats? Besides these extra steps, the original process of fixing a variable, taking the other as arbitrary, and going to the extremes builds intuition on how to make decisions depending on these variables. This process reminded me of the strategy we used to analyze the file placement problem on a sequential tape in 320.

## CIS320: File Placement Problem On a Sequential Tape

This problem is a classic example of the greedy paradigm. 


>👉🏾 **Input**: $n$ files $F_1, F_2, …, F_n$ where each file $F_i$ has two > attributes: length $l_i$, an access probability $P(i)$




> 🎯 **Goal**: arrange the files in a permutation $\pi$ that minimizes the expected > access cost

I’m not going to type out the full blown proofs for this, but to analyze this, we focused on the two attributes: the length and access probability. Then, we fixed one variable, and took the other variable to the extreme. 

1. Assume all access probabilities are the same and the lengths are arbitrary. Then, we observe that the file that is placed first on the tape contributes to the access cost of every file. Therefore, we would want to sort the files in increasing order of file length, $l_i$.
2. Similarly, assume lengths are the same and the access probabilities are arbitrary. In this case, we want to sort in decreasing order of access probability (or increasing order of $\frac{1}{P(i)}$). 

What’s the answer? Arrange the files in increasing order $\frac{l_i}{P(i)}$ (the product of the answers of the modified problems above). 

## The Intersection

The finance case and greedy paradigm problem both share the same idea of fixing one dimension and taking the other dimension as arbitrary in order to build intuition on how to get to the answer. In the general case of these types of problems, it might not be immediately clear which direction to go. Solving multi-variable problems directly is confusing because different blends of the given inputs behave very differently with no apparent pattern. Fixing one variable and making the other arbitrary makes the problem more approachable (often times the answer is obvious) and the combination of both sub-problems makes solving the general case much easier. 

It’s pretty interesting how widely this strategy can be applied, from business cases to computer science theory.