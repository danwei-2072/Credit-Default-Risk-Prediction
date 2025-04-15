# Credit Default Risk Prediction Using R

## Project Overview

This project aims to analyze the `Default` dataset from the `ISLR2` R package using R. It explores how customer account balance (`balance`) and income (`income`) affect the risk of credit card default (`default`). The project utilizes two primary classification models:

1.  **Logistic Regression**
2.  **Quadratic Discriminant Analysis (QDA)**

The analysis includes data visualization, model training, prediction evaluation (using confusion matrices and misclassification rates), and visualization of decision boundaries. Additionally, the project examines the impact of different prediction probability thresholds on model performance.

## Repository Files

*   `Credit Default Risk Prediction.Rmd`: The R Markdown source file containing all analysis code, visualizations, and textual explanations.
*   `Credit-Default-Risk-Prediction.pdf`: The final report generated from the `.Rmd` file.
*   `README.md`: This readme file.

## Data Source

The data used in this analysis comes from the `Default` dataset within the `ISLR2` R package. The main variables used include:

*   `default`: Whether the customer defaulted (Yes/No) - Response variable.
*   `student`: Whether the customer is a student (Yes/No) - *Note: This variable was removed at the beginning of the analysis.*
*   `balance`: Average credit card account balance.
*   `income`: Customer's annual income.

## Methodology

1.  **Environment Setup**: Load necessary R packages (`tidyverse`, `MASS`, `ISLR2`).
2.  **Data Loading and Preprocessing**: Load the `Default` dataset and remove the `student` column.
3.  **Exploratory Data Analysis (EDA)**: Visualize the relationship between `balance`, `income`, and the `default` status using `ggplot2`.
4.  **Data Splitting**: Randomly split the dataset into training (80%) and testing (20%) sets (`set.seed(1)` ensures reproducibility).
5.  **Logistic Regression Model**:
    *   Train a logistic regression model using the training set to predict `default` status (`default ~ balance + income`).
    *   Make predictions on the test set using a probability threshold of **0.5**. Calculate the misclassification rate and confusion matrix.
    *   Visualize the test data points and the decision boundary for a prediction probability of 0.5.
    *   Adjust the probability threshold to **0.1**, repeat the prediction and evaluation, and visualize the new decision boundary to observe the impact of the threshold change.
6.  **Quadratic Discriminant Analysis (QDA) Model**:
    *   Train a QDA model using the training set (`default ~ income + balance`).
    *   Make predictions on the test set using the QDA model.
    *   Visualize the test data points and the decision boundary corresponding to a QDA posterior probability of 0.1.
7.  **Results Discussion**: Analyze the model results and discuss the pros and cons of different models and thresholds.

## How to Run

1.  **Clone the Repository**:
    ```bash
    git clone https://github.com/danwei-2072/Credit-Default-Risk-Prediction.git
    cd Credit-Default-Risk-Prediction
    ```
2.  **Environment Setup**:
    *   Ensure you have R and RStudio installed (recommended).
    *   Open an R or RStudio console and install the required R packages:
        ```R
        # Uncomment and run if you haven't installed them yet
        # install.packages("tidyverse")
        # install.packages("MASS")
        # install.packages("ISLR2")
        # install.packages("rmarkdown")
        # If you need to generate PDF output, LaTeX is also required (tinytex recommended)
        # install.packages("tinytex")
        # tinytex::install_tinytex()
        ```
3.  **Run the Analysis**:
    *   Open the `Credit Default Risk Prediction.Rmd` file in RStudio.
    *   You can run the code chunks sequentially within the file.
    *   Alternatively, click the "Knit" button at the top of the RStudio editor to generate the complete HTML or PDF report.

## Dependencies

*   `tidyverse` (for data manipulation and visualization, includes `ggplot2`, `dplyr`, etc.)
*   `MASS` (for the QDA model)
*   `ISLR2` (provides the `Default` dataset)
*   `rmarkdown` (for generating the report)
*   `tinytex` (optional, for compiling Rmd to PDF)

## Ethical Considerations

The end of the report mentions several ethical considerations related to algorithmic decision-making:

*   **Data Privacy**: The data involved in training algorithms may contain sensitive personal information. Ensuring the confidentiality of this information and preventing data leakage is critical.
*   **Transparency**: The decision-making process of the algorithm should be transparent, especially for important decisions like loan or credit card applications. Customers have the right to know how decisions are made and based on what criteria.
*   **Accountability**: When an algorithm makes an error (e.g., incorrectly denying a credit application), there should be clear responsibility, procedures to correct errors, and remedies for affected individuals.
