# Intrusion Detection Using CIC-IDS2017 Dataset

## Dataset Overview
[CIC-IDS2017](https://www.unb.ca/cic/datasets/ids-2017.html) is a realistic network intrusion dataset containing both normal and attack traffic, including Brute Force, DoS, DDoS, Botnet, and Web Attacks.

- **Records**: 2,830,743  
- **Features**: 79 (78 numerical + 1 categorical)  
- **Imbalanced Dataset**: Majority class is "Benign"  

## Data Preprocessing
- **Handling Missing & Infinite Values**: Replaced infinities with NaN, filled missing values with median, and dropped duplicates.  
- **Encoding Labels**: Attack types were categorized and label-encoded.  
- **Feature Selection**: Removed low-variance and highly correlated features.  
- **Memory Optimization**: Reduced data type size, saving ~47.5% memory.  
- **Dimensionality Reduction**: Used PCA & Incremental PCA (IPCA) for efficiency.  

## Exploratory Data Analysis (EDA)
- **Attack Type Distribution**: Majority of instances are benign.  
- **Correlation Analysis**: Identified relevant features.  
- **Outlier Detection**: Used IQR method to analyze anomalies in attack types.  

## Anomaly Detection
### K-Means Clustering  
- **Optimal Clusters**: k=10 (Elbow Method, Silhouette Score).  
- **Anomaly Detection**: Points far from centroids were flagged.  
- **Accuracy**: Up to 82% with threshold tuning.  

### DBSCAN (Density-Based Clustering)  
- **Advantage**: No need to specify clusters.  
- **Evaluation**: Accuracy of 78%, detected outliers effectively.  

## Conclusion
- **K-Means & DBSCAN performed well but can be improved.**  
- **Future Work**: Use full dataset with parallel computing (e.g., Apache Spark, cloud solutions).  

