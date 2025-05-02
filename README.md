# Geospatial Clustering Using DBSCAN
Overview
This project demonstrates the use of the DBSCAN (Density-Based Spatial Clustering of Applications with Noise) algorithm to identify clusters and outliers in geospatial data. Specifically, it analyzes incident types (e.g., Beaver Accident, Latte Spills, Seal Attack, etc.) using their Latitude and Longitude coordinates. DBSCAN is particularly effective in this context due to its ability to identify clusters of varying shapes and to detect noise (outliers).

### Data
The dataset (rev_data_for_test.csv) contains 1,514 records with the following fields:

Type: Type of event/incident

Latitude: Latitude of the event location

Longitude: Longitude of the event location

Report Location: String representation of coordinates

### Dependencies
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- Install them with:
- pip install pandas numpy matplotlib seaborn scikit-learn

### Steps and Logic
1. Data Loading and Exploration
   
Load the CSV file and inspect the types and distribution of incidents.

Visualize class distribution with a bar chart and plot all points on a scatter plot.

2. Data Preparation
Extract latitude and longitude into a NumPy array.

Normalize features using StandardScaler to improve DBSCAN performance.

3. Clustering with DBSCAN
Train a DBSCAN model with:

eps = 0.25 (radius)

min_samples = 12 (minimum points to form a dense region)

Assign cluster labels, where -1 indicates outliers.

4. Result Interpretation
Count number of clusters and outliers using Counter.

Visualize the clusters and noise:

Cluster points are color-coded.

Outliers are shown in black.

5. Evaluation
Use Silhouette Score to measure clustering quality:

Value near +1 indicates dense and well-separated clusters.

Value near 0 indicates overlapping clusters.

### Key Outputs
Number of clusters: 4

Number of outliers: 60

Silhouette Score: ~0.47 (moderate clustering quality)

### Visualizations
Count Plot: Distribution of incident types.

Scatter Plot: Raw geospatial data.

DBSCAN Clusters: Clustered locations with outliers highlighted.

Seaborn Pairplot: Geographic separation of event types.

### Conclusion
DBSCAN effectively identified meaningful clusters and detected spatial outliers from geospatial event data. This approach can be applied to various location-based use cases such as anomaly detection, urban planning, or incident management.
