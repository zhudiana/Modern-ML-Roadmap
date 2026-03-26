# Overview of a Machine Learning (Predictive) System

Machine Learning systems are typically built as a pipeline of interacting components.  
Each component plays a specific role in transforming raw observations from the world into useful predictions.

At a high level, a predictive ML system starts with **data**, uses a **learning algorithm** to train a **model**, and produces **predictions** that can be evaluated through **validation**.

The diagram below illustrates the main components of this process.

![Overview of a Machine Learning System](/images/ml-system-overview.png)

## Components of a Predictive ML System

### 1. DATA (World Observations)

Everything in Machine Learning starts with **data**. This is the raw experience or the "world observations" that you feed into the computer.

This could be:

- a database of past medical records
- a folder of handwritten digit images
- thousands of spam emails

The quality and quantity of data strongly influence how well a model can learn.

---

### 2. TASK

Before building a model, you need to define exactly what you want the system to do with the data.

The "task" specifies the objective of the system.

For example, are you trying to predict a discrete category (Classification, like "Spam" vs. "Not Spam") or a continuous number (Regression, like predicting the price of a house)?

---

### 3. MODEL (Agent / Hypothesis)

The **model** is the actual mathematical function that represents the relationship between inputs and outputs.

You can think of it as the structure of the "brain" you are creating.

You have to choose what kind of model to use. For instance, deciding whether a _simple linear equation_ is enough, or if you need a complex _Deep Neural Network_ to capture the relationships in your data.

---

### 4. LEARNING ALGORITHM

The **learning algorithm** is the procedure used to train the model.

Its job is to use the available **data** to adjust the **parameters of the model** so that the model fits the data as well as possible.

In simple terms, the algorithm repeatedly modifies the internal mathematics of the model until it finds a good representation of the patterns in the data.

---

### 5. PREDICTION

Once training is complete and the model is built, it is ready to be used to make **predictions**.

When you give the trained model a brand-new, unseen piece of data, it uses the patterns it learned to predict the correct answer.

For example:

- predicting whether an email is spam
- recognizing a handwritten digit
- estimating the price of a house

---

### 6. VALIDATION

This is a critical step. You cannot just assume your model works perfectly after training it. You must verify that it works correctly.

**Validation** is the process of testing the model on data it has not seen before.

This step ensures that the model has learned meaningful patterns rather than simply memorizing the training data.

A successful model should be able to **generalize** and make accurate predictions on new data.

---

In short, building an ML system involves choosing the right **Data** and **Task**, selecting an appropriate **Model**, using a **Learning Algorithm** to build or improve that model, and finally using **Validation** to ensure its **Predictions** are accurate.
