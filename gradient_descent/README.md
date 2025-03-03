# **Comparison of Linear Search and Gradient Descent for Finding Optimal Slope (m)**  

## **Overview**  
This project implements and compares **Linear Search** and **Gradient Descent** to determine the optimal slope (*m*) for a simple linear model:  

$$ y = mx + c + \text{noise} $$  

where:  
- *m* is the slope to be estimated,  
- *c* is a constant intercept (given as 5),  
- *noise* is random noise added to simulate real-world data variability.  

The goal is to find the best value of *m* that minimizes the **Mean Squared Error (MSE)** between the generated data and the predicted values.  

---

## **Dataset Generation**  
A synthetic dataset is generated with 1,000,000 samples using the equation:  

$$ y = 2.5x + 5 + \text{noise} $$  

- *x* values are linearly spaced between -100 and 100.  
- Noise is sampled from a normal distribution N(0, 10) to introduce randomness.
- The dataset is plotted to visualize the noisy linear relationship.  

---

## **Methods Implemented**  

### **1. Linear Search**  
Linear search iterates over a predefined range of *m* values and computes the MSE for each candidate. The *m* with the lowest MSE is selected.  

#### **Steps:**  
1. Define a search range for *m* (e.g., from -5 to 5 with a step of 0.01).  
2. Compute predicted values $\hat{y}$ for each candidate *m*.  
3. Calculate MSE:

$$
MSE = \frac{1}{n} \sum (y - \hat{y})^2
$$

4. Select *m* with the minimum MSE.  

---

### **2. Gradient Descent**  
Gradient Descent is an optimization algorithm that iteratively updates *m* to minimize the loss function (MSE).  

#### **Gradient Descent Update Rule:**  

$$ m = m - \alpha \cdot \frac{\partial J}{\partial m} $$  

where:  
- $\alpha$ (learning rate) controls the step size.  
- $\frac{\partial J}{\partial m}$ is the gradient of the loss function w.r.t. *m*.  
- The gradient is computed as:

$$
\frac{\partial J}{\partial m} = -\frac{2}{n} \sum (y - \hat{y}) x
$$

- The value of *m* is iteratively updated until convergence.  

---

## **Performance Comparison**  
The execution times for both methods are compared over 10 runs. The results are visualized using plots.  

### **Findings:**  
- **Linear Search** provides an exact solution but is much slower.  
- **Gradient Descent** converges faster but may require hyperparameter tuning.  
- On average, Gradient Descent performs significantly better in terms of execution time.  

---

## **Dependencies**  
The project requires the following Python libraries:  

- `numpy`  
- `matplotlib`  
- `time`  

Install dependencies using:  

```sh
pip install numpy matplotlib
