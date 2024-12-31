# Breast Cancer Classification Project (MAS8383)

A comprehensive statistical learning analysis of breast cancer diagnostic data using multiple methodologies: Exploratory Data Analysis (EDA), Hierarchical Clustering, K-means Clustering, and Classification Models. The project analyzes cytological characteristics from fine needle aspiration biopsies to distinguish between benign and malignant breast tissue samples.

## Project Overview
- Statistical analysis of breast cancer diagnostic data from Wisconsin
- Implementation of multiple clustering and classification approaches
- Comparative analysis of model performance
- Custom implementation of K-means algorithm

## Key Features
- Data preprocessing and exploratory analysis
- Multiple analytical approaches:
  - Hierarchical Clustering with different linkage methods
  - Principal Component Analysis (PCA)
  - Custom K-means implementation
  - Logistic Regression with subset selection
  - LASSO Regression
- Model diagnostics and validation
- Performance comparison and evaluation

## Repository Contents
- Project Requirement
- Raw data (from mlbench package)
- Project report with detailed methodology and findings
- R Markdown source files
- Presentation slides

## Technical Stack
### Core Technologies
- R Statistical Software (Version 4.x+)

### Key R Libraries
- `mlbench`: For breast cancer dataset
- `ggplot2`: For data visualization
- `glmnet`: For LASSO regression
- `MASS`: For stepwise regression
- `stats`: For hierarchical clustering
- `reshape2`: For data manipulation
- `knitr`: For report generation

### Statistical Methods & Techniques
- Hierarchical Clustering
  - Single-linkage
  - Complete-linkage
  - Average-linkage
- Principal Component Analysis
- K-means Clustering
- Logistic Regression
  - Subset Selection
  - LASSO Regularization
- Cross-validation

## Results & Findings
### Model Performance Comparison
- Subset Selection Logistic Regression:
  - Best performing model with 5.84% test error
  - Key predictors: Cl.thickness, Cell.shape, Marg.adhesion, Bare.nuclei, Bl.cromatin
  - Excluded Cell.size and Epith.c.size from final model
  - Selected as final classifier due to superior accuracy

- LASSO Regression:
  - Test error of 6.57%
  - Retained broader set of variables including Cell.size and Epith.c.size
  - Eliminated Mitoses through regularization
  - More complex despite LASSO's typical simplification tendency

### Clustering Insights
- Hierarchical Clustering:
  - Single-linkage showed sensitivity to outliers and chaining effect
  - Complete-linkage produced well-defined, compact clusters
  - Average-linkage offered balanced perspective with graduated cluster separation
  - Linkage method choice significantly impacted cluster structure

- K-means Analysis:
  - Custom implementation showed strong agreement with R's built-in function
  - Achieved consistent clustering with only 6 discrepant samples out of 683
  - Demonstrated impact of random initialization on final clusters
  - Highlighted importance of multiple runs for optimal clustering

### Principal Component Analysis
- First Principal Component (PC1):
  - Dominated by Cell.size, Cell.shape, and Bl.cromatin
  - Represented overall cell abnormality and chromatin patterns
  - Showed clear separation between benign and malignant classes

- Second Principal Component (PC2):
  - Strongly influenced by Mitoses
  - Contrasted cell division rate with nuclear/chromatin features
  - Provided complementary information to PC1
