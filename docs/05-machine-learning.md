# Chapter 05 — Machine Learning

**Project:** Artificial Intelligence (AI) — Deep Research & Study Notes  
**Owner / Content Creator:** Sandeep Barupal  
**Copyright:** © 2026 Sandeep Barupal. Original explanatory notes; third-party names and trademarks belong to their respective owners.

## 1. Machine Learning kya hai?

Machine Learning (ML), Artificial Intelligence ka ek part hai. Ismein computer ko har rule manually likhkar nahi batana padta. Hum use data aur examples dete hain, aur algorithm unmein patterns seekhkar prediction ya decision karta hai.

Example: Purane gharon ke size, bedrooms aur prices ka data dekar model ko train karna. Model phir naye ghar ki estimated price predict kar sakta hai.

## 2. AI, ML aur Deep Learning ka relation

- AI: Machines se intelligent tasks karwana.
- Machine Learning: Data se patterns seekhna.
- Deep Learning: Multiple layers wale neural networks se complex patterns seekhna.

Deep Learning, Machine Learning ka subset hai; Machine Learning, AI ka subset hai.

## 3. Traditional programming vs Machine Learning

Traditional programming: Rules + Input Data → Program → Output.

Machine Learning: Training Examples → Learning Algorithm → Trained Model → New Input → Prediction.

Example: Traditional rule transaction ko fixed amount threshold se flag karega. ML model historical patterns se unusual transaction identify karna seekh sakta hai. High-impact decisions mein human review aur suitable controls zaroori hain.

## 4. Machine Learning ke 3 main types

### A. Supervised Learning
Input ke saath correct answer (label) bhi diya jata hai. Examples: spam classification, house-price prediction.

### B. Unsupervised Learning
Data mein labels nahi diye jaate; algorithm patterns ya groups identify karta hai. Example: similar customers ki clustering.

### C. Reinforcement Learning
Agent environment mein actions leta hai aur rewards/penalties ke feedback se strategy seekhta hai. Examples: game-playing agent, robot navigation.

## 5. Classification aur Regression

**Classification:** Category predict karna, jaise Spam/Not Spam, Cat/Dog, Fraud/Normal.

**Regression:** Continuous numerical value predict karna, jaise house price, temperature ya sales amount.

| Classification | Regression |
|---|---|
| Category output | Numerical output |
| Spam / Not Spam | ₹35 lakh |
| Fraud / Normal | 27.5°C |

## 6. Model training workflow

1. Data collect karna.
2. Data clean aur prepare karna.
3. Features aur target define karna.
4. Data ko training, validation aur test sets mein split karna.
5. Algorithm select karna.
6. Training data par model train karna.
7. Validation se settings improve karna.
8. Test set par final evaluation karna.
9. Model deploy karna.
10. Real-world performance monitor karna.

Common illustrative split 70% training, 15% validation aur 15% test ho sakta hai. Ye fixed rule nahi; data size, task aur evaluation design ke hisaab se split choose hota hai.

## 7. Important ML terms

| Term | Simple meaning |
|---|---|
| Dataset | Data ka collection |
| Feature | Model ka input |
| Label / Target | Correct answer jo predict karna hai |
| Algorithm | Learning ka method |
| Model | Training ke baad seekha hua system |
| Training | Model ko examples se sikhana |
| Prediction | New input par output |
| Epoch | Training data ka ek complete pass |
| Hyperparameter | Training se pehle set ki gayi configuration |
| Loss | Prediction error measure karne ka function |
| Inference | Trained model se prediction lena |

## 8. Important algorithms

| Algorithm | Common use |
|---|---|
| Linear Regression | Numerical prediction |
| Logistic Regression | Classification |
| Decision Tree | Rule-like decision paths |
| Random Forest | Multiple trees ka combined prediction |
| K-Nearest Neighbors (KNN) | Similar examples ke basis par prediction |
| K-Means | Data ko clusters mein divide karna |
| Support Vector Machine (SVM) | Classes ke beech decision boundary |
| Naive Bayes | Probability-based classification |
| Gradient Boosting | Sequentially models combine karke errors improve karna |

Koi ek algorithm har problem ke liye best nahi hota. Data, accuracy, speed, interpretability aur cost ke basis par selection hota hai.

## 9. Overfitting aur Underfitting

- **Overfitting:** Model training data ko bahut zyada memorize kar leta hai. Training par achha, unseen data par weak.
- **Underfitting:** Model important patterns nahi seekh pata. Training aur unseen data dono par weak.
- **Good fit:** Model useful patterns seekhta hai aur unseen data par reasonably perform karta hai.

Overfitting reduce karne ke tareeke: representative data, regularization, cross-validation, simpler model, feature selection aur suitable cases mein early stopping.

## 10. Model evaluation

### Classification metrics
- Accuracy: Total predictions mein correct predictions ka proportion.
- Precision: Predicted positive cases mein actual positive ka proportion.
- Recall: Actual positive cases mein se identify kiye gaye positive cases ka proportion.
- F1-score: Precision aur Recall ka harmonic mean.
- Confusion Matrix: Correct/incorrect class predictions ka breakdown.

### Regression metrics
- MAE: Absolute errors ka average.
- MSE: Squared errors ka average.
- RMSE: MSE ka square root.
- R²: Model target variation ko kitna explain karta hai, iska measure.

Sirf accuracy har situation mein enough nahi. Imbalanced fraud dataset mein precision, recall aur confusion matrix bhi check karne chahiye.

## 11. Feature scaling

Features ki ranges alag ho sakti hain, jaise age 25, salary 50,000 aur experience 3. Kuch algorithms mein scaling useful hoti hai.

- Standardization: Values ko mean 0 aur standard deviation 1 ke around scale karna.
- Min-Max scaling: Values ko selected range, commonly 0–1, mein map karna.

```python
from sklearn.preprocessing import StandardScaler

scaler = StandardScaler()
scaled_data = scaler.fit_transform([[20], [30], [40]])
print(scaled_data)
```

Scaling har algorithm ke liye zaroori nahi. Tree-based models jaise Decision Tree aur Random Forest ko generally iski need nahi hoti.

## 12. Cross-validation

Cross-validation se model ko training data ke different folds par evaluate kiya jata hai.

5-fold example:
1. Data ko 5 parts mein divide karein.
2. 4 parts par train aur 1 part par validate karein.
3. Validation part rotate karke 5 rounds karein.
4. Results ko summarize karein.

Ye single split ke comparison mein performance ka more stable estimate de sakta hai. Time-series data mein random folds ke bajay time-aware split use karna pad sakta hai.

## 13. Hyperparameter tuning

Hyperparameters training se pehle set ki jaane wali settings hain, jaise learning rate, tree depth, number of trees, KNN neighbors aur regularization strength.

Common methods: Grid Search, Random Search aur Bayesian Optimization.

```python
from sklearn.model_selection import GridSearchCV
from sklearn.tree import DecisionTreeClassifier

model = DecisionTreeClassifier(random_state=42)
params = {
    "max_depth": [2, 3, 5, None],
    "min_samples_split": [2, 5, 10]
}

search = GridSearchCV(model, params, cv=5)
```

Tuning ke liye validation/cross-validation use karein; final test set ko tuning decisions se alag rakhein.

## 14. Practical project — Iris flower classification

Goal: Flower measurements se Iris species predict karna.

```python
from sklearn.datasets import load_iris
from sklearn.model_selection import train_test_split
from sklearn.tree import DecisionTreeClassifier
from sklearn.metrics import accuracy_score

iris = load_iris()
X = iris.data
y = iris.target

X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42, stratify=y
)

model = DecisionTreeClassifier(random_state=42)
model.fit(X_train, y_train)

predictions = model.predict(X_test)
print("Accuracy:", accuracy_score(y_test, predictions))

new_flower = [[5.1, 3.5, 1.4, 0.2]]
result = model.predict(new_flower)
print("Predicted flower:", iris.target_names[result[0]])
```

Yahan X mein measurements (features) aur y mein species labels hain. Model training data par learn karta hai aur test data par evaluate hota hai. Ek small standard dataset ka score real-world performance ki guarantee nahi hota.

## 15. Real-world applications

- Banking: fraud detection, credit-risk estimation.
- E-commerce: recommendations, sales forecasting, customer grouping.
- Healthcare: image analysis aur risk prediction; clinical use mein expert validation required hai.
- Cybersecurity: anomaly detection aur threat classification.
- Transport: traffic prediction aur demand forecasting.

## 16. Limitations and risks

1. Poor-quality data se poor predictions aa sakti hain.
2. Biased data unfair results de sakta hai.
3. Overfitting unseen data par failure la sakta hai.
4. Kuch models explain karna difficult hota hai.
5. Privacy aur security risks ho sakte hain.
6. Training/deployment compute cost la sakte hain.
7. Real-world data change hone par model performance gir sakti hai.

Deployment ke baad monitoring, periodic evaluation aur controlled updates zaroori hain.

## 17. Official learning resources

- Scikit-learn User Guide: https://scikit-learn.org/stable/user_guide.html
- Google Machine Learning Crash Course: https://developers.google.com/machine-learning/crash-course
- Kaggle Learn: https://www.kaggle.com/learn
- UCI Machine Learning Repository: https://archive.ics.uci.edu/
- PyTorch Tutorials: https://pytorch.org/tutorials/

## 18. Knowledge check

1. Machine Learning kis ka part hai?
2. Supervised Learning mein labels hote hain ya nahi?
3. House price prediction classification hai ya regression?
4. Overfitting ka kya matlab hai?
5. Test dataset ka main purpose kya hai?

Answer hints: AI; labels hote hain; regression; training data ko memorize karna; unseen data par final evaluation.

## 19. Chapter summary

- ML data se patterns seekhkar predictions karta hai.
- Supervised, Unsupervised aur Reinforcement Learning major learning types hain.
- Classification categories predict karta hai; Regression numerical values.
- Training, validation aur test data ka role alag hota hai.
- Algorithms task ke hisaab se select hote hain.
- Evaluation mein suitable metrics use karne chahiye.
- Overfitting, leakage, bias aur data quality ko monitor karna zaroori hai.
- Scikit-learn se beginner ML model train kiya ja sakta hai.

**Chapter 05 status:** Learning notes prepared and added to the repository.
