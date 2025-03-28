# Exp:8 Hamming-Shannon_fano
# Name: Keerthana S
# Reg no.: 212223060122
# Consider a discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} for its output. 
# Apply the Huffman and Shannon-Fano to this source. Show that draw the tree diagram, the average code word length, Entropy, Variance, Redundancy, Efficiency.

### AIM:

To compute the Average Codeword Length, Entropy, Efficiency, Redundancy, and Variance for a discrete memoryless source using Huffman and Shannon-Fano coding based on the given probabilities and codeword lengths.

### TOOLS REQUIRED:

python IDE with Numpy and Scipy.

### PROGRAM:

```python
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
for k in range (n):
    Avg1 = p[k] * lk[k]
    L = L + Avg1
for k in range (n):
    e = p[k] * math.log(1 / p[k], 2)
    hs = hs + e
hs = round(hs,3)
eff = hs / L
eff = round(eff,3)
red =  round(1 - eff,3) 
var = 0
for k in range(n):
    var1 = p[k] * (lk[k]-L)**2
    var = var + var1
var = round(var,3)
print()
print(f"Average Codeword Length is : {L}")
print(f"Entropy is : {hs}")
print(f"Efficiency is : {eff*100} %")
print(f"Redudancy is : {red}")
print(f"Variance is : {var}")
```

### CALCULATION:

![image](https://github.com/user-attachments/assets/5ab58f65-a0b7-49b3-864a-f900cddd2c03)

![WhatsApp Image 2025-03-28 at 15 54 37_f6a3c68c](https://github.com/user-attachments/assets/3608257e-63cc-4dc6-86ec-5ce008522e5c)

![WhatsApp Image 2025-03-28 at 15 57 57_31610384](https://github.com/user-attachments/assets/a8731b22-9084-491e-b168-6549766d8c69)

![WhatsApp Image 2025-03-28 at 15 53 06_eb7e7e1d](https://github.com/user-attachments/assets/57d26373-f63f-41b8-818d-8d94b19dbb3a)

![WhatsApp Image 2025-03-28 at 15 57 57_31610384](https://github.com/user-attachments/assets/a8731b22-9084-491e-b168-6549766d8c69)


### RESULT:

For the given probabilities 0.125,0.0625,0.25,0.0625,0.125,0.125,0.25

Average Codeword Length is : 2.625 Entropy is : 2.625 Efficiency is : 100.0 % Redudancy is : 0.0 Variance is : 0.484



