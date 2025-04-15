## ODDS AND ODDS Ratio

### ODDS
ODDS = success/failure
     = p/(1-p)

let's say p = 0.8
then ODDS = 0.8/(1-0.8)
          = 0.8/0.2
          = 4 (for every one failure there are four successes) total of 5 cases


### ODDS RATIO

|                   | Cancer | No Cancer |
|-------------------|--------|-----------|
| Gene Mutation     | 30     | 12        |
| No Gene Mutation  | 10     | 4         |

ODDS of cancer in gene mutation = 30/10 = 3
ODDS of cancer in no gene mutation = 10/4 = 2.5 

ODDS ratio= 3/2.5  = 1.2

So, Here a person with a Gene mutation the chances of getting cancer are 1.2 times more
OR = 1 There is no association between genes and cancer
OR > 1 There is a positive association between genes and cancer
OR < 1 There is a negative association between genes and cancer






## 📘 Understanding Logistic Regression

Logistic Regression is a classification algorithm that combines two key ideas:

- **Regression**: Uses a linear combination of features (like linear regression)
- **Logistic (Logit)**: Applies a transformation to map the output to a probability between 0 and 1

---

### 🔢 Step-by-Step Derivation

1. **Start with a Linear Equation**  
   We begin with a linear combination of input features:  
   \[
   Z = b0+b1*x1
   \]  
   However, this output can range from \(-\infty\) to \(+\infty\), which isn't valid for probabilities.

2. **Convert to Odds**  
   We express the probability \(p\) in terms of odds:  
   p/(1-p)
   Odds range from \(0\) to \(+\infty\).

3. **Apply the Logit Function**  
   Take the natural logarithm (log base e) of the odds to linearize the relationship:  
   ln(p/(1-p)) = b0+b1*x1

4. **Solve for p (Probability)**  
   e^(ln(p/(1-p))) = e^(b0+b1*x1) (let's say b0+b1*x1 is z)
   p/(1-p) = e^z
   p = (1-p)e^z
   p = e^z-p*e^z
   p + p*e^z = e^z
   p(1+e^z) = e^z
   p = e^z/(1+e^z)
   p = 1/(1+e^-z)

---

### ✅ Final Logistic Regression Formula:

p = 1/(1+e^-z)

This is the **sigmoid function**, which maps any real-valued number into the (0, 1) interval — making it ideal for predicting probabilities in binary classification.

---

🧠 Logistic regression is powerful because it keeps the interpretability of linear models while working for classification tasks by squashing outputs between 0 and 1 using the sigmoid function.
