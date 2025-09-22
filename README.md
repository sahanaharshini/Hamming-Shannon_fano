# Huffman-Shannon_fano
 Aim:
Consider a discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} for its output. 
Apply the Huffman and Shannon-Fano to this source. 
Show that by drawing the tree diagram, and 
Calculate the average code word length, entropy, variance, redundancy, and efficiency.

Program:
```
import numpy as np
import math 
L  = 0
hs = 0
p = []
lk = []
n = int(input("Enter the number of Samples : "))
for i in range (n): 
    pr = float(input(f"Enter the probability of sample values {i + 1}: "))  
    p.append(pr)
for j in range (n): 
    l = float(input(f"Enter the length of the sample values {j + 1}: "))  
    lk.append(l)
# Avg length of the code word
for k in range (n):
    Avg1 = p[k] * lk[k]
    L = L + Avg1
# Entropy
for k in range (n):
    e = p[k] * math.log(1 / p[k], 2)
    hs = hs + e
hs = round(hs,3)
# Efficiency
eff =  hs / L
eff = round(eff,3)
# Redundancy 
red =  round(1 - eff,3) 
# Variance
var = 0
for k in range(n):
    var1 = p[k] * (lk[k]-L)**2
    var = var + var1
var = round(var,3)
print(f"Average Codeword Length is : {L}")
print(f"Entropy is : {hs}")
print(f"Efficiency is : {eff}")
print(f"Redudancy is : {red}")
print(f"Variance is : {var}")
```
Calculation:

<img width="940" height="1434" alt="image" src="https://github.com/user-attachments/assets/60bcda2c-ede7-4270-9353-e52f50d37005" />
<img width="944" height="1460" alt="image" src="https://github.com/user-attachments/assets/d13afff0-1e54-4e15-a3d7-17a6f88bb4dc" />



Compare the manually calculated value and the observed practical value.

OUTPUT
```
  Enter the number of Samples : 7
  Enter the probability of sample values 1: 0.125
  Enter the probability of sample values 2: 0.0625
  Enter the probability of sample values 3: 0.25
  Enter the probability of sample values 4: 0.0625
  Enter the probability of sample values 5: 0.125
  Enter the probability of sample values 6: 0.125
  Enter the probability of sample values 7: 0.25
  Enter the length of the sample values 1: 3
  Enter the length of the sample values 2: 4
  Enter the length of the sample values 3: 2
  Enter the length of the sample values 4: 4
  Enter the length of the sample values 5: 3
  Enter the length of the sample values 6: 3
  Enter the length of the sample values 7: 2
  Average Codeword Length is : 2.625
  Entropy is : 2.625
  Efficiency is : 1.0
  Redudancy is : 0.0
  Variance is : 0.484

```
Results:

Consider a discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} for its output. 
Apply the Huffman and Shannon-Fano to this source. 
Show that by drawing the tree diagram, and 
Calculate the average code word length, entropy, variance, redundancy, and efficiency.

