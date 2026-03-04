Task 1 — Data Quality Issues

I inspected the dataset for common data quality problems by checking:

Data types (numeric vs categorical) using df.dtypes / df.info()

Missing values per column using df.isna().sum()

Duplicate rows using df.duplicated().sum()

Value ranges & summary stats for numeric columns using df.describe()
This helps detect issues like wrong datatypes, incomplete records, or unusual values.

Task 2 — Missing Value Strategy

I applied median imputation to a numeric feature (e.g., study_hours) using:
fillna(median)
Why median? The median is more robust than the mean when the data contains outliers or is skewed, so it avoids shifting values too much.

Task 3 — Outlier Detection & Handling (IQR)

For each numeric feature, I used the IQR method:

Compute Q1 and Q3

Compute IQR = Q3 − Q1

Outliers are values below Q1 − 1.5×IQR or above Q3 + 1.5×IQR
I handled outliers by clipping (winsorizing) them to the lower/upper bounds to reduce extreme impact while keeping the data size unchanged.

Task 4 — Normalization (Min-Max & Z-score)

To make features comparable (important for distance-based models and PCA), I normalized numeric columns using:

Min-Max Scaling: rescales values to [0, 1]

Z-score Standardization: converts to mean 0 and standard deviation 1
This prevents one feature with a larger scale from dominating others.

Task 5 — PCA (Dimensionality Reduction)

I applied PCA on standardized numeric features to reduce dimensionality while keeping most information.
I evaluated PCA using:

Explained variance ratio (how much variance each component explains)

Cumulative explained variance (how many components are needed to reach a target like 95%)
This helps understand how many principal components can represent the dataset effectively.
