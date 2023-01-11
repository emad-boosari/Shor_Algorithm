# Shor Algorithm
__Shor's algorithm__ is a quantum computer algorithm for finding the _prime factors of an integer_. It was developed in 1994 by the American mathematician __Peter Shor__. On a quantum computer, to factor an integer $N$, Shor's algorithm runs in polynomial time, meaning the time taken is polynomial in $log N$, the size of the integer given as input


## What is the story? Classical approach
Consider a postive integer Number like $N$. We are intrested in the factor $p$ of $N$ if it exists. 

### Classical Approach

To determine the prime factors we can use a simple approach step by step like below



1. if $N$ is a prime number declare that it is and exit.
2. if $N$ is not a prime number, then choose a random integer $'a'$ between $1<a<N$

* Calculate $gcd(a,N)$
     - if $gcd(a,N) \neq 1$, then return the $gcd(a,N)$ as a prime facotr
     - if $gcd(a,N) = 1$, proceed to step 3.
 3. find the period ($r$) of the following function 
 
$$f_{a,N}(x) = a^x \text{mod} N$$

 5. if period $r$ is odd or if $a^r $
 6. 5
 

Let me consider a simple example. We have a number like 15 and we would like to find an its prime facotrs, it means 3 and 5. We choose randomly a number like 7 and try to find _Mod_ of a function like below

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

 In this case we can see there is a period for the function $f_{7,15}(x)$ and the result will be repeated after *four* iteration. Now we can use this period (r=4) in order to find the prime factors of the number 15 in the following way:

 1. if $r$ is an odd number it is not good to find the prime factor and we need to change the $a$, in this case $a$ was 7.
 2.  if $r$ is an even number we can find the prime factora as follows:
   * $p_1$ = $\text{gcd}(a^{r/2}+1,N)$
   * $p_2$ = $\text{gcd}(a^{r/2}-1,N)$
          
 In our case $r=4$ and 
   * $p_1$ = $\text{gcd}(7^{4/2}+1,15)=\text{gcd}(50,15)=5$
   * $p_2$ = $\text{gcd}(7^{4/2}-1,15)=\text{gcd}(48,15)=3$
 
 
As a second example let me consider $N=21$ and $a=5$.
  * $f_{5,21}(0) = 5^0 \text{mod} 21 = 1$
  * $f_{5,21}(1) = 5^1 \text{mod} 21 = 5$
  * $f_{5,21}(2) = 5^2 \text{mod} 21 = 4$
  * $f_{5,21}(3) = 5^3 \text{mod} 21 = 20$
  * $f_{5,21}(4) = 5^4 \text{mod} 21 = 16$
  * $f_{5,21}(5) = 5^5 \text{mod} 21 = 17$
  * $f_{5,21}(6) = 5^6 \text{mod} 21 = 1$
  * $f_{5,21}(7) = 5^7 \text{mod} 21 = 5$
 
 So the peroiod $r$ is 6 and the prime factors are
   * $p_1$ = $\text{gcd}(5^{6/2}+1,21)=\text{gcd}(126,21)=5$
   * $p_2$ = $\text{gcd}(5^{6/2}-1,21)=\text{gcd}(124,21)=3$
 

