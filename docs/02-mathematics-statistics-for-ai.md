# Chapter 02 — Mathematics & Statistics for AI

**Project:** Artificial Intelligence (AI) — Deep Research & Study Notes  
**Owner / Content Creator:** Sandeep Barupal  
**Copyright:** © 2026 Sandeep Barupal. Original explanatory notes; third-party names and trademarks belong to their respective owners.

> Language: Easy Hindi (Hinglish). Goal formulas ratna nahi, unka meaning aur AI mein use samajhna hai.

## 1. AI ko Mathematics ki zaroorat kyun hai?

AI model data se patterns learn karta hai. Maths model ko data represent karne, relationships calculate karne, uncertainty measure karne aur training error reduce karne mein help karti hai.

Example: House-price prediction mein input features ho sakte hain house size, bedrooms, bathrooms aur location score. Model in features aur known prices ke beech relationship learn karta hai aur naye house ke liye estimated price deta hai.

## 2. Basic Mathematics

### 2.1 Percentage

100 mein se kitna hissa, percentage kehlata hai.

Formula: Percentage = (Part / Total) × 100

Example: 100 images mein se 90 correctly classify hui: 90 / 100 × 100 = 90%.

Note: Accuracy har problem ke liye sufficient metric nahi hoti. Imbalanced data mein precision, recall aur F1-score bhi dekhna pad sakta hai.

### 2.2 Ratio

Do quantities ki comparison.

Example: 60 spam aur 40 normal emails ka ratio 60:40 = 3:2.

### 2.3 Average

Mean = Sum of values / Number of values

Example: 80, 90, 70, 85, 75 ka mean = 80.

## 3. Algebra

Algebra variables aur equations ki madad se relationships represent karta hai.

Example: y = 2x + 5

- x: input
- 2: coefficient/weight in this simple equation
- 5: constant/bias-like term
- y: output

Agar x = 10, to y = 25.

AI mein functions aur equations prediction rules, model parameters aur transformations ko represent karte hain.

Important topics:
- Variables and constants
- Equations and inequalities
- Functions and graphs
- Exponents and powers
- Logarithms
- Polynomial expressions

## 4. Linear Algebra

Linear Algebra modern ML aur Deep Learning mein bahut important hai. Data ko vectors, matrices aur tensors mein represent kiya jaata hai.

### 4.1 Scalar

Ek single number, jaise 5.

### 4.2 Vector

Numbers ki ordered list: [10, 20, 30]

House example: [1000, 2, 3] ka matlab size 1000 sq ft, 2 bedrooms, 3 bathrooms ho sakta hai. Real projects mein units aur feature scaling clearly define karna zaroori hai.

### 4.3 Matrix

Rows aur columns mein arranged numbers:

A = [[1, 2], [3, 4]]

Example dataset:
X = [[800, 2], [1000, 3], [1200, 3]]

Har row ek house aur columns size/bedrooms ko represent kar sakte hain.

### 4.4 Tensor

Tensor multi-dimensional numerical data structure hai. Scalar, vector aur matrix tensors ke special cases hain.

Color image ko commonly height × width × 3 channels (RGB) ke array/tensor ke roop mein represent kiya ja sakta hai. Batch mein multiple images hon to ek additional dimension aa sakti hai.

AI uses:
- Neural network calculations
- Image and video processing
- Language model computations
- GPU-based numerical operations

Important topics:
- Vector addition and subtraction
- Dot product
- Matrix multiplication
- Transpose and inverse (where applicable)
- Eigenvalues and eigenvectors
- Tensor shapes and broadcasting

## 5. Statistics

Statistics data ko summarize aur analyse karne ka method hai.

### 5.1 Mean

Values ka average. Example: 10, 20, 30, 40, 50 ka mean = 30.

### 5.2 Median

Sorted data ki middle value. Example: 10, 20, 30, 40, 50 ka median = 30. Even number of values mein beech ki do values ka average liya jaata hai.

### 5.3 Mode

Jo value sabse zyada baar aati hai. Example: 10, 20, 20, 30, 40 ka mode = 20.

### 5.4 Variance

Variance data values ke mean se squared spread ko measure karta hai.

Population variance: σ² = Σ(xᵢ - μ)² / N

Sample variance: s² = Σ(xᵢ - x̄)² / (n - 1)

Population aur sample formulas ka denominator alag hota hai.

### 5.5 Standard Deviation

Standard deviation variance ka square root hai: σ = √σ². Ye data ke spread ko original unit mein samajhne mein help karta hai.

### 5.6 Other statistics concepts

| Concept | Simple meaning |
|---|---|
| Population | Pura group jiske baare mein study karni hai |
| Sample | Population ka selected subset |
| Distribution | Values kis tarah spread hain |
| Correlation | Variables ke beech association |
| Covariance | Do variables saath kaise vary karte hain |
| Outlier | Baaki values se kaafi different observation |
| Sampling bias | Sample representative na hone ki problem |
| Hypothesis testing | Data ke basis par statistical claim evaluate karna |

**Important:** Correlation ka matlab causation nahi hota. Do variables related dikh sakte hain bina ek doosre ka cause hue.

## 6. Probability

Probability kisi event ke hone ki likelihood batati hai.

Basic equally-likely outcomes ke case mein:
P(A) = favourable outcomes / total outcomes

Fair coin toss mein Head ki probability = 1/2 = 0.5 = 50%.

Probability 0 aur 1 ke beech hoti hai:
- 0: impossible event
- 1: certain event
- 0.5: 50% chance

### 6.1 Conditional Probability

Kisi event B ke hone ki condition par event A ki probability:

P(A|B) = P(A ∩ B) / P(B), jab P(B) > 0.

### 6.2 Bayes' Theorem

P(A|B) = [P(B|A) × P(A)] / P(B)

New evidence milne ke baad probability update karne mein help karta hai.

### 6.3 Other probability topics

- Random variables
- Independent and dependent events
- Joint and marginal probability
- Probability distributions
- Expected value
- Likelihood
- Bayes' theorem

AI uses: classification confidence, uncertainty estimation, Bayesian models aur probabilistic prediction.

**Caution:** Model ka 90% confidence score automatically guarantee nahi karta ki 90% cases mein prediction correct hogi. Calibration aur evaluation zaroori hai.

## 7. Calculus

Calculus changing quantities ko study karta hai. Model training mein derivatives aur gradients important hain.

### 7.1 Derivative

Derivative batata hai ki input change hone par function ka output kitni rate se change hota hai.

Example: y = x²; derivative dy/dx = 2x. Agar x = 3, derivative 6 hoga.

### 7.2 Integral

Integral small quantities ko accumulate karke total/area calculate karne mein use hota hai.

Example: ∫x² dx = x³/3 + C.

AI ke basic model training mein derivative aur gradient ka direct use zyada common hai; integral ka role specific mathematical/statistical contexts mein aata hai.

### 7.3 Calculus topics

- Limits
- Continuity
- Derivatives
- Partial derivatives
- Chain rule
- Gradients
- Integrals

## 8. Optimization

Optimization ka aim kisi objective ko minimize ya maximize karna hai. ML mein aksar model loss ko minimize karne ki koshish ki jaati hai.

### 8.1 Loss Function

Loss function prediction aur target ke beech error measure karta hai.

Example:
- Actual price = ₹50 lakh
- Predicted price = ₹40 lakh
- Absolute error = ₹10 lakh

Alag tasks ke liye alag loss functions hote hain: Mean Squared Error, Mean Absolute Error, Cross Entropy etc.

### 8.2 Gradient Descent

Gradient descent model parameters ko update karne ka optimization method hai.

Update rule: θ_new = θ_old - α × ∇L(θ)

- θ: model parameters
- α: learning rate
- ∇L(θ): loss ka gradient

Basic process:
1. Model prediction karta hai.
2. Loss calculate hota hai.
3. Gradient calculate hota hai.
4. Parameters update hote hain.
5. Process repeat hota hai.

### 8.3 Important optimization terms

| Term | Meaning |
|---|---|
| Loss function | Model error/objective measure |
| Gradient | Parameters ke respect mein change ki direction/rate |
| Learning rate | Update step ka size |
| Batch size | Ek update mein process hone wale examples ki count |
| Epoch | Training dataset par ek complete pass |
| Local minimum | Nearby region ka low point |
| Overfitting | Training data par achha, new data par weak performance |
| Regularization | Overfitting reduce karne ke methods |

Learning rate bahut high ho to training unstable ho sakti hai; bahut low ho to training slow ho sakti hai.

## 9. Information Theory

Information Theory information aur uncertainty ko mathematically study karti hai.

### 9.1 Entropy

Entropy probability distribution ki uncertainty measure karti hai.

Formula: H(X) = -Σ p(x) log₂ p(x)

Balanced binary outcomes (50%/50%) ki entropy 1 bit hoti hai. Agar ek outcome certain ho (100%/0%), entropy 0 hoti hai.

### 9.2 Information Gain

Information Gain batata hai ki kisi split/feature se uncertainty kitni reduce hui. Decision Tree learning mein use hota hai.

### 9.3 Cross Entropy

Cross Entropy true distribution aur predicted distribution ke beech difference measure karne ka method hai. Classification aur language model training mein common loss ke roop mein use hota hai.

## 10. House Price Prediction — Combined Practical Example

Goal: House ke features se price estimate karna.

1. **Data:** House size, bedrooms, bathrooms, location aur actual price collect karein.
2. **Algebra:** Input-output relationship ko function ke roop mein represent karein.
3. **Linear Algebra:** Rows/features ko matrices aur vectors mein store karein.
4. **Statistics:** Missing values, distribution, outliers aur feature relationships inspect karein.
5. **Probability:** Prediction uncertainty ko suitable method se analyse karein.
6. **Calculus:** Model parameters ke respect mein loss gradients calculate karein.
7. **Optimization:** Training data par loss reduce karein.
8. **Evaluation:** Separate test data par MAE/RMSE jaise metrics check karein.

Data ko train/validation/test sets mein split karna zaroori hai, taaki evaluation fair ho aur data leakage avoid ho.

## 11. Maths ke liye Python Tools

| Tool | Use | Official link |
|---|---|---|
| NumPy | Arrays, vectors, matrices, numerical operations | https://numpy.org/ |
| Pandas | Tabular data cleaning and analysis | https://pandas.pydata.org/ |
| Matplotlib | Charts and visualizations | https://matplotlib.org/ |
| SciPy | Scientific computing and optimization | https://scipy.org/ |
| SymPy | Symbolic algebra and calculus | https://www.sympy.org/ |

## 12. Learning resources

- Khan Academy Maths: https://www.khanacademy.org/math
- 3Blue1Brown: https://www.3blue1brown.com/
- Seeing Theory: https://seeing-theory.brown.edu/
- NumPy Learn: https://numpy.org/learn/

## 13. Self-check questions

1. Mean aur median mein kya difference hai?
2. Vector aur Matrix kya hote hain?
3. Tensor ka image processing mein kya use hai?
4. Variance aur standard deviation kya measure karte hain?
5. Conditional probability kya hai?
6. Derivative kya batata hai?
7. Gradient Descent ka purpose kya hai?
8. Entropy uncertainty ko kaise represent karti hai?

## 14. Chapter summary

- Basic Maths calculations aur percentages mein help karti hai.
- Algebra relationships aur functions represent karta hai.
- Linear Algebra numerical data ko vectors, matrices aur tensors mein represent karta hai.
- Statistics data ko summarize aur analyse karti hai.
- Probability uncertainty aur likelihood model karti hai.
- Calculus gradients calculate karne mein help karta hai.
- Optimization model loss ko reduce karne mein use hota hai.
- Information Theory entropy aur cross entropy jaise concepts provide karti hai.
