# Shor Algorithm
__Shor's algorithm__ is a quantum computer algorithm for finding the _prime factors of an integer_. It was developed in 1994 by the American mathematician __Peter Shor__. On a quantum computer, to factor an integer $N$, Shor's algorithm runs in polynomial time, meaning the time taken is polynomial in $log N$, the size of the integer given as input


## What is the story?
Regardless of quantum computing and Shor algorithm let me explain whati is going on. Let me consider a simple example. We have a number like 15 and we would like to find an its prime facotrs, it means 3 and 5. We choose randomly a number like 7 and try to find _Mod_ of a function like below

$$f_{a,N}(x) = a^x \text{mod} N$$

which here $a = 7$ and $N=15$ for $x = 0,1,...,N$. After doing this for a while we will see there is a period. Look at well to the following:<par>

  * $f_{7,15}(0) = 7^0 \text{mod} 15 = 1$
  * $f_{7,15}(1) = 7^0 \text{mod} 15 = 7$
 


