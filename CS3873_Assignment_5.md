# CS3873 - Assignmnet 5

**Author:** Shahriar Kariman

**Due:** April 9th, 2025

## Question 1 - Address Spaces

The size of each address space is:

- MAC $\rightarrow$ 6 bytes $=$ 48 bits meaning $2^{48} \approx 2.8 \times 10^{14}$ addresses
- IPV4 $\rightarrow$ 4 bytes $=$ 32 bits
- IPV6 $\rightarrow$ 16 bytes $=$ 128 bits

## Question 2 - RSA Cryptogrophy

If $p = 17$ and $q = 11$ then:

$$
\begin{split}
  n &= p \times q = 187
  \\
  z &= (p-1) \times (q-1) = 160
\end{split}
$$

For $e = 37$:

$$
\begin{split}
  e \times d \equiv 1 \pmod{160}
  \\
  37 \times d - 160 \times k = 1
  \\
  d = \frac{1+160 \times k}{37}, \ k = 3
  \\
  d = 13
\end{split}
$$

Now to encrypt $m$:

$$
\begin{split}
  c &= m^e \bmod n
  \\
  c &= 4^{37} \bmod 187
  \\
  c &= \left[ (4^5 \bmod 187)^7 \times (4^2 \bmod 187) \right] \bmod 187 =
  \\
  &= (89^7 \times 16) \bmod 187 =
  \\
  &= \left[ (89^2 \bmod 187)^3 \times (89 \bmod 187) \times (16 \bmod 187) \right] \bmod 187 =
  \\
  &= (67^3 \times 89 \times 16) \bmod 187 =
  \\
  &= \left[ (67^2 \bmod 187) \times (67 \bmod 187) \times (89 \bmod 187) \times (16 \bmod 187) \right] \bmod 187 =
  \\
  &= ( 1 \times 67 \times 89 \times 16) \bmod 187 = ( 1072 \times 89 ) \bmod 187 =
  \\
  &= \left[ (1072 \bmod 187) \times (89 \bmod 187) \right] \bmod 187 =
  \\
  &= ( 137 \times 89 ) \bmod 187 = 95408 \bmod 187 = 38
  \\
  c = 38
\end{split}
$$

To be clear this question took an hour of my time and provided absolutly zero learning value.

## Question 3 - Error Detection & Correction

### Part A

No I can't be sure about which bits were flipped since there are 2 rows that have odd parity but no columns this means that there was a 2 bit error.

### Part B

So I can tell that there are odd parities in row 3 and column 2 which means the correct table would be as such with the corrected bit in bold:

|       | Col 1 | Col 2 | Col 3 | Col 4 |
|-------|-------|-------|-------|-------|
| Row 1 |   1   |   0   |   1   |   0   |
| Row 2 |   0   |   0   |   1   |   1   |
| Row 3 |   1   | **0** |   1   |   0   |
| Row 4 |   0   |   0   |   1   |   1   |

## Question 4 - Message Between Bob and Alice

### Part A - Message Integrity

If Alice computes a hash from the message then sends both the hash with the message then Bob can recalculate the hash and compair his result with the hash he recived from Alice he should find that they are the same if there was no error.

### Part B - Confidentiality

Yes cause Alice has Bobs public key so she can just send her encrypted message. $\rightarrow \text{cipher} = \text{Encrypt}(\text{message}, E_B)$

### Part C - Authentication

I dont see how that would be possible given that Alice does not have a public-rpivate key pair anyone could have use Bob's public key to encrypt that message.

## Question 5 -
