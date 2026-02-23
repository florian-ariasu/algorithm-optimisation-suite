# Algorithm Optimisation Suite

A collection of five algorithmic solutions, each applying a distinct strategy — binary search, dynamic programming, greedy optimisation, modular exponentiation, and two-pointer traversal — to efficiently solve computational problems.

---

## Problems & Approaches

---

### Server Power Optimisation

**Approach**
- **Binary search** on the possible power limit.
- Initialize `left = 0`, `right = max power supply (ci)`.
- Adjust `mid` based on computed power values.
- **Stopping condition:** `min1 == min2`, meaning we've maximised the power supply.

**Complexity:** `O(log n)` — binary search ensures efficient convergence.

---

### Coloring

**Approach**
- Utilizes **modular exponentiation** (`fastPow`) for efficiency.
- Six cases based on `H` (horizontal) and `V` (vertical) positioning.
- Uses two **coefficient arrays** to store values dynamically.
- Applies **multiplication rules** based on previous character positioning.

**Complexity:** `O(n)` — single-pass computation.

---

### Compression

**Approach**
- Read two sequences and use **two indices** to traverse them simultaneously.
- Track sums with `sum1` and `sum2`, and use flags (`search`, `case1`, `case2`) to handle sub-sequence sums efficiently.
- **Two main cases:**
  1. Sum elements from the second sequence to match an element in the first.
  2. Sum elements from the first sequence to match an element in the second.
- If sequences can't be compressed properly, output `-1`.

**Complexity:** `O(max(n, m))` — both sequences traversed linearly.

---

### Encryption Optimisation

**Approach**
1. **Calculate letter frequency per word**.
2. **Sort words** based on descending frequency, frequency-to-length ratio, and word length for ties.
3. **Select words greedily** to maximise encryption efficiency.
4. **Repeat for each letter (`a-z`)** and track the maximum encrypted length.

**Complexity:** `O(N²)` — due to nested sorting and frequency checks.

---

### Optimal Offer (Dynamic Programming)

**Approach**
- Uses **dynamic programming** (`dp[i]`) to track the minimum price at step `i`.
- Three options at each step:
  1. Buy normally (`dp[i - 1] + prices[i]`).
  2. Use a **2-product offer** (`dp[i - 2] + discounted sum`).
  3. Use a **3-product offer** (`dp[i - 3] + best discount`).
- Stores **optimal previous results** to ensure minimum cost.

**Complexity:** `O(n)` — processes each price efficiently.

---

## Summary

| Problem    | Approach                   | Complexity      |
|------------|----------------------------|-----------------|
| Server     | Binary search              | O(log n)        |
| Coloring   | Modular exponentiation     | O(n)            |
| Compression| Two-pointer traversal      | O(max(n, m))    |
| Encryption | Sorting + Greedy selection | O(N²)           |
| Offer      | Dynamic programming        | O(n)            |

---

## Testing

To test the programs, create input files manually and use the Makefile rules.

**Server Power (`server.cpp`)**
```
Input:  4 / 6 9 7 5 / 2 4 1 8
Output: 2.5
```

**Coloring**
```
Input:  2 / 1 H 1 V
Output: 6
```

**Compression**
```
Input:  6 / 11 2 2 1 8 6 / 7 / 3 8 2 1 2 11 3
Output: 4
```

**Encryption**
```
Input:  4 / too / otter / tote / oo
Output: 9
```

**Offer**
```
Input:  5 1 / 80 27 10 20 300
Output: 413.5
```

---

## Development Notes

This is a 2nd-year Algorithm Design course assignment, developed with AI guidance throughout.

---

## Licence

This project is licensed under the MIT Licence. See the [LICENSE](./LICENSE) file for details.
