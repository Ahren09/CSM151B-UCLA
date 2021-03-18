# Homework 1
Name: Yiqiao Jin  
UID: 305107551

## 1.5
a. We know that:

CPU time (s) = Instruction Count (i) $\times$ CPI (clock/i) / Clock rate (c/s)

P1: $\frac{3 GHz}{1.5} = 2 \times 10^9$  
P2: $\frac{2.5 GHz}{1.0} = 2.5 \times 10^9$  
P3: $\frac{4 GHz}{2.2} = 1.82 \times 10^9$  

So P2 has the highest performance expressed in instructions per second

b. Number of cycles:

P1: $3 GHz \times 10 sec = 3 \times 10^{10}$  
P2: $2.5 GHz \times 10 sec = 2.5 \times 10^{10}$  
P3: $4 GHz \times 10 sec = 4 \times 10^{10}$  

Number of instructions:

P1: $2 \times 10^9 \times 10 sec = 2 \times 10^{10}$  
P2: $2.5 \times 10^9 \times 10 sec = 2.5 \times 10^{10}$  
P3: $1.82 \times 10^9 \times 10 sec = 1.82 \times 10^{10}$ 

c. The ratio of the new clock rates wrt the old one is $\frac{1.2}{0.7} = 1.714$

Multiply the clock rates by this ratio, the clock rates for P1-P3 becomes 5.14GHz, 4.29GHz, 6.86GHz

## 1.6
a. 

P1: CPI = $1 \times 0.1 + 2 \times 0.2 + 3 \times 0.5 + 3 \times 0.2 = 2.6\ clocks/i$

P2: CPI = 2 clock/i

b.
According to the CPIs,  
P1 needs $2.6 \times 10^6$ cycles;  
P2 needs $2 \times 10^6$ cycles;  

Time taken:  
P1: $2.6 \times 10^6 / (2.5GHz) = 1.04 \times 10^{-3}s$  
P2: $2   \times 10^6 / (3.0GHz) = 0.66 \times 10^{-3}s$  

So P2 is faster than P1.

## 1.7
a.

CPU time (s) = Instruction Count (i) $\times$ CPI (clock/i) / Clock rate (c/s)

OR

CPI (clock/i) = CPU time (s) $\times$ Clock rate (c/s) / Instruction Count 

Clock cycle time = 1ns means a clock rate of 10^9 clocks/s, or executing $10^9$ cycles per second.


A: CPI $= 1.1s \times 10^9 / 10^9 = 1.1$  
B: CPI $= 1.5s \times 10^9 / 1.2 \times 10^9 = 1.25$

b.

ratio: $\frac{F_B}{F_A}$ = $(1.2 \times 10^9×1.25) / (10^9 \times 1.1) = 1.37$

So 37% faster

c. 

Speedups:

A: $(10^9 \times 1.1) / (6 \times10^8×1.1) = 1.67$, or 67% speedups  
B: $(1.2×10^9 \times 1.25) / (6×10^8 \times1.1) = 2.27$, or 127% speedups

## 1.13
a. 

The reduction is $70 - 70 \times 0.8 = 14s$

The reduction time takes 14/250 = 5.6%

b.

$250 \times 0.8 = 200 = 70+85+40+ T$

$T = 5s$

Thus the time for INT must be reduced by $(55-5)/55$ = $90.9$%

c.

No, since $T_{branch} = 40s < 0.2 \times T_{total} = 50s$