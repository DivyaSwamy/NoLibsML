## Implementing Machine Learning Algorithms from Scratch

### Core Concepts to Understand

When implementing any machine learning algorithm, there are a few fundamental components you must clearly define:

#### 1. Model Representation  
What is the functional form of the model?

y = f(X)

- Define what kind of function f(X) is (linear, logistic, neural network, etc.)

---

#### 2. Cost (Loss) Function  
What are we optimizing?

- The loss function measures how far predictions are from true values.
- Examples:
  - Mean Squared Error (MSE) for regression

---

#### 3. Learnable Parameters  
What variables is the model learning?

- These are the parameters inside f(X)
- Example (Linear Regression):
  - Weights (slope)
  - Bias (intercept)

---

#### 4. Learning Algorithm  
How does the model learn?

- Most commonly: Gradient Descent
- Iteratively updates parameters to minimize the loss.
  - For e.g slope / intercept in linear regression

---

#### 5. Gradients (Derivatives)  
How do parameters change?

- Compute derivative of loss w.r.t. parameters:
- Critical for updating parameters correctly
- Example:
  - Linear Regression ? gradients w.r.t. weights and bias

---

#### 6. Terminology  
- Weights ? coefficients (slopes)  
- Bias ? intercept  

---

## Programming Structure for ML from Scratch

A clean way to implement ML algorithms is using an object-oriented approach (class-based design).

---

### Model Class Structure

Your model class should include the following functions:

#### 1. `__init__` (Initialization)
- Set hyperparameters:
  - Learning rate
  - Number of iterations (epochs)

---

#### 2. `forward()` / `predict()`
- Computes predictions:

y_pred = f(X)

---

#### 3. `__loss()`
- Computes the loss value
- Internal method (not meant for external use)

---

#### 4. `__gradients()`
- Computes gradients of loss w.r.t. parameters
- Core of learning

---

#### 5. `__update()`
- Updates weights and bias using gradients:
   - ? = ? - ? * ?L
   - weight = weight + learning_rate* gradient

---

#### 6. `fit()`
- Trains the model:
  - Runs forward pass
  - Computes loss
  - Computes gradients
  - Updates parameters
- Repeats for given number of iterations

---

##  Private vs Public Methods

### Private Methods (Internal Use)
- Prefixed with `__`
- Examples:
  - `__loss`
  - `__gradients`
  - `__update`

By convention, these should not be accessed outside the class.

---

### Public Methods (User-Facing)
- Used externally to interact with the model
- Examples:
  - `fit()`
  - `predict()`

---

## Summary

To implement any ML algorithm from scratch, always think in this order:

1. Define the model f(X)  
2. Define the loss function  
3. Identify parameters to learn  
4. Choose optimization method (e.g., Gradient Descent)  
5. Derive gradients  
6. Implement training loop  