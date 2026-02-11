## Efficient Algorithms: Searching, DP & Optimisation

This repository contains solutions to five algorithmic problems, each requiring a unique approach, from dynamic programming to binary search. Below is a brief overview of each solution.

> [!IMPORTANT]
> This is the first project homework for Algorithms Design class (2nd year, 2nd sem)
- It was done with AI guidance and peer support throughout the process
- The code was written by me, except for the **encryption problem**
- For the **encryption problem** I have looked it up on my colleagues GitHub profiles to see their implementation
- The **encryption problem** was done after submitting the implementation for the deadline, without it being part of the project at that time
- All credits to my colleagues and to AI assistance for the **encryption problem** 
- Educational purposes only

---

### Server Power Optimisation

### Approach
- **Binary search** on the possible power limit.
- Initialize `left = 0`, `right = max power supply (ci)`.
- Adjust `mid` based on computed power values.
- **Stopping condition:** `min1 == min2`, meaning we've maximised the power supply.

#### Complexity
**O(log n)** – binary search ensures efficient convergence.

---

### Coloring

#### Approach
- Utilizes **modular exponentiation** (`fastPow`) for efficiency.
- Six cases based on `H` (horizontal) and `V` (vertical) positioning.
- Uses two **coefficient arrays** to store values dynamically.
- Smartly applies **multiplication rules** based on previous character positioning.

#### Complexity
**O(n)** – single-pass computation.

---

### Compression

#### Approach
- Read two sequences and use **two indices** to traverse them simultaneously.
- Track sums with `sum1` and `sum2`, and use flags (`search`, `case1`, `case2`) to handle sub-sequence sums efficiently.
- **Two main cases:**
  1. Sum elements from the second sequence to match an element in the first.
  2. Sum elements from the first sequence to match an element in the second.
- If sequences can't be compressed properly, output `-1`.

#### Complexity
**O(max(n, m))** – as we traverse both sequences linearly.

---

### Encryption Optimisation

#### Approach
1. **Calculate letter frequency per word**.
2. **Sort words** based on:
   - Descending frequency.
   - Frequency-to-length ratio.
   - Longer words preferred for ties.
3. **Select words greedily** to maximise encryption efficiency.
4. **Repeat for each letter (`a-z`)** and track the maximum encrypted length.

#### Complexity
**O(N²)** – due to nested sorting and frequency checks.

---

### Optimal Offer (Dynamic Programming)

#### Approach
- Uses **dynamic programming** (`dp[i]`) to track the minimum price at step `i`.
- Three options at each step:
  1. Buy normally (`dp[i - 1] + prices[i]`).
  2. Use a **2-product offer** (`dp[i - 2] + discounted sum`).
  3. Use a **3-product offer** (`dp[i - 3] + best discount`).
- Stores **optimal previous results** to ensure minimum cost.

#### Complexity
**O(n)** – processes each price efficiently.

---

### Testing

#### Sample Inputs and Expected Outputs
To test the programs, create input files manually and use the Makefile rules. Here are sample test cases for each problem:

1. **Server Power (server.cpp)**
   - Input:
   - `4`
   - `6 9 7 5`
   - `2 4 1 8`
   - Expected Output:
   - `2.5`

2. **Coloring**
   - Input:
   - `2`
   - `1 H 1 V`
   - Expected Output:
   - `6`

3. **Compression**
   - Input:
   - `6`
   - `11 2 2 1 8 6`
   - `7`
   - `3 8 2 1 2 11 3`
   - Expected Output:
   - `4`

4. **Encryption**
   - Input:
   - `4`
   - `too`
   - `otter`
   - `tote`
   - `oo`
   - Expected Output:
   - `9`

5. **Offer**
   - Input:
   - `5 1`
   - `80 27 10 20 300`
   - Expected Output:
   - `413.5`

---

### Summary

| Problem        | Approach                  | Complexity |
|---------------|--------------------------|------------|
| Server        | Binary search             | O(log n) |
| Coloring      | Modular exponentiation    | O(n) |
| Compression   | Two-pointer traversal     | O(max(n, m)) |
| Encryption    | Sorting + Greedy Selection | O(N²) |
| Offer         | Dynamic programming       | O(n) |

Each solution leverages a tailored algorithmic strategy to optimise performance.

---

### Licence

This project is licensed under the MIT Licence. See the [LICENCE](./LICENSE) file for further details.
