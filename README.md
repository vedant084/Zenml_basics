# Basic ZenML SVC Pipeline

This repository demonstrates a simple machine learning pipeline using **ZenML** with an **SVC (Support Vector Classifier)** model. The pipeline covers the typical workflow of training and testing an SVC model using a dataset split into training and testing subsets.

---

## Project Structure

- **importer**  
  Loads the dataset and splits it into `x_train`, `y_train`, `x_test`, and `y_test`.

- **svc_trainer**  
  Trains an SVC model using the training data (`x_train`, `y_train`).

- **svc_tester**  
  Evaluates the trained SVC model on the test data (`x_test`, `y_test`) and outputs an evaluation metric (e.g., accuracy as a float).

---

## Pipeline Flow

```plaintext
importer
├── x_train (ndarray)
├── y_train (ndarray)
├── x_test  (ndarray)
└── y_test  (ndarray)
 
svc_trainer
├── Inputs: x_train, y_train
├── Output: trained SVC model

svc_tester
├── Inputs: trained SVC model, x_test, y_test
├── Output: float (accuracy or other evaluation metric)


<img width="1121" height="660" alt="Screenshot 2025-09-16 202409" src="https://github.com/user-attachments/assets/155b9dc4-254a-4fb2-ae8e-f578373e9135" />


