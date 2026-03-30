# Machine Learning Models

After defining the **task** and understanding the **data**, the next step in building a Machine Learning system is choosing a **model**.

---

## What is a Model?

A model is a mathematical or logical structure used to **capture the relationship between input data and outputs**.

Its goal is to:

> **represent the hidden patterns in the data in a form that can be used for prediction or analysis**.

---

### The Language of the Model

Every model describes relationships using a specific **language**.

This language can take different forms:

- mathematical equations
- logical rules
- probabilistic representations

The choice of this language determines **how the system represents knowledge**.

---

### Model as a Function

In most Machine Learning settings, a model is represented as a function:

**$h(x, w)$**

where:

- **$x$** = input data
- **$w$** = parameters (adjustable values of the model)
- **$h$** = the function (model)

The parameters **$w$** are learned from data.

---

## Core Terminology

To understand how models work, we introduce some key concepts.

### Training Example

A training example is a pair:

(**$x$**, **$y$**)

where:

- **$x$** = input data
- **$y$** = target value (desired output)

In real-world data, the target often includes noise:

**$y$** = **$f(x)$** + noise

---

### Target Function (**$f$**)

The **target function $f$** is the true underlying relationship between input and output.

- It represents the real rule governing the data
- It is **unknown** in practice

---

### Hypothesis (**$h$**)

The model does not know the true function **$f$**, so it learns an approximation:

**$h(x)$**

This approximation is called a **hypothesis**.

The goal is:

**$h(x) ≈ f(x)$**

---

### Hypothesis Space (H)

The **hypothesis space H** is the set of all possible functions the model can represent.

Examples:

- all possible straight lines
- all possible decision rules
- all possible neural network configurations

The choice of model determines the hypothesis space.

---

## Types of Models (Hypothesis Spaces)

Different models represent data in different ways.

### 1. Linear Models

Linear models use **continuous mathematical functions**.

Example:

**$h(x) = w₁x + w₀$**

For classification:

**$h(x) = sign(wᵀx + w₀)$**

These models are:

- simple
- interpretable
- based on weighted combinations of inputs

---

### 2. Symbolic (Rule-Based) Models

These models use **logical rules**.

Example:

```

if (x₁ = 0) and (x₂ = 1)
then h(x) = 1
else
h(x) = 0

```

They are:

- easy to interpret
- similar to traditional programming logic

---

### 3. Probabilistic Models

These models describe relationships using **probability distributions**.

They estimate:

**$p(x, y)$**

This allows the system to:

- model uncertainty
- compute likelihoods
- make probabilistic predictions

---

### 4. Instance-Based Models (K-Nearest Neighbors)

These models do not build a global function.

Instead, they:

- store training examples
- compare new data to existing data

Example:

To predict a value:

- find the **K nearest neighbors**
- compute their average (for regression)

## Key Points

The choice of model determines:

- what patterns can be learned
- how flexible the system is
- how predictions are made

> A model defines the **set of possible solutions** the learning algorithm can choose from.

## Summary

Building a Machine Learning model involves:

- defining a hypothesis space
- selecting a model structure
- learning parameters from data

The ultimate goal is to find a function:

**$h(x)$**

that closely approximates the true relationship:

**$f(x)$**

and generalizes well to new data.
