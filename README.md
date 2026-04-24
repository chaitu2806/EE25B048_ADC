## 2-Bit ADC

I made a 2-bit ADC for a sine function with reference voltage as **2.5V** and amplitude as **2.5V**.

The voltage changes from **0V to 5V**.

Using a 2-bit ADC, I represented 4 voltage levels:
- 0V  
- $\frac{5}{3}$ V  
- $\frac{10}{3}$ V  
- 5V  

For this, I used **3 OP07 comparators** for comparing voltage levels and getting outputs.

### Comparator Thresholds
- 1.25V → a  
- 2.5V → b  
- 3.75V → c  

---

## 2-Bit Logic

| $I_1$ | $I_0$ | Condition | Voltage Range |
|------|------|-----------|--------------|
| 0 | 0 | $a' b' c'$ | $0 \le V < 1.25$ |
| 0 | 1 | $a' b c'$ | $1.25 \le V < 2.5$ |
| 1 | 0 | $a b c'$ | $2.5 \le V < 3.75$ |
| 1 | 1 | $a b c$ | $3.75 \le V \le 5$ |

---

## Output Equations

$$
I_0 = a(b'c' + bc)
$$

$$
I_1 = ab
$$

---
Then I represented the layers using the following equation:

$$
V_{out} = \frac{V(I_0)}{3} + \frac{2 \cdot V(I_1)}{3}
$$

The levels are:
- 0V  
- $\frac{5}{3}$ V  
- $\frac{10}{3}$ V  
- 5V  

I represented this without an **inverted logic**.
