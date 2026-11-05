# Chapter 03 — Python Programming for AI

**Project:** Artificial Intelligence (AI) — Deep Research & Study Notes  
**Owner / Content Creator:** Sandeep Barupal  
**Copyright:** © 2026 Sandeep Barupal. Original explanatory notes; third-party names and trademarks belong to their respective owners.

## 1. Python kya hai?

Python ek programming language hai. Iski help se hum computer ko step-by-step instructions dete hain. Python ka syntax relatively simple hota hai, isliye beginners aur AI developers dono ise use karte hain.

Example:

```python
print("Hello AI World!")
```

Output:
```text
Hello AI World!
```

## 2. AI mein Python ka use kyon hota hai?

Python ka use data analysis, Machine Learning, Deep Learning, Generative AI, AI agents, automation aur AI applications ke backend mein hota hai. Iske liye bahut saari libraries aur community resources available hain.

## 3. Python program kaise chalta hai?

1. Developer Python code likhta hai.
2. Python runtime code ko process karta hai.
3. Program ke instructions execute hote hain.
4. Output ya error milta hai.
5. Developer result check karke code improve karta hai.

## 4. Setup aur tools

- Python: https://www.python.org/
- Visual Studio Code: https://code.visualstudio.com/
- Jupyter: https://jupyter.org/

Python install karne ke baad terminal mein `python --version` (kuch systems par `python3 --version`) chala kar version check kar sakte hain.

## 5. Python fundamentals

### 5.1 Variables

Variable data ko naam dekar store karta hai.

```python
student_name = "Aman"
age = 20
marks = 85.5
```

### 5.2 Data types

| Type | Meaning | Example |
|---|---|---|
| int | Whole number | `age = 20` |
| float | Decimal number | `price = 99.5` |
| str | Text | `name = "Aman"` |
| bool | True/False | `is_active = True` |
| list | Ordered, changeable collection | `marks = [70, 80, 90]` |
| tuple | Ordered, generally fixed collection | `point = (4, 7)` |
| dict | Key-value data | `user = {"name": "Aman"}` |
| set | Unique values | `tags = {"AI", "Python"}` |

### 5.3 Operators

- Arithmetic: `+`, `-`, `*`, `/`, `//`, `%`, `**`
- Comparison: `==`, `!=`, `>`, `<`, `>=`, `<=`
- Logical: `and`, `or`, `not`
- Assignment: `=`, `+=`, `-=`

### 5.4 Conditions

Conditions ke through program decision leta hai.

```python
marks = 72

if marks >= 40:
    print("Pass")
else:
    print("Try again")
```

### 5.5 Loops

Loop kisi task ko baar-baar chalata hai.

```python
for number in range(1, 4):
    print(number)

count = 1
while count <= 3:
    print(count)
    count += 1
```

### 5.6 Functions

Function reusable code block hota hai.

```python
def calculate_average(values):
    if not values:
        return 0
    return sum(values) / len(values)

print(calculate_average([70, 80, 90]))
```

## 6. Important Python concepts

- **OOP:** Code ko classes aur objects mein organize karne ka approach.
- **Class:** Object banane ka blueprint.
- **Object:** Class se bana hua instance.
- **Inheritance:** Ek class ka doosri class ke features reuse karna.
- **Exception handling:** Errors ko safely handle karna using `try` and `except`.
- **File handling:** Files read/write karna.
- **Modules and packages:** Code ko reusable files/folders mein organize karna.
- **Virtual environment:** Har project ki Python dependencies ko alag rakhna.
- **Decorators:** Function ke behavior ko wrap/extend karna.
- **Generators:** Values ko zaroorat ke hisaab se one-by-one produce karna.
- **Async programming:** I/O wait ke dauran doosre tasks ko progress karne dena.

Simple OOP example:

```python
class Student:
    def __init__(self, name):
        self.name = name

    def introduce(self):
        return f"My name is {self.name}"

student = Student("Aman")
print(student.introduce())
```

Error handling example:

```python
try:
    number = int(input("Enter a number: "))
    print(100 / number)
except ValueError:
    print("Please enter a valid whole number.")
except ZeroDivisionError:
    print("Number zero nahi hona chahiye.")
```

## 7. Python libraries used in AI

| Library | Simple use |
|---|---|
| NumPy | Numerical calculations aur arrays |
| Pandas | Table-like data read, clean aur analyze karna |
| Matplotlib | Graphs aur charts banana |
| Scikit-learn | Traditional Machine Learning models |
| PyTorch | Deep Learning aur neural networks |
| TensorFlow | Machine Learning aur Deep Learning |
| Hugging Face Transformers | Pre-trained transformer models ke saath kaam |

Official resources:
- NumPy: https://numpy.org/
- Pandas: https://pandas.pydata.org/
- Matplotlib: https://matplotlib.org/
- Scikit-learn: https://scikit-learn.org/
- PyTorch: https://pytorch.org/
- TensorFlow: https://www.tensorflow.org/
- Hugging Face: https://huggingface.co/docs/transformers/

## 8. AI project mein Python workflow

```text
Data collect
    ↓
Data load (Pandas)
    ↓
Data clean and prepare
    ↓
Explore / calculate (Pandas + NumPy)
    ↓
Train model (e.g. Scikit-learn)
    ↓
Evaluate model
    ↓
Use through application / API
    ↓
Monitor and improve
```

Har AI project mein exactly yehi tools ya sequence zaroori nahi hote; workflow project ke goal aur data ke hisaab se badalta hai.

## 9. Practical beginner project — Student result checker

```python
student_name = "Aman"
marks = [78, 82, 69, 90, 75]

average = sum(marks) / len(marks)

print("Student:", student_name)
print("Average:", average)

if average >= 40:
    print("Result: Pass")
else:
    print("Result: Needs improvement")
```

**Important:** Ye simple rule-based Python program hai, trained Machine Learning model nahi. Isse variables, lists, calculations aur conditions ki practice hoti hai.

## 10. Practice projects

1. Beginner: Calculator, marks calculator, expense tracker, quiz program.
2. Intermediate: CSV data analyzer, sales dashboard, spam-message classifier.
3. Advanced: Image classifier, text summarizer, AI chatbot, model-serving API.

Advanced project banane se pehle Python, data handling, model evaluation aur security basics samajhna zaroori hai.

## 11. Python learning roadmap

1. Syntax, variables aur data types.
2. Conditions, loops aur functions.
3. Lists, dictionaries aur strings.
4. Files, modules aur exception handling.
5. OOP, virtual environments aur package installation.
6. NumPy, Pandas aur Matplotlib.
7. Scikit-learn ke saath basic ML.
8. PyTorch ya TensorFlow ke saath deep learning basics.
9. APIs, testing, deployment aur monitoring.

## 12. Quick knowledge check

1. Python kya hai?
2. List aur dictionary mein kya difference hai?
3. Function ka main benefit kya hai?
4. Pandas ka use kis kaam mein hota hai?
5. Kya student result checker example ek trained ML model hai?

**Answer hints:** Programming language; ordered collection vs key-value structure; reusable code; data handling/analysis; nahi, woh rule-based program hai.

## 13. Chapter summary

- Python ek widely used programming language hai.
- Variables, data types, conditions, loops aur functions programming ke basics hain.
- OOP, files, modules aur exception handling larger projects mein useful hote hain.
- NumPy, Pandas, Scikit-learn aur PyTorch jaise tools AI workflows mein help karte hain.
- Python code likhna aur actual ML model train karna alag cheezein hain.

**Chapter 03 status:** Learning notes prepared and added to the repository.
