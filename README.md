# Shor Algorithm
__Shor's algorithm__ is a quantum computer algorithm for finding the _prime factors of an integer_. It was developed in 1994 by the American mathematician __Peter Shor__. On a quantum computer, to factor an integer $N$, Shor's algorithm runs in polynomial time, meaning the time taken is polynomial in $log N$, the size of the integer given as input


## What is the story?
Regardless of quantum computing and Shor algorithm let me explain whati is going on. Let me consider a simple example. We have a number like 15 and we would like to find an its prime facotrs, it means 3 and 5. We choose randomly a number like 7 and try to find _Mod_ of a function like below

$$f_{a,N}(x) = a^x \text{mod} N$$

which here $a = 7$ and $N=15$ for $x = 0,1,...,N$. After doing this for a while we will see there is a period. Look at well to the following:<par>

  * $f_{7,15}(0) = 7^0 \text{mod} 15 = 1$
  * $f_{7,15}(1) = 7^1 \text{mod} 15 = 7$
  * $f_{7,15}(2) = 7^2 \text{mod} 15 = 4$
  * $f_{7,15}(3) = 7^3 \text{mod} 15 = 13$
  * $f_{7,15}(4) = 7^4 \text{mod} 15 = 1$
  * $f_{7,15}(5) = 7^5 \text{mod} 15 = 7$
  * $f_{7,15}(6) = 7^6 \text{mod} 15 = 4$
  * $f_{7,15}(7) = 7^7 \text{mod} 15 = 13$ 

 In this case we can see there is a period for the function $f_{7,15}(x)$ and the result will be repeated after *four* iteration. Now we can use this period in order to find the prime factors of the number 15 in the following way:
 
 
 


