# Inductive Bias in Machine Learning

## What is Inductive Bias?

In Machine Learning, we are trying to learn an **unknown function** ( f ) from limited data.

However, learning from data alone is not enough.

> A learning algorithm must make **assumptions** about the problem in order to generalize.

These assumptions are called **Inductive Bias**.

## Why Inductive Bias is Necessary

Without any assumptions, a model cannot decide between multiple valid solutions.

> Many different hypotheses can perfectly fit the same training data.

As a result:

- the model cannot choose the “correct” function
- it cannot make reliable predictions on unseen data
- it fails to **generalize**

## Types of Inductive Bias

### 1. Language Bias (Model Bias)

This restricts the **hypothesis space ( H )**.

Examples:

- Linear models → only straight-line relationships
- Neural networks → can represent complex patterns

### 2. Search Bias (Algorithm Bias)

This affects **how the algorithm searches** within the hypothesis space.

For example:

- preferring simpler models
- following specific optimization paths

## Example: Learning Boolean Functions

<img src="images/table4.png" width="300" />

We consider a simple problem:

- Input: x = (**$x_1, x_2, x_3, x_4$**) (binary features)
- Output: **$y$** → {0,1}

## Why the Problem is Ambiguous

With 4 binary inputs:

**$2^4 = 16$** possible inputs

Each input can map to 0 or 1, so:

|H| = **$2^{16} = 65,536$**

There are **65,536 possible functions**.

## After Observing Limited Data

<img src="images/table5.png" width="150" />

Suppose we only observe **7 training examples**.

That means:

- 7 inputs → known outputs
- 9 inputs → **unknown outputs**

Each of the 9 unknown inputs can be either 0 or 1:

**$2^9 = 512$**

So there are **512 different functions** that all match the training data.

## Why the Model Cannot Decide

Let’s take a **concrete unseen input**:

**$x = (1,1,1,1)$**

This input was **not in the training data**.

Now consider two possible hypotheses:

- **Hypothesis A:** **$h(x) = 0$**
- **Hypothesis B:** **$h(x) = 1 $**

Both:

- perfectly match all 7 training examples
- but give **different predictions** for this new input

So which one is correct?

> The model has **no way to decide**.

## The Real Problem

The issue is not just missing data.

> The problem is that **multiple hypotheses are equally valid**.

This creates **ambiguity**.

## The Lookup Table Problem

Without inductive bias, the model behaves like a:

> **Lookup Table Learner**

It:

- memorizes training examples
- only works on seen inputs
- fails on new data

## No Bias ⇒ No Generalization

> Without inductive bias, learning is impossible.

Because:

- too many valid solutions exist
- no preference between them
- predictions become arbitrary

Therefore:

Inductive bias is not a limitation — it is a **requirement**. Since a model's job is not just to predict but to **make consistent and justifiable predictions**, inductive bias makes that possible.

It allows Machine Learning systems to:

- reduce the number of possible solutions
- choose meaningful hypotheses
- generalize to unseen data

## Using Inductive Bias: Conjunctive Rules

So far, we have seen that without inductive bias, learning is impossible due to the massive hypothesis space.

To solve this, we introduce a **language bias** by restricting the type of functions the model is allowed to use.

---

### Restricting the Hypothesis Space

Instead of allowing **all possible Boolean functions**, we limit the model to only use **conjunctive rules**.

These are logical rules built using:

- AND operations
- simple conditions on inputs

Examples:

- **$h(x) = x_2$**
- **$h(x) = x_1 \text { AND } x_2$**
- **$h(x) = \text{NOT}(x_1) \text{ AND } x_2 $**

---

### How This Reduces Complexity

For each input feature, we now have only three possibilities:

- the feature must be true
- the feature must be false
- the feature is ignored ("don’t care")

So for **$n$** inputs:

**$|H| = 3^n + 1$**

The **$+1$** accounts for **contradictory rules**.

For example, a rule that requires:

- **$ x_1 = 1 \text { AND } x_1 = 0 $**

is impossible to satisfy.

All such contradictory rules always evaluate to **False**, so they are grouped together as a **single additional hypothesis**.

---

For **$n = 4 $**

**$|H| = 3^4 + 1 = 81 + 1 = 82$**

---

### Why This Matters

Compare:

- Without bias → **$65,536$** possible functions
- With bias → only **$82$** hypotheses

> This dramatically reduces the search space.
