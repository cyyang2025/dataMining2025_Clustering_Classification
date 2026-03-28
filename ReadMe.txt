================================================================================
K-MEANS CLUSTERING ANALYSIS / MULTI-CLASS CLASSIFICATION TASK
Data Mining HW2
================================================================================

PROGRAM OVERVIEW
================================================================================
This program is a 
(1)K-means clustering analysis experiments include:
1. scikit-learn (CPU-based) k-means experiments
2. cuML (GPU-based) k-means experiments
3. K-means analysis with fixed initial centroids
4. Number of clustering analysis (1-12 clusters)

and
(2)Multi-class classification task
1. Decision Tree classification experiments


SYSTEM REQUIREMENTS
================================================================================
- Python 3.x
- Execution Environment: Google Colab (Recommended for GPU support)
- Required Packages:
  - pandas
  - numpy
  - scikit-learn
  - cuML (GPU-based, requires RAPIDS)
  - matplotlib
  - cudf
  - cupy


DATA FILES REQUIRED
================================================================================
Place the following CSV files in the /content/ directory:

(1)K-means clustering analysis
1. 2025clustering.csv - Dataset for K-means experiments

(2)Multi-class classification task
2. hw2_tree_train.csv - Decision Tree training dataset
3. hw2_tree_test.csv - Decision Tree testing dataset


EXECUTION STEPS
================================================================================
PART 1: K-means clustering analysis
###############################

STEP 1: Environment Setup
----------------------------
1. Open Google Colab
2. Copy this program code to a Colab Notebook
3. Upload the required CSV data files to Colab environment
4. Execute the initialization code:
   
   !git clone https://github.com/rapidsai/rapidsai-csp-utils.git
   !python rapidsai-csp-utils/colab/pip-install.py

5. Import all required packages


STEP 2: Run Q1 - scikit-learn CPU K-means (Iterations 1-15)
----------------------------
Parameters: n_clusters=4, random_state=42, n_init=1
Run the section: "Q1. Using scikit-learn (cpu_based) to record SSE for iterations 1-15"

Expected Output:
- Table showing SSE values for each iteration
- Line chart: Iterations vs SSE

Important: Run this experiment twice with the same parameters to verify consistency


STEP 3: Run Q2 - cuML GPU K-means (Iterations 1-15)
----------------------------
Parameters: n_clusters=4, random_state=42, n_init=1
Run the section: "Q2. Using cuML (GPU_based) to record SSE for iterations 1-15"

Expected Output:
- Table showing SSE values for each iteration
- Line chart: Iterations vs SSE

Comparison: Compare results with Q1 to verify reproducibility with same random seed


STEP 4: Run Q3/Q4 - Fixed Initial Centroids
----------------------------
Parameters: n_clusters=4, random_state=42, n_init=1
Initial centroids from dataset rows: 10, 110, 1110, 1500
Run the section: "Q3, Q4 Using cuML (GPU_based) to record SSE for iterations 1-15 with fixed initial centroids"

Expected Output:
- Table showing SSE values for each iteration
- Line chart: Iterations vs SSE


STEP 5: Run Q5/Q6 - Cluster Size Analysis
----------------------------
For scikit-learn (CPU):
- Parameters: n_clusters=6, max_iter=999, random_state=42, n_init=1
- Initial centroids from dataset rows: 10, 50, 110, 1200, 1500, 1800
- Output: List cluster data point counts in descending order

For cuML (GPU):
- Same parameters as above
- Execute and compare cluster results between both packages


STEP 6: Run Q7/Q8- Number of clustering analysis (1-12 clusters)
----------------------------
For scikit-learn (CPU):
- Parameters: test k values from 1 to 12, random_state=42, n_init=1
- Output: SSE values for each k value
- Chart: k value vs SSE curve

For cuML (GPU):
- Use candidate initial center indices: 
  [390, 885, 923, 931, 1123, 1163, 1351, 1556, 1610, 1619, 1778, 1994]
- When clustering into k groups, use the first k indices as initial centers
- Parameters: max_iter=999, random_state=42, n_init=1
- Output: SSE values for each k value
- Chart: k value vs SSE curve


PART 2: Multi-class classification task
###############################

STEP 1: Environment Setup
----------------------------
1. Open Google Colab
2. Copy this program code to a Colab Notebook
3. Upload the required CSV data files to Colab environment
4. Import all required packages

STEP 2: Training
----------------------------
- Train multiple Decision Tree models (different max_depth and criterion)
- Evaluate accuracy on training and validation sets
- Select best model for test set prediction
- Output predictions to predictions.csv

================================================================================
Version: 1.0
Last Updated: 24 November 2025
================================================================================