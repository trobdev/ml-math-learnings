# Machine Learning Foundations — From Scratch

A personal learning series built around understanding the mathematical and computational underpinnings of Machine Learning, written in plain Python wherever possible.  The goal is not to produce production-ready code, but to deeply understand *why* things work, not just *that* they work.  Each notebook introduces new concepts that build on the ones before it, working progressively toward a stronger foundation in the math and intuition behind modern ML systems.

---

## Philosophy

Most ML practitioners start with libraries like `scikit-learn`, `PyTorch`, or `TensorFlow` — and for good reason.  They are powerful tools that abstract away a lot of complexity.  But that abstraction also has a cost: it becomes easy to use a model without understanding what's happening beneath it.  

This series takes the opposite approach first.  By implementing core operations from scratch, the goal is to build up an honest mental model of ML mechanics — one that pays off as the work advances into deeper and more complex territory.  Libraries are introduced selectively, and only after the underlying concept has been worked out manually.

---

## Series Overview

The notebooks in this series are numbered and intended to be read in order.  Each one ends with a forward look at what's coming, and each one recaps what came before.  The series is ongoing, with more notebooks planned.

---

### 01 — Vectors and Similarity

**File:** `vectors_and_similarity.ipynb`

This is where the series begins, with the most fundamental building block in ML: the **vector**.  The notebook starts from first principles — what a vector is, what it measures, and how to work with it — and then moves toward a surprisingly practical application.

The core mathematical operations covered include vector addition, subtraction, scalar multiplication, dot products, norms (L2/Euclidean), and vector normalization.  Each is implemented by hand in Python using only built-in functionality.

The second half of the notebook applies these tools to a real problem: **text similarity using cosine similarity**.  A simple vocabulary is established, a handful of classic literary texts are tokenized and vectorized into sparse word-count embeddings, and a user query is ranked against them.  The results reveal both the power and the limitations of the bag-of-words approach — particularly its sensitivity to exact word matching (e.g., "storm" vs. "storms" yielding different rankings).

**Key concepts:** vectors, dot product, L2 norm, normalization, cosine similarity, sparse embeddings, bag-of-words, tokenization

---

### 02 — Matrices and Linear Models

**File:** `02_matrices_and_linear_models.ipynb`

Building directly on the vector work from Notebook 01, this notebook introduces **matrices** as organized collections of vectors — the standard way of representing datasets in ML, where rows are examples and columns are features.

After covering matrix structure, shape, and the conventions used throughout the literature (notably from Goodfellow, Bengio, and Courville's *Deep Learning*), the notebook implements core matrix operations from scratch: the **transpose**, **matrix-matrix multiplication** (built on top of dot products and the transpose), and **matrix-vector multiplication**.

The second half brings everything together into a **linear model**: $\hat{y} = Xw + b$ — the matrix form of the familiar $y = mx + b$.  A toy dataset is constructed around a lighthearted running race scenario (features: pizza slices eaten and hours slept), and predictions are generated and compared against true values using residuals.  The notebook closes with a side-by-side comparison of the hand-built model against `scikit-learn`'s `LinearRegression`, which produces identical results — a satisfying confirmation that the scratch implementation is sound.

**Key concepts:** matrices, shape, transpose, matrix multiplication, matrix-vector multiplication, linear models, weights, bias, residuals, scikit-learn

---

## What's Coming

This series is actively expanding.  Future notebooks will continue in the same spirit — building from scratch, introducing libraries as comparisons, and maintaining a focus on genuine understanding over shortcut fluency.  Topics currently planned or in progress include:

- **Linear Regression** — a deeper dive into fitting a model to data, including concepts like Gaussian elimination and least squares
- **Loss Functions and Optimization** — understanding how a model learns by minimizing error
- **Gradient Descent** — the mechanism behind model training, implemented step by step
- **More to follow** as the series develops

---

## Constraints and Conventions

- **Plain Python first.** Core operations are implemented without NumPy, pandas, or ML libraries.  This is intentional and foundational.
- **Libraries as comparisons.** When a library is introduced (e.g., scikit-learn, NumPy), it is used to validate or compare — not to replace the from-scratch work.
- **Annotated math.** LaTeX is used throughout to express formulas clearly alongside their Python implementations.
- **Cited sources.** References are included where concepts are drawn from specific texts.

---

## References

The series draws on the following foundational texts:

Goodfellow, I., Bengio, Y., & Courville, A. (2016). *Deep learning*. MIT Press.

Johnston, N. (2021). *Introduction to linear and matrix algebra*. Springer. https://njohnston.ca/publications/introduction-to-linear-and-matrix-algebra

Pedregosa, F., Varoquaux, G., Gramfort, A., Michel, V., Thirion, B., Grisel, O., Blondel, M., Prettenhofer, P., Weiss, R., Dubourg, V., Vanderplas, J., Passos, A., Cournapeau, D., Brucher, M., Perrot, M., & Duchesnay, E. (2011). Scikit-learn: Machine learning in Python. *Journal of Machine Learning Research, 12*, 2825–2830. https://scikit-learn.org/stable/modules/linear_model.html
