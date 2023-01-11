# Shor Algorithm
__Shor's algorithm__ is a quantum computer algorithm for finding the _prime factors of an integer_. It was developed in 1994 by the American mathematician __Peter Shor__. On a quantum computer, to factor an integer $N$, Shor's algorithm runs in polynomial time, meaning the time taken is polynomial in $log N$, the size of the integer given as input


## What is the story?
Regardless of quantum computing and Shor algorithm let me explain whati is going on. Let me consider a simple example. We have a number like 15 and we would like to find an its prime facotrs, it means 3 and 5. We choose randomly a nnumber like 7 and try to find _Mod_ of a function like below

$$f_{a,N}(x) = a^x Mod N$$

which here $a = 7$ and $N=15$.
