# ListeriaFoodEnvironment

🥬 This dataset contains the location, soil properties, climate, and land use for each soil sample tested for Listeria species. 

📖 This dataset is sourced from the publication "**Liao, J., Guo, X., Weller, D.L. et al. Nationwide genomic atlas of soil-dwelling Listeria reveals effects of selection and population ecology on pangenome evolution. Nat Microbiol 6, 1021–1030 (2021). https://doi.org/10.1038/s41564-021-00935-7**". 
Please cite this paper when using this dataset.
# Listeria Food Environment Analysis

## Overview

This project utilizes machine learning algorithms to analyze and predict Listeria contamination in food environments. Aimed at food safety researchers and public health officials, it provides a comprehensive toolkit for understanding patterns of Listeria outbreaks and formulating preventive measures. 

## Installation

To get started with this project, follow these steps:

1. Clone the repository:

```bash
git clone https://github.com/FoodDatasets/ListeriaFoodEnvironment.git
cd ListeriaFoodEnvironment
```
2. Install the required Python packages:
```bash
pip install -r requirements.txt
```

## Supported Algorithms
1. logistic_regression: Logistic Regression
2. neural_network: Neural Network
3. decision_tree: Decision Tree
4. svm: Support Vector Machine
5. knn: K-Nearest Neighbors
6. gbm: Gradient Boosting Machine
## Dependencies
This project is built using Python and relies on several libraries for data processing and machine learning:  
1.Pandas  
2.Numpy  
3.Scikit-learn  
4.Keras  
5.TensorFlow  
# Machine Learning Model Execution Guide

This script allows users to select different machine learning algorithms via command line parameters to train models and evaluate them on a specified dataset.

## How to Run

Use the following command line format to run this script:
```bash
python ml_algorithms_runner.py --file_path <path_to_your_data.csv> --algorithm <algorithm_name> [options]

```
### Parameter Explanation
- `--file_path` (required): The path to your CSV file.
- `--algorithm` (required): The algorithm to use. Options include `logistic_regression`, `neural_network`, `decision_tree`, `svm`, `knn`, `gbm`.

#### Optional Arguments
- `--test_size`: The proportion of the dataset to include in the test split (default: 0.2).
- `--random_state`: The seed used by the random number generator (default: 42).
  
##### For the Neural Network algorithm, you can also specify:
- `--nn_epochs`: The number of epochs for training (default: 100).
- `--nn_batch_size`: The batch size during training (default: 10).
- `--nn_layers`: The number of hidden layers (default: 2).
- `--nn_neurons`: The number of neurons per hidden layer (default: 64).
 
##### Logistic Regression Specific Arguments
- `--lr_C`: Inverse of regularization strength; must be a positive float. Smaller values specify stronger regularization (default: 1.0).
- `--lr_penalty`: Specifies the norm used in the penalization (default: 'l2').

##### Decision Tree Specific Arguments
- `--dt_max_depth`: The maximum depth of the tree. If None, then nodes are expanded until all leaves are pure or until all leaves contain less than min_samples_split samples (default: None).
- `--dt_min_samples_split`: The minimum number of samples required to split an internal node (default: 2).

##### SVM (Support Vector Machine) Specific Arguments
- `--svm_C`: Regularization parameter. The strength of the regularization is inversely proportional to C. Must be strictly positive (default: 1.0).
- `--svm_kernel`: Specifies the kernel type to be used in the algorithm (default: 'rbf').

##### KNN (K-Nearest Neighbors) Specific Arguments
- `--knn_n_neighbors`: Number of neighbors to use for kneighbors queries (default: 5).
- `--knn_metric`: The distance metric to use for the tree (default: 'minkowski').

##### GBM (Gradient Boosting Machine) Specific Arguments
- `--gbm_learning_rate`: Learning rate shrinks the contribution of each tree by learning_rate. There is a trade-off between learning_rate and n_estimators (default: 0.1).
- `--gbm_n_estimators`: The number of boosting stages to be run (default: 100).

Additional optional arguments are available for other algorithms. Refer to the script's help for more details:
```bash
python ml_algorithms_runner.py --help
```
### Usage Example

To run a Neural Network algorithm on data.csv with 3 hidden layers, each with 32 neurons, for 50 epochs and a batch size of 16:
```bash
python ml_algorithms_runner.py --file_path data.csv --algorithm neural_network --nn_epochs 50 --nn_batch_size 16 --nn_layers 3 --nn_neurons 32
```

To run a Logistic Regression on your_data.csv with a regularization strength of 0.5 and using L1 penalty:
```bash
python ml_algorithms_runner.py --file_path your_data.csv --algorithm logistic_regression --lr_C 0.5 --lr_penalty l1

```
Adjust the above commands according to your actual file paths and parameters.

# Performance of Various Models on the Dataset

| Algorithm              | Epochs | Positive-Negative Ratio | Accuracy | Precision | Recall | F1 Score |
|------------------------|--------|------------------------|----------|-----------|--------|----------|
| Neural Network         | 100    | 1.263 (139/110)        | 0.811    | 0.848     | 0.806  | 0.827    |
| Logistic Regression    | -      | 1.263                  | 0.747    | 0.767     | 0.784  | 0.776    |
| SVM (Support Vector Machine) | - | 1.263                | 0.731    | 0.734     | 0.813  | 0.771    |
| KNN (k-Nearest Neighbors)    | - | 1.263                | 0.707    | 0.736     | 0.741  | 0.738    |
| Gradient Boosting Classifier | - | 1.263                | 0.811    | 0.723     | 0.922  | 0.810    |
| Decision Tree              | -  | 1.263                | 0.807    | 0.819     | 0.849  | 0.834    |

# Confusion Matrix Results for Various ML Algorithms

The following table details the confusion matrix results for each machine learning algorithm tested. These results provide insights into each model's ability to correctly predict the true positives and true negatives, as well as the instances of false positives and false negatives.

| Algorithm | True Negatives | False Positives | False Negatives | True Positives |
|-----------|----------------|-----------------|-----------------|----------------|
| Neural Network | 90 | 20 | 27 | 112 |
| Logistic Regression | 77 | 33 | 30 | 109 |
| SVM (Support Vector Machine) | 69 | 41 | 26 | 113 |
| KNN (k-Nearest Neighbors) | 73 | 37 | 36 | 103 |
| Gradient Boosting Classifier | 84 | 26 | 21 | 118 |
| Decision Tree | 90 | 20 | 28 | 111 |

*Note: These results are indicative of the model's performance on the dataset, reflecting the balance between sensitivity (recall) and specificity.*


<img src="ml_algorithms_performance_curve_vivid.png" width="600">
<img src="ml_algorithms_confusion_matrix.png" width="600">

# LazyPredict Method
## Prerequisites

- Python 3.6 or higher
- Required Python packages (can be installed using `pip`):
``` bash
pip install pandas scikit-learn matplotlib lazypredict
```

## Usage
``` bash
python name.py --file_path /path/to/your csv --test_size 0.2 --random_state 42
```
### Command-line Arguments
- `--file_path`: Path to the CSV file containing the dataset (required).
- `--test_size`: Fraction of the dataset to be used as the test set (default is 0.2).
- `--random_state`: Random seed for reproducibility (default is 42).

## Example Output
### Model Performance Table

![Model Performance Table](Images/model_performance_table.png)

### Model Accuracy Comparison

![Model Accuracy Comparison](Images/model_performance_bar.png)


