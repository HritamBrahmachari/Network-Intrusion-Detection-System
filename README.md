# Network Intrusion Detection using IBM AutoAI

This repository documents a project to build and deploy a machine learning model for network intrusion detection. The entire project was completed without writing any code, using the automated capabilities of IBM Watson Studio's AutoAI tool.

## Problem Statement

The challenge was to create a robust network intrusion detection system (NIDS) using machine learning.The system needed to be capable of analyzing network traffic data to distinguish between normal activity and various types of cyber-attacks.The goal was to build a model that could effectively secure communication networks by providing an early warning of malicious activities. 

The mandatory technology for this project was the use of IBM Cloud lite services. 

## Methodology: A No-Code Approach

This project utilized a no-code, cloud-based methodology to ensure rapid development and deployment. The core of the system is the **IBM AutoAI** tool, which automated the entire model-building process, from data preparation and feature engineering to model training and deployment.

### Tools Used

* **IBM Cloud**
* **IBM Watson Studio**
* **IBM AutoAI**

### Dataset

* **Name:** Network Intrusion Detection
* **Source:** The project used a dataset from Kaggle, as specified in the project requirements. 
    * **Link:** `https://www.kaggle.com/datasets/sampadab17/network-intrusion-detection` 
* **Description:** The dataset contains records of network connections, each with 41 features and a `class` label indicating if the traffic was `normal` or an `anomaly`.

## Steps to Replicate

1.  **Setup Project:** Create a new, empty project in IBM Watson Studio.
2.  **Upload Data:** Upload the `Train_data.csv` file from the Kaggle dataset as a data asset.
3.  **Create AutoAI Experiment:** Start a new AutoAI experiment.
4.  **Configure Experiment:**
    * Select the uploaded `Train_data.csv` as the data source.
    * Choose the `class` column as the **Prediction Column**.
    * Set the **Positive Class** to `anomaly` to optimize for attack detection.
5.  **Run Experiment:** Execute the experiment. AutoAI will automatically train several model pipelines.
6.  **Save Model:** From the results leaderboard, save the top-ranked pipeline as a new model asset.
7.  **Deploy Model:** Promote the saved model to a Deployment Space and deploy it as an **Online** web service.
8.  **Test API:** Use the "Test" tab in the deployment space to send sample JSON data to the model's API endpoint and verify it returns a prediction.

## Results

* The process successfully generated and deployed a real-time API for network intrusion detection.
* The top-performing algorithm selected by AutoAI was a **LightGBM Classifier**.
* The final deployed model was able to correctly receive new data and return a classification (`normal` or `anomaly`) with a corresponding confidence score, confirming the solution's functionality.
