# Homework 2
Name: Yiqiao Jin  
UID: 305107551

## 2.24
Both are impossible.

#### For jump

There are totally 32 bits for a MIPS instruction. The first 6 bits of the instruction are used for opcode. The target address (consisting of the rest 26 bits) is left-shifted by 2 bits to get a 28-bit address, which is joined to the upper 4 bits of the PC. In other words, the remaining upper 4 bits do not change, and the lowest 28-bits of the PC are set to these 28 bits.

The current PC is at 0x20000000. Since the uppermost 4 bits 0010 do not change, and the lowermost 2 bits must be 00, the instruction that we can jump to must range from 0x20000000 to 0x2FFFFFFC. Since the address of 0x40000000 has upper 4 bits of 0100, we cannot jump to this new address.

#### For beq

***beq*** has a 16 bit immediate field. When the two registers are equal, it sets PC to PC+4+(immediate * 4) 

The immediate is a signed int between $-2^{15}$ and $2^{15}-1$. It is multiplied by 4 in beq, thus allows for branching to $-2^{17}$ addresses in the negative direction (from PC+4) and $2^{17}-4$ addresses in the positive direction (from PC+4).

The current PC is at 0x20000000. So the highest address that can be branched to is 0x20000000 + 0x4 + 0x0001FFFC = 0x20020000. Thus it is impossible to set the new address to 0x40000000.

## 2.26.1
The first line with 'slt' sets t2 to 1 if $0<t2$. Each iteration in the LOOP subtracts 1 from t1 and adds 2 to s2. Since t1 is initialized to 10, LOOP will be executed 10 times until t1 = 0. After that, t2 gets set to 0, and beq will exit the LOOP and branch to "DONE".

Thus s2 will be 20.

## 2.26.3
5 * N + 2 times

All 5 instructions in LOOP get executed N times before t1 is set to zero. Then the two instructions *slt* and *beq* are executed before exiting the loop.

## 2.46.1

The number of cycles executed **BEFORE**:

$500M \times 1 + 300M \times 10 + 100M \times 3 = 3800\ Million$ cycles

$ET_{before} = 3800\ Million \times CT_{before}$

The number of cycles executed **AFTER**:

$375M \times 1 + 300M \times 10 + 100M \times 3 = 3675\ Million$ cycles

$ET_{after} = 3675M \times 1.1 \times CT_{after} = 4042.5\ Million \times CT_{before}$ cycles

Thus, using the new instructions would NOT be a good design choice.