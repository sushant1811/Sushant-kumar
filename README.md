# Exploratory Data Analysis on School Dataset (1993–1998)

## Project Overview

This project presents an end-to-end Exploratory Data Analysis (EDA) of a school dataset covering the period from 1993 to 1998.

The primary objective is to investigate school-related variables, understand their distributions, identify relationships between academic performance and school characteristics, and apply statistical and machine learning techniques to discover meaningful patterns.

The project progresses through data preprocessing, exploratory visualization, statistical analysis, clustering, dimensionality reduction, and predictive modelling.

## Dataset

- **Dataset:** School Data (1993–1998)
- **Source:** [School Dataset – GitHub](https://raw.githubusercontent.com/salemprakash/EDA/main/Data/school93_98.csv)
- **Initial Dataset Dimensions:** 10,668 rows × 19 columns

### Important Features

| Feature | Description |
|---|---|
| `lunch` | Lunch-related variable |
| `enrol` | Student enrolment |
| `exppp` | Expenditure per pupil |
| `math4` | Mathematics score |
| `year` | Academic year |
| `rexpp` | Related expenditure measure |
| `found` | School-related funding information |
| `lenrol` | Log-transformed enrolment |
| `lrexpp` | Log-transformed expenditure |
| `lavgrexpp` | Log-transformed average expenditure measure |

## Technologies Used

- **Language:** Python
- **Environment:** Google Colab / Jupyter Notebook
- **Data Manipulation:** Pandas, NumPy
- **Visualization:** Matplotlib, Seaborn
- **Statistical Analysis:** SciPy
- **Machine Learning:** Scikit-learn

## Project Workflow

### 1. Data Loading and Preprocessing

The initial stage focuses on preparing the dataset for analysis.

- Importing required Python libraries.
- Loading the dataset from GitHub.
- Exploring dataset dimensions, data types, and descriptive statistics.
- Identifying and handling missing values.
- Detecting and removing duplicate records.
- Applying Min-Max scaling to numerical features.

### 2. Exploratory Data Analysis (EDA)

#### Univariate Analysis

Examines individual variables to understand their distributions and characteristics.

- Histogram of mathematics scores (`math4`).
- Boxplot of student enrolment (`enrol`).
- Histogram of the lunch variable (`lunch`).

#### Bivariate Analysis

Investigates relationships between pairs of variables.

- Student enrolment versus mathematics scores.
- Mathematics scores across academic years (1993–1998).
- Expenditure per pupil versus mathematics scores using regression visualization.

#### Multivariate Analysis

Explores relationships between multiple variables simultaneously.

- Correlation heatmap of numerical features.
- Pair plot of `math4`, `enrol`, `exppp`, and `lunch`.
- Combined scatterplot using enrolment, mathematics scores, academic year, and expenditure per pupil.

### 3. Statistical Analysis

The project performs statistical analysis at three levels.

#### One-Dimensional Analysis

Nine numerical variables are examined using:

- Mean, median, and mode.
- Variance and standard deviation.
- Minimum, maximum, and quartiles.
- Interquartile range.
- Skewness and kurtosis.
- Histograms with KDE curves and boxplots.

#### Two-Dimensional Analysis

Relationships between numerical variables are investigated using:

- Covariance matrix.
- Pearson correlation.
- Spearman correlation.
- P-value and statistical significance analysis.
- Correlation heatmap.
- Pairwise scatterplots with regression lines.

Five selected variable relationships are studied in detail, including enrolment versus mathematics scores, expenditure versus mathematics scores, and lunch versus mathematics scores.

#### Three-Dimensional Analysis

Three important variables are analysed together:

- Expenditure per pupil (`exppp`).
- Student enrolment (`enrol`).
- Mathematics score (`math4`).

Descriptive statistics, correlation analysis, and a 3D scatterplot are used to investigate their combined relationships.

### 4. K-Means Clustering

K-Means is implemented as an unsupervised learning technique to group observations based on similarities.

**Selected Features:**

- `lunch`
- `enrol`
- `exppp`
- `math4`
- `rexpp`

**Implementation:**

- Feature standardization using StandardScaler.
- Elbow Method to examine the appropriate number of clusters.
- Silhouette Score for cluster evaluation.
- Final K-Means model training.
- Cluster size and average feature analysis.
- 2D and 3D cluster visualizations.

### 5. Hierarchical Clustering

Hierarchical Clustering is implemented to investigate how observations can be grouped based on their similarity.

**Implementation:**

- Uses the same five numerical features as K-Means.
- Standardizes the selected features.
- Uses a random sample of up to 500 observations for computational and visualization efficiency.
- Applies Ward's linkage method.
- Generates a dendrogram to visualize hierarchical relationships.
- Applies Agglomerative Clustering.
- Evaluates clusters using the Silhouette Score.
- Visualizes clusters through 2D and 3D scatterplots.

### 6. Principal Component Analysis (PCA)

PCA is applied to reduce dimensionality while retaining as much information as possible from the original numerical features.

**Selected Features:** Nine numerical variables, including `lunch`, `enrol`, `exppp`, `math4`, `rexpp`, `found`, `lenrol`, `lrexpp`, and `lavgrexpp`.

**Implementation:**

- Reloading the original dataset.
- Handling missing values using median imputation.
- Standardization using StandardScaler.
- Applying Principal Component Analysis.
- Calculating explained variance ratios.
- Generating a Scree Plot.
- Generating a Cumulative Explained Variance Plot.
- Identifying the number of components required to retain at least 80% cumulative variance.
- Visualizing observations using the first two principal components.
- Analysing PCA component loadings.

### 7. Simple Linear Regression

Simple Linear Regression is implemented to investigate the relationship between the lunch variable and mathematics scores.

**Variables:**

- Independent Variable (X): `lunch`
- Dependent Variable (Y): `math4`

**Implementation:**

- Loading the original dataset separately.
- Selecting the required variables.
- Handling missing observations.
- Pearson correlation analysis.
- 80:20 train-test split.
- Training a Linear Regression model.
- Regression line visualization.
- Model evaluation.
- Residual analysis.

**Correlation Result:**

Pearson correlation coefficient: approximately **-0.4795**.

**Regression Equation:**

\[
\widehat{math4} = 73.8546 - 0.4110(lunch)
\]

**Model Performance:**

| Evaluation Metric | Result |
|---|---:|
| R² Score | 0.2213 |
| RMSE | 18.8332 |
| MAE | 15.2638 |

The negative regression coefficient indicates an inverse association between the lunch variable and predicted mathematics scores.

The R² score indicates that the model explains approximately 22.13% of the variation in mathematics scores on the test dataset.

These results represent statistical associations and should not be interpreted as evidence of causation.

## Project Structure

```text
Sushant-kumar/
│
├── EDA_phase1.ipynb
│
└── README.md
```

## How to Run

1. Clone the repository:

```bash
git clone https://github.com/sushant1811/Sushant-kumar.git
```

2. Navigate to the project directory:

```bash
cd Sushant-kumar
```

3. Install the required dependencies:

```bash
pip install pandas numpy matplotlib seaborn scipy scikit-learn
```

4. Open `EDA_phase1.ipynb` using Jupyter Notebook or Google Colab.

5. Execute the notebook cells sequentially to reproduce the analysis and visualizations.

The dataset is loaded directly from its public GitHub raw URL.

## Key Learning Outcomes

- Data cleaning and preprocessing.
- Exploratory data visualization.
- Descriptive and correlation-based statistical analysis.
- Univariate, bivariate, and multivariate analysis.
- 1D, 2D, and 3D statistical analysis.
- Unsupervised learning using K-Means and Hierarchical Clustering.
- Dimensionality reduction using PCA.
- Predictive modelling using Simple Linear Regression.
- Model evaluation and residual analysis.

## Conclusion

This project demonstrates a complete analytical workflow for exploring school-related data.

By combining statistical methods, visualization techniques, clustering algorithms, dimensionality reduction, and regression modelling, the project investigates patterns and relationships among school characteristics and academic performance.

It also demonstrates the practical application of Python-based data analysis and machine learning techniques to a real-world dataset.

## Author

**Sushant Kumar**

[GitHub Profile](https://github.com/sushant1811)
