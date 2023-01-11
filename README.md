# Shor Algorithm
__Shor's algorithm__ is a quantum computer algorithm for finding the _prime factors of an integer_. It was developed in 1994 by the American mathematician __Peter Shor__. On a quantum computer, to factor an integer $N$, Shor's algorithm runs in polynomial time, meaning the time taken is polynomial in $log N$, the size of the integer given as input


## What is the story? Classical approach
Consider a postive integer Number like $N$. We are intrested in the factor $p$ of $N$ if it exists. 

### Classical Approach

To determine the prime factors we can use a simple approach step by step like below
1. if $N$ is a prime number declare that it is and exit.
2. if $N$ is not a prime number, then choose a random integer $a \in (1,N)$  
   * Calculate $gcd(a,N)$         
     * if $gcd(a,N) \neq 1$, then return the $gcd(a,N)$ as a prime facotr
     * if $gcd(a,N) = 1$, proceed to __step 3__.
 3. find the period $r$ in such a way that for the function $f_{a,N}(x) = a^x \text{mod} N$ 
$$f_{a,N}(r+1)= f_{a,N}(1) $$
or in general
$$f_{a,N}(r+s)= f_{a,N}(s) \quad \text{for} \qquad s>1 $$

 5. if period $r$ is odd or if $a^r \equiv -1 \text{mod} N$, then return to __step 2__ and choose another $a$.
     * Attention: $ a \equiv b \text{mod} N $ if and only if $a$ $\text{mod}$ $N$ = $b$ $\text{mod}$ $N$
       * Example: $17 \equiv 2\text{mod} 15$
 7. prime factors are 
   $$p_1 = \text{gcd}(a^{r/2}+1,N), \qquad p_2 = \text{gcd}(a^{r/2}-1,N)$$

### First Examples $N=15$ and $a=7$
As a first example, let me consider $N=15$ and $a=7$ which is a famous example in quantum computation literature. As a naive person, we can find the period just by following the numbers below:

  * $f_{7,15}(0) = 7^0 \text{mod} 15 = 1$
  * $f_{7,15}(1) = 7^1 \text{mod} 15 = 7$
  * $f_{7,15}(2) = 7^2 \text{mod} 15 = 4$
  * $f_{7,15}(3) = 7^3 \text{mod} 15 = 13$
  * $f_{7,15}(4) = 7^4 \text{mod} 15 = 1$
  * $f_{7,15}(5) = 7^5 \text{mod} 15 = 7$
  * $f_{7,15}(6) = 7^6 \text{mod} 15 = 4$
  * $f_{7,15}(7) = 7^7 \text{mod} 15 = 13$ 

 In this case we can see the period is *four* $(r=4)$. Now we can use this period (r=4) in order to find the prime factors of the number 15 in the following way:
   * $$p_1 = \text{gcd}(7^{4/2}+1,15)=\text{gcd}(50,15)=5 \qquad  p_2 = \text{gcd}(7^{4/2}-1,15)=\text{gcd}(48,15)=3$$
 
### First Examples $N=28$ and $a=5$
For second example we will have:
  * $f_{5,28}(0) = 5^0 \text{mod} 28 = 1$
  * $f_{5,28}(1) = 5^1 \text{mod} 28 = 5$
  * $f_{5,28}(2) = 5^2 \text{mod} 28 = 4$
  * $f_{5,28}(3) = 5^3 \text{mod} 28 = 20$
  * $f_{5,28}(4) = 5^4 \text{mod} 28 = 16$
  * $f_{5,28}(5) = 5^5 \text{mod} 28 = 17$
  * $f_{5,28}(6) = 5^6 \text{mod} 28 = 1$
  * $f_{5,28}(7) = 5^7 \text{mod} 28 = 5$
 
 So the peroiod $r$ is 6 and the prime factors are
   * $p_1$ = $\text{gcd}(5^{6/2}+1,21)=\text{gcd}(126,21)=5$
   * $p_2$ = $\text{gcd}(5^{6/2}-1,21)=\text{gcd}(124,21)=3$
 

