# MIT 18.06 Linear Algebra — Lecture 1 Practice Problems
## Vectors, Linear Combinations, Matrices, Subspaces, Invertibility

> **The rule:** Solve everything by hand. Show every step.
> Target: 1 hour total.
> ~20 min Topic 1 (vectors + combinations), ~20 min Topic 2 (matrices), ~20 min Topic 3 (subspaces)

---

## TOPIC 1 — Vectors and Linear Combinations

### Problem 1.1 — Warm up: compute combinations

Given:
$$u = \begin{bmatrix} 1 \\ -1 \\ 0 \end{bmatrix}, \quad v = \begin{bmatrix} 0 \\ 1 \\ -1 \end{bmatrix}, \quad w = \begin{bmatrix} 0 \\ 0 \\ 1 \end{bmatrix}$$

Compute each linear combination by hand:

**Part A:** 2u + 3v + w

**Part B:** u - v + 2w

**Part C:** 0u + 0v + 0w (what do you always get? why?)

**Part D:** Can you find scalars x₁, x₂, x₃ such that x₁u + x₂v + x₃w = [3, 1, 2]ᵀ?
Try to find them by setting up the three equations and solving.

---

### Problem 1.2 — Geometric thinking

Answer each question in one sentence. No computation needed.

**Part A:** If you take ALL multiples of a single nonzero vector u, what geometric shape do you get?

**Part B:** If you take ALL combinations of two vectors u and v (where neither is a multiple of the other), what geometric shape do you get?

**Part C:** If you take ALL combinations of three vectors u, v, w in R³ (where none lies in the plane of the other two), what do you get?

**Part D:** What is the key difference between case B and case C above?

---

### Problem 1.3 — When do combinations fill the space?

For each set of vectors, decide: do their combinations fill all of R³, or only a smaller space?
Give a one-sentence reason for each.

**Set 1:**
$$\begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix}, \begin{bmatrix} 0 \\ 1 \\ 0 \end{bmatrix}, \begin{bmatrix} 0 \\ 0 \\ 1 \end{bmatrix}$$

**Set 2:**
$$\begin{bmatrix} 1 \\ 2 \\ 3 \end{bmatrix}, \begin{bmatrix} 2 \\ 4 \\ 6 \end{bmatrix}, \begin{bmatrix} 0 \\ 1 \\ 0 \end{bmatrix}$$

**Set 3:**
$$\begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix}, \begin{bmatrix} 1 \\ 1 \\ 0 \end{bmatrix}, \begin{bmatrix} 1 \\ 1 \\ 1 \end{bmatrix}$$

**Set 4:**
$$\begin{bmatrix} 1 \\ -1 \\ 0 \end{bmatrix}, \begin{bmatrix} 0 \\ 1 \\ -1 \end{bmatrix}, \begin{bmatrix} -1 \\ 0 \\ 1 \end{bmatrix}$$

---

## TOPIC 2 — Matrices: Ax = b

### Problem 2.1 — Matrix times vector = combination of columns

Given:
$$A = \begin{bmatrix} 1 & 0 & 0 \\ -1 & 1 & 0 \\ 0 & -1 & 1 \end{bmatrix}, \quad x = \begin{bmatrix} 2 \\ 5 \\ 3 \end{bmatrix}$$

**Part A:** Compute Ax by the row method (dot product of each row with x).

**Part B:** Compute Ax by the column method
(x₁ × column 1 + x₂ × column 2 + x₃ × column 3).

**Part C:** Verify both give the same answer.

**Part D:** In one sentence — what does this matrix A do to the vector x?
(Hint: look at the output. What operation on the components of x does it perform?)

---

### Problem 2.2 — Solving Ax = b forward

Using the same difference matrix A from Problem 2.1:

$$A = \begin{bmatrix} 1 & 0 & 0 \\ -1 & 1 & 0 \\ 0 & -1 & 1 \end{bmatrix}$$

Solve Ax = b for each right-hand side. Show your work — read off x one component at a time from top to bottom.

**Part A:** b = [2, 3, 4]ᵀ

**Part B:** b = [1, 0, -1]ᵀ

**Part C:** b = [0, 0, 0]ᵀ

**Part D (written):** For Part C you got x = [0,0,0]ᵀ. 
The lecture said: "if b = 0 then x = 0." 
Why is this special? What does it mean for the matrix?

---

### Problem 2.3 — The inverse matrix

The lecture showed that if A is the difference matrix then A⁻¹ is the sum matrix:

$$A^{-1} = \begin{bmatrix} 1 & 0 & 0 \\ 1 & 1 & 0 \\ 1 & 1 & 1 \end{bmatrix}$$

**Part A:** Verify AA⁻¹ = I by hand multiplication. Show every entry.

**Part B:** Use A⁻¹ to solve Ax = b for b = [3, 1, 2]ᵀ.
Just compute x = A⁻¹b directly.

**Part C:** Verify your answer by computing Ax and checking it equals b.

**Part D (written):** The lecture connected this to calculus.
"A is the difference matrix — like a derivative. A⁻¹ is the sum matrix — like an integral."
In 2 sentences: explain why this analogy makes sense using the specific numbers from Part B.

---

### Problem 2.4 — The circular matrix C

$$C = \begin{bmatrix} 1 & 0 & -1 \\ -1 & 1 & 0 \\ 0 & -1 & 1 \end{bmatrix}$$

**Part A:** Add all three rows of C. What do you get?

**Part B:** What does this tell you about Cx = b?
For what values of b does Cx = b have a solution?

**Part C:** Find all vectors x such that Cx = 0.
(Hint: try x = [1,1,1]ᵀ. Then find ALL solutions.)

**Part D:** Why can C not have an inverse?
Answer in one sentence using what you found in Part C.

**Part E (written):** The lecture said A and C are both difference matrices but one is invertible and one is not.
What is the geometric difference between their columns?
(Hint: do the columns of C lie in a plane or fill R³?)

---

## TOPIC 3 — Subspaces

### Problem 3.1 — Identify the subspace

For each description, state which type of subspace it is:
- The origin (zero vector only)
- A line through the origin
- A plane through the origin
- All of R³

**Description A:** All multiples of the vector [1, 2, 3]ᵀ

**Description B:** All combinations of [1,0,0]ᵀ and [0,1,0]ᵀ

**Description C:** All combinations of [1,0,0]ᵀ, [0,1,0]ᵀ, [0,0,1]ᵀ

**Description D:** Only the vector [0,0,0]ᵀ

**Description E:** All vectors [b₁, b₂, b₃]ᵀ where b₁ + b₂ + b₃ = 0

---

### Problem 3.2 — Is it a subspace?

For each set of vectors, decide: is it a subspace? Yes or No. One sentence reason.

**Set A:** All vectors in R² with both components positive: {[x,y]ᵀ : x > 0, y > 0}

**Set B:** All vectors in R³ of the form [a, 2a, 3a]ᵀ for any scalar a

**Set C:** All vectors in R² where x + y = 1

**Set D:** All vectors in R³ where b₁ + b₂ + b₃ = 0

**Key test for any subspace:** If v and w are in the set, is v + w in the set? Is 5v in the set?
Apply this test to verify each of your answers.

---

### Problem 3.3 — Basis: the key concept

**Part A:**
The lecture said three vectors form a basis for R³ if:
- They are independent (no one is a combination of the others)
- Their combinations cover the whole space

Are these three vectors a basis for R³?
$$\begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix}, \begin{bmatrix} 1 \\ 1 \\ 0 \end{bmatrix}, \begin{bmatrix} 1 \\ 1 \\ 1 \end{bmatrix}$$

Check both conditions. For independence: can you write any one of them as a combination of the other two?

**Part B:**
Are these three vectors a basis for R³?
$$\begin{bmatrix} 1 \\ 2 \\ 3 \end{bmatrix}, \begin{bmatrix} 1 \\ 1 \\ 1 \end{bmatrix}, \begin{bmatrix} 3 \\ 5 \\ 7 \end{bmatrix}$$

Hint: check if the third vector is a combination of the first two.

**Part C (written):**
The lecture gave THREE equivalent ways to say "these vectors form a basis":
1. They are independent
2. Their combinations cover the whole space
3. The matrix with these vectors as columns is invertible

Why are all three saying the same thing? Write 3 sentences connecting them.

---

## BOSS PROBLEM — The Two Matrices Combined

This problem uses everything from the lecture.

You have two matrices:
$$A = \begin{bmatrix} 1 & 0 & 0 \\ -1 & 1 & 0 \\ 0 & -1 & 1 \end{bmatrix} \quad \text{and} \quad C = \begin{bmatrix} 1 & 0 & -1 \\ -1 & 1 & 0 \\ 0 & -1 & 1 \end{bmatrix}$$

**Part A:** For A: find all solutions to Ax = 0.
For C: find all solutions to Cx = 0.
What is the fundamental difference?

**Part B:** For A: what vectors b can appear as Ax for some x?
For C: what vectors b can appear as Cx for some x?
Describe each answer as a subspace of R³.

**Part C:** The columns of A form a basis for R³. Verify this by showing:
- No column of A is a combination of the other two
- Their combinations cover all of R³ (equivalently: A is invertible, which we showed)

**Part D:** The columns of C do NOT form a basis for R³. Show this by:
- Finding which column of C lies in the plane of the other two
- Describing the plane (what equation do its vectors satisfy?)

**Part E (written):**
The lecture ended with: "When you look at a matrix, try to see what is it doing."

In 3 sentences, answer:
- What is A doing? (what transform does it represent?)
- What is C doing? (what transform does it represent?)
- Why does one have an inverse and the other does not?

---

## Mastery Checklist

You have internalized Lecture 1 when you can:

- [ ] Compute any linear combination of vectors by hand
- [ ] State what geometric shape all combinations of 1, 2, or 3 independent vectors form
- [ ] Compute Ax both by rows (dot products) and by columns (linear combination)
- [ ] State in one sentence what the difference matrix A does to x
- [ ] Solve Ax = b for a triangular matrix by reading top to bottom
- [ ] Explain why Ax = 0 having only x = 0 as solution means A is invertible
- [ ] Find all solutions to Cx = 0 when C is not invertible
- [ ] State the condition on b for Cx = b to have a solution
- [ ] List all four types of subspaces of R³
- [ ] Check whether a set of vectors is a subspace using the closure test
- [ ] State three equivalent definitions of a basis
- [ ] Explain in words why A has an inverse but C does not

---

*MIT 18.06 Linear Algebra*
*Math practice only — no computation*
*Lecture 1: Vectors, Linear Combinations, Matrices, Subspaces*

generated by claude
