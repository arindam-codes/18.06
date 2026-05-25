# MIT 18.06 Linear Algebra — Lecture 2 Practice Problems
## Elimination with Matrices, Pivots, Back Substitution, Inverse Matrices

> **The rule:** Solve everything by hand. Show every step. Show every matrix at every stage.
> Target: 1 hour total.
> ~15 min Topic 1, ~15 min Topic 2, ~20 min Topic 3, ~10 min Topic 4

---

## TOPIC 1 — Mechanics of Forward Elimination

### Problem 1.1 — Complete elimination by hand

Perform forward elimination on this system. Show A at EVERY intermediate step.

A = [[2,1,1],[4,3,3],[8,7,9]], b = [1,1,1]

**Part A:** Identify the first pivot. State the multiplier for the (2,1) position. State the multiplier for the (3,1) position. Apply both. Write the new matrix.

**Part B:** Identify the second pivot. State the multiplier for the (3,2) position. Apply it. Write the new matrix U.

**Part C:** Write the three pivots. Compute det(A) = product of pivots.

**Part D:** Carry b along through every step to get c. Write the final augmented system [U | c].

---

### Problem 1.2 — Back substitution

Using your U and c from Problem 1.1, solve Ux = c by back substitution.

Show every line:
- Solve for z from the third equation
- Substitute z into second, solve for y
- Substitute y and z into first, solve for x

**Verify:** Compute Ax using original A and your solution x. Check it equals b.

---

### Problem 1.3 — Failure cases

For each matrix below, attempt elimination. State: complete success / temporary failure / complete failure.

B1 = [[0,2,1],[3,5,1],[6,4,1]]
B2 = [[1,2,3],[2,4,7],[3,6,9]]
B3 = [[1,1,1],[1,2,2],[1,2,3]]

For B1: write the permutation matrix P that fixes the zero pivot. Then continue elimination on the swapped matrix.

---

## TOPIC 2 — Augmented Matrices and Full System Solution

### Problem 2.1 — Augmented matrix approach

A = [[1,3,1],[2,7,2],[3,11,4]], b = [2,5,8]

**Part A:** Write augmented matrix [A | b].
**Part B:** Perform elimination on full augmented matrix. Show [U | c].
**Part C:** Solve by back substitution.
**Part D:** Verify: multiply original A by x. Does it give b?

---

### Problem 2.2 — Same A, different b

Using same A from 2.1, solve with b' = [1, 2, 4].

**Part A:** Do you need to redo elimination? Why or why not?
**Part B:** What is different? What stays the same?
**Part C:** Apply same multipliers to b' to get c'. Solve by back substitution.

Key insight to write down: U and multipliers depend only on A. Only c changes when b changes.

---

## TOPIC 3 — Elementary and Permutation Matrices

### Problem 3.1 — Build elimination matrices

For A = [[2,1,1],[4,3,3],[8,7,9]]:

**Part A:** Write E21 — elimination matrix zeroing the (2,1) entry. State multiplier. Write full 3x3 matrix.
**Part B:** Compute E21*A by hand. Verify it matches Step 1 from Problem 1.1.
**Part C:** Write E31. Compute E31*(E21*A).
**Part D:** Write E32. Compute E32*(E31*(E21*A)). This is U.

---

### Problem 3.2 — Associative law in action

**Part A:** Compute M = E32 * E31 * E21 by hand.
**Part B:** Compute M*A. Verify equals U.
**Part C:** Write one sentence explaining the associative law in plain English — no symbols.
**Part D:** Show AB ≠ BA using:

A = [[1,2],[0,1]], B = [[1,0],[3,1]]

Compute AB and BA. Show they differ.

---

### Problem 3.3 — Row vs column operations

A = [[1,2,3],[4,5,6],[7,8,9]]

**Part A:** Write P that swaps rows 1 and 2. Compute PA. What changed?
**Part B:** Compute AP with the same P. What changed?
**Part C (written):** Complete: "To do a row operation, multiply on the ___ of A. To do a column operation, multiply on the ___ of A." Explain why using column vs row combination logic.

---

### Problem 3.4 — LU factorization

You know: E32 * E31 * E21 * A = U
So: A = E21⁻¹ * E31⁻¹ * E32⁻¹ * U = L * U

**Part A:** Write E21⁻¹, E31⁻¹, E32⁻¹ immediately (flip signs). Explain in one sentence why this works.
**Part B:** Compute L = E21⁻¹ * E31⁻¹ * E32⁻¹.
**Part C:** Verify LU = A by hand multiplication.
**Part D (written):** Notice L is lower triangular with 1s on diagonal and multipliers below. Why do the multipliers appear directly in L without mixing?

---

## TOPIC 4 — Inverses

### Problem 4.1 — Inverse of elimination matrices

E = [[1,0,0],[-5,1,0],[0,0,1]]

**Part A:** Write E⁻¹ immediately. No computation. One sentence why.
**Part B:** Verify E * E⁻¹ = I by hand.
**Part C:** Write F⁻¹ for F = [[1,0,0],[0,1,0],[0,-3,1]]. Verify F * F⁻¹ = I.

---

### Problem 4.2 — Order reverses under inversion

E21 has multiplier 3. E32 has multiplier 2. M = E32 * E21.

**Part A:** Write M by multiplying the two matrices.
**Part B:** Write M⁻¹ = E21⁻¹ * E32⁻¹ (order reverses). Compute it.
**Part C:** Verify M * M⁻¹ = I.
**Part D (written):** Socks-shoes analogy: "Put on socks then shoes → take off shoes first then socks." Connect this to why (E32 E21)⁻¹ = E21⁻¹ E32⁻¹ and NOT E32⁻¹ E21⁻¹.

---

## BOSS PROBLEM

A = [[a,2,1],[2,6,3],[1,4,3]], b = [1,4,2], a unknown.

**Part A:** Perform elimination symbolically. Find three pivots in terms of a.
**Part B:** For what values of a does elimination fail (temporarily or completely)?
**Part C:** For a = 2, find U and c. Write all multipliers.
**Part D:** For a = 2, write E21, E31, E32. Compute L. Verify LU = A.
**Part E:** Solve Ux = c for a = 2 by back substitution.
**Part F:** Compute det(A) from pivots. Verify using cofactor expansion. They must match.

---

## Mastery Checklist

- [ ] Identify each pivot during elimination without hesitation
- [ ] State the multiplier for each elimination step
- [ ] Carry b alongside A through augmented matrix approach
- [ ] Solve Ux = c by back substitution in correct order
- [ ] Recognize temporary failure (row swap) vs complete failure
- [ ] Write any Emn from the multiplier alone
- [ ] State associative law in plain English
- [ ] Show AB ≠ BA with concrete example
- [ ] Explain left vs right multiplication (row ops vs column ops)
- [ ] Write E⁻¹ instantly by flipping multiplier sign
- [ ] Explain (AB)⁻¹ = B⁻¹A⁻¹ using socks-shoes analogy
- [ ] Compute L from inverse elimination matrices
- [ ] Verify LU = A for complete 3x3 example
- [ ] Compute det(A) from pivots of U

---

*MIT 18.06 Linear Algebra*
*Math practice only — Lecture 2: Elimination with Matrices*
calude genrated to fully internalize the lecture material
