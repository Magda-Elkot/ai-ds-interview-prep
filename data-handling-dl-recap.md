# Data Handling & Deep Learning Interview Recap

##  NumPy & Pandas: Your Data Toolkit

**NumPy** is for raw, fast numerical operations on arrays. **Pandas** is for practical data wrangling using DataFrames.

### Key Concepts

- **NumPy's `ndarray`**: The core object. Use it for **vectorized operations** (e.g., `arr1 + arr2`), which are way faster than Python loops.
- **Pandas' `DataFrame`**: The go-to for structured data. Think of it as a table in Python.

### Essential Commands

- **Load**: `pd.read_csv('file.csv')`
- **Inspect**: `df.head()`, `df.info()`, `df.describe()`
- **Clean**: `df.isnull().sum()` to find missing values, `df.dropna()` to remove them, `df.fillna(value)` to fill them.
- **Filter**: `df[df['col'] > 10]`
- **Group**: `df.groupby('category').mean()`

---

##  Deep Learning Intuition: The Training Flow

Don't get lost in the math. Explain the intuitive cycle: **predict, measure error, fix.**

### Core Components

- **Neurons**: The building blocks. A neuron takes inputs, applies a **weighted sum** and **bias**, and then passes the result through an **activation function** (like **ReLU**).
- **Weights & Biases**: The numbers the network learns. They are adjusted during training to improve predictions.
- **Loss Function**: Measures how wrong the prediction is. We want this to be as low as possible.
- **Optimizer**: The "fixer." It's the algorithm that adjusts the weights based on the error. **Adam** is a common choice.

### The Training Cycle (What to Say)

1.  **Forward Pass**: Data goes in, a prediction comes out.
2.  **Calculate Loss**: The prediction is compared to the true value to find the error.
3.  **Backpropagation**: The error signal travels backward through the network, telling each weight how much it contributed to the mistake.
4.  **Update Weights**: The optimizer uses that information to adjust the weights, so the next prediction will be better. This repeats for many **epochs**.

---

##  Interview Tip

When asked a question, don't just define the term. Explain its **purpose** and **how it fits into the workflow**. For example, don't just define NumPy; explain that it's for performance and vectorized operations. Don't just define backpropagation; explain that it's how the network learns from its mistakes.