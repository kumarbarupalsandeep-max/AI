# Chapter 06 — Deep Learning

**Project:** Artificial Intelligence (AI) — Deep Research & Study Notes  
**Owner / Content Creator:** Sandeep Barupal  
**Copyright:** © 2026 Sandeep Barupal. Original explanatory notes; third-party names and trademarks belong to their respective owners.

## 1. Deep Learning kya hai?

Deep Learning, Machine Learning ka ek subset hai. Ismein multiple layers wale Artificial Neural Networks data se patterns aur representations seekhte hain. Ye images, audio, text aur complex data par useful ho sakta hai.

Example: Cat aur dog images ke examples se model visual patterns seekhkar nayi image classify kar sakta hai. Performance data quality, model design aur training par depend karti hai.

## 2. Neural Network kya hota hai?

Neural Network connected mathematical units (neurons) aur layers se bana model hota hai.

- **Input layer:** Data receive karti hai.
- **Hidden layers:** Data ke patterns learn karti hain.
- **Output layer:** Prediction ya final result deti hai.

Example: House price model mein inputs house size, rooms aur location-related features ho sakte hain; output estimated price ho sakta hai.

## 3. Artificial Neuron: weights, bias aur activation

Neuron inputs ko weights ke saath combine karta hai, bias add karta hai aur activation function apply karta hai.

```
z = w1*x1 + w2*x2 + ... + wn*xn + b
output = f(z)
```

- **Input (x):** Model ko milne wali value.
- **Weight (w):** Input ka learned influence.
- **Bias (b):** Additional adjustable parameter.
- **Activation (f):** Calculation ko transform karne wala function.

Weights aur bias training ke dauran update hote hain.

## 4. Activation functions

Activation functions network ko non-linear relationships learn karne mein help karte hain.

| Function | Simple explanation / common use |
|---|---|
| ReLU | Negative values ko zero karta hai; hidden layers mein common |
| Sigmoid | Output ko 0 aur 1 ke beech map karta hai |
| Tanh | Output ko -1 aur 1 ke beech map karta hai |
| Softmax | Multiple class scores ko probability-like distribution mein convert karta hai |

Softmax output ko automatically perfectly calibrated probability nahi banata.

## 5. Forward propagation

Forward propagation mein input layers se aage pass hota hai aur network prediction generate karta hai.

1. Input data receive hota hai.
2. Weights aur bias ke saath calculations hoti hain.
3. Activation functions apply hote hain.
4. Result next layer tak jata hai.
5. Output layer prediction deti hai.

## 6. Loss function

Loss function model prediction aur correct target ke beech error measure karta hai. Training ka goal chosen loss ko reduce karna hota hai.

| Loss | Common task |
|---|---|
| Mean Squared Error (MSE) | Regression |
| Mean Absolute Error (MAE) | Regression |
| Binary Cross Entropy | Binary classification |
| Categorical Cross Entropy | Multi-class classification |

## 7. Backpropagation

Backpropagation output loss se gradients calculate karne ka method hai. Ye gradients batate hain ki model parameters ko kis direction mein adjust karna useful ho sakta hai.

Training loop:
1. Forward pass se prediction.
2. Loss calculate.
3. Backpropagation se gradients.
4. Optimizer se weights update.
5. Multiple batches aur epochs tak repeat.

## 8. Gradient descent and optimizers

Gradient descent loss reduce karne ke liye parameters update karta hai.

```
new_weight = old_weight - learning_rate * gradient
```

Common optimizers:
- **SGD:** Gradient ke basis par parameter update.
- **Momentum:** Previous update direction ko use karke updates smooth kar sakta hai.
- **Adam:** Adaptive learning-rate estimates use karta hai.
- **RMSprop:** Adaptive optimizer.

Learning rate update step ka size control karta hai. Bahut high learning rate training unstable kar sakta hai; bahut low learning rate training slow kar sakta hai.

## 9. Epoch, batch aur iteration

| Term | Meaning |
|---|---|
| Epoch | Training dataset ka ek complete pass |
| Batch | Ek step mein process hone wala data group |
| Iteration | Ek batch par training/update step |

Agar 1,000 records aur batch size 100 hai, toh ek epoch mein 10 batches process honge, assuming all records use kiye ja rahe hain.

## 10. Deep Learning architectures

### ANN — Artificial Neural Network
General-purpose neural network. Tabular prediction aur classification jaise tasks mein use ho sakta hai.

### CNN — Convolutional Neural Network
Spatial patterns, especially images, process karne mein useful. Common flow: image input → convolution → pooling/feature processing → classification layers → output.

Applications: object recognition, image classification, quality inspection.

### RNN — Recurrent Neural Network
Sequential data process karne ke liye design hua. Sequence ke previous context ko next steps tak carry kar sakta hai. Long sequences par vanishing/exploding gradients ki problem aa sakti hai.

Applications: time-series aur sequence modelling.

### LSTM — Long Short-Term Memory
RNN ka special type hai. Gates ke through information retain ya forget karne ka mechanism provide karta hai.

### Transformer
Self-attention mechanism se sequence ke different parts ke relationships learn karta hai. Modern language models aur kai multimodal systems mein widely used hai.

| Architecture | Main focus |
|---|---|
| ANN | General input-output patterns |
| CNN | Spatial/image patterns |
| RNN | Sequential information |
| LSTM | Longer sequence dependencies |
| Transformer | Attention-based relationships |

Har Deep Learning model Transformer nahi hota.

## 11. Transfer Learning

Transfer Learning mein pehle se trained model ko related naye task ke liye reuse kiya jata hai.

Common approaches:
1. **Feature extraction:** Pretrained model ke learned features use karke naya task train karna.
2. **Fine-tuning:** Pretrained model ke kuch ya saare parameters ko naye data par further train karna.

Benefits mein training time aur required data/compute reduce hona shamil ho sakta hai. Result task aur dataset par depend karta hai.

## 12. Overfitting ko reduce karna

Overfitting tab hota hai jab model training examples ko bahut zyada fit ya memorize kar leta hai aur unseen data par weak perform karta hai.

Methods:
- Representative training data.
- Data augmentation.
- Dropout.
- Regularization.
- Early stopping based on validation performance.
- Proper train/validation/test separation.

## 13. Tools and frameworks

| Tool | Purpose |
|---|---|
| PyTorch | Neural networks build aur train karna |
| TensorFlow | Deep Learning development |
| Keras | High-level neural-network API |
| JAX | High-performance numerical computing |
| Hugging Face | Pretrained models aur AI development tools |
| CUDA | Supported NVIDIA GPUs par parallel computing |

Official resources:
- PyTorch Tutorials: https://pytorch.org/tutorials/
- TensorFlow Tutorials: https://www.tensorflow.org/tutorials
- Keras: https://keras.io/
- Hugging Face Docs: https://huggingface.co/docs
- NVIDIA CUDA: https://developer.nvidia.com/cuda-zone

## 14. Practical project — MNIST handwritten digit recognition

Goal: 28×28 pixel handwritten digit image se 0–9 digit classify karna. Example TensorFlow/Keras ka use karta hai.

### Step 1 — Imports

```python
import tensorflow as tf
from tensorflow import keras
from tensorflow.keras import layers
```

### Step 2 — Dataset load

```python
(x_train, y_train), (x_test, y_test) = keras.datasets.mnist.load_data()
```

### Step 3 — Normalize data

```python
x_train = x_train.astype("float32") / 255.0
x_test = x_test.astype("float32") / 255.0
```

### Step 4 — Build neural network

```python
model = keras.Sequential([
    layers.Input(shape=(28, 28)),
    layers.Flatten(),
    layers.Dense(128, activation="relu"),
    layers.Dropout(0.2),
    layers.Dense(10, activation="softmax")
])
```

### Step 5 — Compile

```python
model.compile(
    optimizer="adam",
    loss="sparse_categorical_crossentropy",
    metrics=["accuracy"]
)
```

### Step 6 — Train

```python
model.fit(
    x_train,
    y_train,
    epochs=5,
    batch_size=32,
    validation_split=0.1
)
```

### Step 7 — Evaluate

```python
test_loss, test_accuracy = model.evaluate(x_test, y_test)
print("Test Accuracy:", test_accuracy)
```

Ye actual neural-network training example hai. Exact test accuracy code run karne ke baad milegi; ek beginner dataset ka result real-world performance guarantee nahi karta.

## 15. Real-world applications

- Healthcare research: medical image analysis aur decision-support research; clinical use mein expert validation required hai.
- Automotive: road, vehicle aur pedestrian recognition.
- Speech: speech recognition aur audio processing.
- Manufacturing: visual defect detection aur quality inspection.
- Language: translation, summarization aur text processing.

## 16. Limitations and risks

1. Large aur representative datasets ki zaroorat ho sakti hai.
2. GPU/compute aur energy cost high ho sakti hai.
3. Training time-consuming ho sakti hai.
4. Kuch models explain karna difficult hota hai.
5. Biased data biased outputs produce kar sakta hai.
6. Overfitting aur unreliable predictions ka risk hota hai.
7. Data privacy aur model security important hain.

## 17. Knowledge check

1. Deep Learning kis ka subset hai?
2. Neural network ki three basic layer categories kaun si hain?
3. Backpropagation ka main role kya hai?
4. CNN kis type ke task mein commonly useful hai?
5. Transformer architecture kis mechanism ka use karti hai?

Answer hints: Machine Learning; input/hidden/output; gradients calculate karna; image/spatial processing; self-attention.

## 18. Chapter summary

- Deep Learning, Machine Learning ka subset hai.
- Neural networks mein neurons, layers, weights aur bias hote hain.
- Activation functions non-linear patterns learn karne mein help karte hain.
- Forward propagation prediction generate karta hai; backpropagation gradients calculate karta hai.
- Optimizers parameters update karte hain.
- ANN, CNN, RNN, LSTM aur Transformers different architectures hain.
- Transfer Learning pretrained models ko reuse karta hai.
- Data quality, compute, security aur evaluation important hain.

**Chapter 06 status:** Learning notes prepared and added to the repository.
