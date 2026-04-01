# 📘 Value Function Approximation using TD(0) – Random Walk


**Name:** Sanad Naqvi
**Roll No:** 221A023

## 🎯 Aim
To implement **Temporal Difference Learning (TD(0))** with **Linear Function Approximation** for estimating the value function in a Random Walk environment.

---

## 🧩 Problem Statement
The goal is to estimate the value of states in a **Random Walk environment** consisting of 5 non-terminal states (A to E) and two terminal states.  

Instead of using a lookup table, we approximate the value function using **linear function approximation**, and update it using **TD(0)** learning.

---

## 📚 Brief Theory

### 🔹 Random Walk Environment
- States: A, B, C, D, E (represented as 1 to 5)
- Terminal states: Left (0) and Right (6)
- Agent starts from the center state (C)
- Moves randomly left or right with equal probability

---

### 🔹 Value Function
The value of a state represents the expected return starting from that state.

True state values are:

[1/6, 2/6, 3/6, 4/6, 5/6]


---

### 🔹 Temporal Difference Learning (TD(0))
TD(0) updates value estimates using:

V(s) ← V(s) + α [r + γV(s') − V(s)]


Where:
- α = learning rate  
- γ = discount factor  
- r = reward  
- s' = next state  

---

### 🔹 Linear Function Approximation
- Value function is approximated as:

  V(s) = w · x(s)

  
- Where:
- `w` = weight vector  
- `x(s)` = feature vector (one-hot encoding)

---

## ⚙️ Implementation Explanation

### 1. State Representation
- Each state is represented using **one-hot encoding**
- Feature vector size = number of states (5)

---

### 2. Initialization
- Weights initialized to zero
- Learning rate (α) = 0.01  
- Discount factor (γ) = 1.0  

---

### 3. Training Process
- Start from the center state (C)
- At each step:
- Move left or right randomly
- Receive reward:
  - `1` if reaching right terminal
  - `0` otherwise
- Update weights using TD(0)

---

### 4. Value Estimation
- After training, values are computed as:

V(s) = w · x(s)


---

### 5. Visualization
- Plot:
- True values
- Estimated values from the model

---

## 📊 Results

- The estimated values gradually approximate the true values.
- Small deviations may occur due to:
- Limited number of episodes
- Learning rate choice
- The graph shows convergence toward the true value function.

---

## ✅ Conclusion

- TD(0) effectively learns value functions from experience.
- Linear function approximation reduces memory usage compared to tabular methods.
- The model successfully approximates the true state values.
- This approach is useful for large or continuous state spaces.

---

## 📖 References

1. Sutton, R. S., & Barto, A. G.  
 *Reinforcement Learning: An Introduction*

2. NumPy Documentation  
 https://numpy.org/

3. Matplotlib Documentation  
 https://matplotlib.org/

---

## 📦 requirements.txt
numpy
matplotlib
