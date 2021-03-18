# Homework 6
Name: Yiqiao Jin  
UID: 305107551

## Without Unrolling
Note that we are only able to use the values of \$t0 and \$t1 two iterations after the lw instructions execute.

| Cycle | 1st Issue(Branch/ALU)     | 2nd Issue(lw/sw)  |
|-------|---------------------------|-------------------|
| 1     |                           | lw \$t0, 0(\$s0)  |
| 2     |                           |                   |
| 3     | addi  \$s0,  \$s0, 4      | lw  \$t1, 0($t0)  |
| 4     | bne  \$s0,  \$s2, Loop    |                   |
| 5     | add  \$t1,  \$s1, \$t1   |                   |
| 6     |                           | sw  \$t1, 0($t0)  |

Number of cycles = (cycles per iter * number of iters) + cycles for last instruction = 6 * 200 + 4 = 1204

## With Unrolling
Note that if we make 2 copies of the loop body, we increment the program counter by 8 in each iteration. 

| Cycle | 1st Issue(Branch/ALU)      | 2nd Issue(lw/sw)  |
|-------|----------------------------|-------------------|
| 1     |                            | lw \$t0, 0(\$s0)  |
| 2     |                            | lw  \$t2, 4($s0)  |
| 3     |                            | lw  \$t1, 0($t0)  |
| 4     | addi \$s0, \$s0, 8         | lw \$t3, 0($t2)   |
| 5     | add  \$t1, \$s1, \$t1      |                   |
| 6     | bne  \$s0, \$s2, Loop      | sw  \$t1, 0($t0)  |
| 7     | add  \$t3, \$s1, \$t3      |                   |
| 8     |                            | sw  \$t3, 0($t2)  |

Number of cycles = (cycles per iter * number of iters) + cycles for last instruction = 8 * 100 + 4 = 804