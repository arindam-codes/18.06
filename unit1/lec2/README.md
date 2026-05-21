# MIT 18.06 Linear Algebra — Lecture 2 Math Practice
## Elimination with Matrices, Elimination Matrices, Permutations, Inverses

> **The rule:** Solve everything by hand. No calculator. No Python.
> Show every step. Every multiplier. Every matrix at every stage.
> If you cannot show the step — you do not understand it yet.

---

## LEVEL 1 — Forward Elimination: Build the Instinct

### Problem 1.1
Perform complete elimination on this system. Show A at every step.

$$A = \begin{bmatrix} 2 & 4 & -2 \\ 4 & 9 & -3 \\ -2 & -3 & 7 \end{bmatrix}, \quad b = \begin{bmatrix} 2 \\ 8 \\ 10 \end{bmatrix}$$

- State each pivot as you find it.
- State each multiplier before you use it.
- Write the full matrix after each elimination step.
- Write U and c at the end.
- Solve Ux = c by back substitution. Show every line.

---

### Problem 1.2
Perform elimination on this system:

$$A = \begin{bmatrix} 1 & 3 & 2 \\ 2 & 7 & 5 \\ 3 & 11 & 9 \end{bmatrix}, \quad b = \begin{bmatrix} 1 \\ 3 \\ 5 \end{bmatrix}$$

- After finding U, state the three pivots.
- Compute det(A) = product of pivots.
- Solve by back substitution.
- Check your answer by substituting x back into the original equations.

---

### Problem 1.3 — Zero pivot: temporary failure
$$A = \begin{bmatrix} 0 & 2 & 1 \\ 3 & 8 & 1 \\ 6 & 4 & 1 \end{bmatrix}$$

- Attempt elimination. What goes wrong immediately?
- Write the permutation matrix P that fixes this.
- Compute PA by hand.
- Now perform elimination on PA normally.
- State the pivots of PA.

---

### Problem 1.4 — Zero pivot: complete failure
$$A = \begin{bmatrix} 1 & 2 & 3 \\ 2 & 4 & 6 \\ 0 & 1 & 1 \end{bmatrix}$$

- Attempt elimination step by step.
- At what point does it fail completely?
- Why can there be no row swap to fix it?
- What does this tell you about the columns of A?

---

### Problem 1.5 — Identify without computing
For each matrix below, decide WITHOUT doing full elimination:
- Does elimination succeed, fail temporarily, or fail completely?
- Give a one-sentence reason.

$$B_1 = \begin{bmatrix} 5 & 0 & 0 \\ 0 & 3 & 0 \\ 0 & 0 & 7 \end{bmatrix}$$

$$B_2 = \begin{bmatrix} 1 & 2 \\ 2 & 4 \end{bmatrix}$$

$$B_3 = \begin{bmatrix} 0 & 0 & 1 \\ 0 & 2 & 3 \\ 4 & 5 & 6 \end{bmatrix}$$

$$B_4 = \begin{bmatrix} 1 & 1 & 1 \\ 1 & 2 & 2 \\ 1 & 2 & 3 \end{bmatrix}$$

---

## LEVEL 2 — Elimination Matrices: Think in Matrix Language

### Problem 2.1
Given:
$$A = \begin{bmatrix} 1 & 2 & 1 \\ 3 & 8 & 1 \\ 0 & 4 & 1 \end{bmatrix}$$

**Part A:** Write the elimination matrix E₂₁ that eliminates position (2,1).
Show the multiplier. Write the full 3×3 matrix.

**Part B:** Compute E₂₁A by hand. Show the full multiplication.

**Part C:** From E₂₁A, write E₃₂ that eliminates position (3,2).
Show the multiplier. Write the full 3×3 matrix.

**Part D:** Compute E₃₂(E₂₁A) by hand. This is U.

**Part E:** Now compute the product E₃₂E₂₁ first, then (E₃₂E₂₁)A.
Verify you get the same U as Part D.
This verifies the associative law: E₃₂(E₂₁A) = (E₃₂E₂₁)A.

---

### Problem 2.2 — Non-commutativity
Let:
$$A = \begin{bmatrix} 1 & 2 \\ 3 & 4 \end{bmatrix}, \quad B = \begin{bmatrix} 0 & 1 \\ 1 & 0 \end{bmatrix}$$

**Part A:** Compute AB by hand.

**Part B:** Compute BA by hand.

**Part C:** Are they equal? Write one sentence explaining why AB ≠ BA in general.

**Part D:** B is a permutation matrix. What does it do when multiplied on the LEFT of A (as BA)? What does it do on the RIGHT (as AB)?
Answer in words: "BA swaps _____ of A. AB swaps _____ of A."

---

### Problem 2.3 — Order matters in elimination
Using the E₂₁ and E₃₂ from Problem 2.1:

**Part A:** Compute E₂₁E₃₂ (apply E₃₂ first, then E₂₁).

**Part B:** Compute E₃₂E₂₁ (apply E₂₁ first, then E₃₂).

**Part C:** Apply E₂₁E₃₂ to A. Apply E₃₂E₂₁ to A.
Do both give upper triangular results? Which one is correct?

**Part D (write in your own words):**
Why does the order of elimination matrices matter?
What goes wrong if you apply E₂₁ after E₃₂ instead of before?

---

## LEVEL 3 — Permutation Matrices

### Problem 3.1
Write out explicitly the following permutation matrices (3×3):

**P₁₂** — swaps rows 1 and 2
**P₁₃** — swaps rows 1 and 3
**P₂₃** — swaps rows 2 and 3

For each:
- Write the matrix.
- Compute P² by hand. What do you get? Why?
- Compute det(P). (Hint: think about what row swaps do to the determinant.)

---

### Problem 3.2
Given:
$$A = \begin{bmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \\ 7 & 8 & 9 \end{bmatrix}$$

**Part A:** Compute P₁₂A by hand (where P₁₂ swaps rows 1 and 2).
What changed in A?

**Part B:** Compute AP₁₂ by hand.
What changed in A?

**Part C:** In one sentence each:
- Multiplying on the LEFT by a permutation matrix does what?
- Multiplying on the RIGHT by a permutation matrix does what?

---

### Problem 3.3 — Deeper thinking
Can you write any permutation of 3 rows as a product of two "swap" matrices?

Try to write P₁₃ (swap rows 1 and 3) as a product of two matrices that each only swap adjacent rows (P₁₂ and P₂₃).

Hint: think about how to move row 1 to position 3 using only adjacent swaps.
How many adjacent swaps are needed? What does this tell you about det(P₁₃)?

---

## LEVEL 4 — Inverses

### Problem 4.1 — Inverse of elimination matrices
Given:
$$E_{21} = \begin{bmatrix} 1 & 0 & 0 \\ -3 & 1 & 0 \\ 0 & 0 & 1 \end{bmatrix}$$

**Part A:** Write E₂₁⁻¹ immediately. No calculation. Explain why in one sentence.

**Part B:** Verify E₂₁ × E₂₁⁻¹ = I by hand multiplication.

**Part C:** Write E₃₂⁻¹ if:
$$E_{32} = \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & -2 & 1 \end{bmatrix}$$

Verify E₃₂ × E₃₂⁻¹ = I by hand.

---

### Problem 4.2 — Order reverses under inversion
Let M = E₃₂E₂₁ where E₂₁ has multiplier 3 and E₃₂ has multiplier 2.

**Part A:** Write M explicitly by computing E₃₂E₂₁.

**Part B:** Write M⁻¹ = E₂₁⁻¹E₃₂⁻¹ (the order reverses — why?).

**Part C:** Compute MM⁻¹ by hand. Verify you get I.

**Part D (write the explanation):**
The socks-shoes analogy:
"If I put on socks first, then shoes, to undo this I must..."
Write the full analogy connecting it to why (AB)⁻¹ = B⁻¹A⁻¹.

---

### Problem 4.3 — LU Factorization by hand
For the matrix from Problem 2.1:
$$A = \begin{bmatrix} 1 & 2 & 1 \\ 3 & 8 & 1 \\ 0 & 4 & 1 \end{bmatrix}$$

**Part A:** From your elimination work in Problem 2.1, you already have:
- Multipliers: l₂₁, l₃₂
- Upper triangular matrix U

Write L by placing the multipliers directly in their positions below the diagonal, with 1s on the diagonal.

**Part B:** Compute LU by hand. Verify LU = A.

**Part C:** State the beautiful fact:
"The matrix L is lower triangular and its off-diagonal entries are exactly ___."

---

## LEVEL 5 — Determinants from Pivots

### Problem 5.1
Find the determinant of each matrix using elimination (product of pivots):

$$C_1 = \begin{bmatrix} 3 & 1 \\ 6 & 4 \end{bmatrix}$$

$$C_2 = \begin{bmatrix} 1 & 2 & 3 \\ 2 & 5 & 7 \\ 3 & 7 & 11 \end{bmatrix}$$

$$C_3 = \begin{bmatrix} 2 & 1 & 0 \\ 1 & 3 & 1 \\ 0 & 1 & 2 \end{bmatrix}$$

For each: show elimination steps, state each pivot, compute det = product of pivots.

---

### Problem 5.2 — Effect of row swap on determinant
Take C₁ from above. Swap its two rows. Call the result C₁'.

**Part A:** Compute det(C₁') using the pivot formula.

**Part B:** How does det(C₁') compare to det(C₁)?

**Part C:** State the rule: "Each row swap multiplies the determinant by ___."

**Part D:** If a matrix needs 2 row swaps during elimination, and the product of pivots of U is 12, what is det(A)?

---

### Problem 5.3 — Scale effect on determinant
Take the 3×3 matrix C₂. Scale every entry by 2 — call it D = 2C₂.

**Part A:** What are the pivots of D? (Think — don't compute fully.)

**Part B:** What is det(D)?

**Part C:** Complete the general rule: "If A is n×n and D = kA, then det(D) = ___."

**Part D:** Prove this from the pivot formula in 3-4 lines of reasoning.

---

## LEVEL 6 — Conceptual Questions: No Computation

These test whether you understand the ideas, not just the mechanics.
Answer each in 2-4 sentences.

**Q1:** If you change only the vector b (keeping A the same), do L and U change? Why?

**Q2:** Two rows of A are identical. What happens during elimination? What is det(A)?

**Q3:** An elimination matrix Eₘₙ always has det = 1. Why? (Think about what elimination does geometrically — it shears, it does not scale volume.)

**Q4:** If A is invertible and you know L and U, how would you solve Ax = b?
Describe the two-step process in words.

**Q5:** The matrix E₂₁ subtracts 3 times row 1 from row 2.
E₂₁⁻¹ adds 3 times row 1 to row 2.
Why is this inverse "free" — why do you not need to do any calculation to find it?

**Q6:** You are told that after elimination, the third pivot is 0.
What does this tell you about:
- The determinant of A?
- Whether Ax = b has a solution for every b?
- The null space of A?

---

## BOSS PROBLEM — The Synthesis

This is the hardest problem. It uses every concept from the lecture.

Given this matrix:
$$A = \begin{bmatrix} a & 2 & 1 \\ 2a & 6 & 3 \\ a & 4 & 3 \end{bmatrix}$$

where a is an unknown parameter.

**Part A:**
Perform elimination on A (treating a as a symbol).
What are the three pivots in terms of a?

**Part B:**
For what value(s) of a does elimination fail?
- Fail temporarily (zero pivot but fixable)?
- Fail completely (matrix not invertible)?

**Part C:**
For what value(s) of a is det(A) = 0?
Verify this matches your answer from Part B.

**Part D:**
For a = 1, complete the elimination and write U.
Write L with the multipliers.
Verify LU = A for a = 1.

**Part E:**
For a = 1, solve the system Ax = b where b = [1, 4, 2]ᵀ.
Show back substitution completely.

**Part F (written):**
The matrix A above has a special structure — notice that row 2 = 2 × row 1... only when a has a certain value. For that value of a:
- What is the relationship between the columns?
- What does this mean geometrically (the columns do not span ___)?
- Why must the determinant be 0?

---

## Mastery Checklist

You have mastered this lecture when you can:

- [ ] Perform elimination on any 3×3 system by hand with zero errors
- [ ] State each pivot and multiplier without hesitation
- [ ] Handle zero pivots — recognize temporary vs complete failure
- [ ] Write any elimination matrix Eₘₙ from the multiplier alone
- [ ] Verify associativity by computing both (E₃₂E₂₁)A and E₃₂(E₂₁A)
- [ ] Show AB ≠ BA with a concrete 2×2 example
- [ ] Distinguish: PA swaps rows, AP swaps columns
- [ ] Write E⁻¹ instantly by flipping the sign of the multiplier
- [ ] Explain the socks-shoes analogy for why (AB)⁻¹ = B⁻¹A⁻¹
- [ ] Extract L from multipliers and verify LU = A
- [ ] Compute det(A) from pivots and row swaps
- [ ] Explain what det = 0 means for solvability
- [ ] Answer all Level 6 conceptual questions without notes
- [ ] Solve the Boss Problem completely

---

```
    def analyze_system(A, b):
        """
        Given a 3x3 matrix A and vector b, this function:
        
        1. Builds E21, E31, E32 elimination matrices explicitly
        2. Applies them step by step to get U
        3. Stores multipliers into L
        4. Verifies A = LU
        5. Handles zero pivots with a permutation matrix P
        6. Computes det(A) from pivots and number of swaps
        7. Solves Ux = c by back substitution
        8. Verifies Ax = b
        9. Computes E21_inverse by flipping sign
        10. Verifies E21 * E21_inv = I
        
        Prints every step with mathematical explanation.
        Returns x (the solution).
        """
        pass
```
# Test it on these three systems:

# System 1: clean elimination, no swaps needed
A1 = [[1, 2, 1],
      [3, 8, 1],
      [0, 4, 1]]
b1 = [2, 12, 2]

# System 2: zero pivot needs row swap
A2 = [[0, 2, 1],
      [3, 8, 1],
      [6, 4, 1]]
b2 = [1, 5, 7]

# System 3: singular matrix — should detect and report
A3 = [[1, 2, 3],
      [2, 4, 6],
      [0, 1, 1]]
b3 = [1, 2, 1]

*MIT 18.06 Linear Algebra — Self-study mastery track*
*Math practice only — no computation*
*Lecture 2: Elimination with Matrices*