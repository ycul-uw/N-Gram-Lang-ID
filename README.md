# N-Gram Language Models for Language Identification

_Author: Lucy Wu_

_Date: 03/12/2025_

## Description

This repository contains three different implementations of bigram-based language models used for language identification. The models predict the probability of a given sentence belonging to a specific language **(English, French, or Italian)** using different smoothing techniques:

### **1. Letter-based Bigram Model with Add-One Smoothing**

- This model constructs bigrams at the **letter level** and applies **Add-One (Laplace) Smoothing**.
- It is useful for handling small datasets or languages with rich morphology but struggles with capturing meaningful word dependencies.

### **2. Word-based Bigram Model with Add-One Smoothing**

- This model constructs bigrams at the **word level** and applies **Add-One (Laplace) Smoothing**.
- It improves over the letter-based model by capturing word relationships but suffers from overestimating unseen words.

### **3. Word-based Bigram Model with Good-Turing Smoothing**

- Similar to the word-based model but uses **Good-Turing Smoothing** instead of Add-One.
- This method effectively redistributes probability mass, improving predictions for unseen bigrams and achieving the highest accuracy.

## How to Run

### **Prerequisites**

Ensure you have Jupyter Notebook installed or clone the repository in Visual Studio Code along with the following dependencies:

```bash
pip install numpy jupyter
```

### **Steps to Run**

1. Navigate to the `src/` directory:
   ```bash
   cd src
   ```
2. Navigate to the `Code/` directory:
   ```bash
   cd Code
   ```
3. Open the desired notebook and run the cells:
   - **Letter-based model**: `letterLangId.ipynb`
   - **Word-based Add-One model**: `wordLangId.ipynb`
   - **Word-based Good-Turing model**: `wordLangId2.ipynb`

- Models will be trained using the datasets in `src/Data/Input`.
- Outputs will be automatically placed in `src/Data/Output`
- Evaluate of the predictions/accuracy of each model is displayed at the end of each model files.

### **Example Usage**

1. Open `wordLangId.ipynb` in Jupyter Notebook.
2. Modify the file paths to point to your training and test datasets.
3. Run all the cells to train and evaluate the model.

## Notes

- The training data should be in plain text format with properly tokenized words.
- The models output log probabilities for classification.
- Good-Turing smoothing provides the best accuracy but is computationally heavier.