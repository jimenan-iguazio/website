+++
title = "MLRun Feature Store Overview"
description = "How to use the MLRun feature store"
weight = 10
                    
+++


The common flow to work with MLRun’s feature store is: 

1. Define the features, transformations, and validation logic
2. Ingest data (Dataframe, Kubernetes, Nuclio)
3. Create feature vectors for training
4. Serve models


### Define Features, Transformations, and Validation Logic

MLRun introduces a robust transformation engine that lets you perform complex operations in a few lines of Python code. 

To test the execution process, call the `infer` method with a sample DataFrame.  This runs all operations in memory without storing the results. 


### Ingest Data

MLRun allows you to ingest data directly from a DataFrame by calling the feature set `ingest` method. 

You can define an ingestion process that runs as a Kubernetes job. This is useful if there is a large ingestion process, or if there is recurrent ingestion and you would like to schedule the job.

MLRun can also leverage [Nuclio](https://nuclio.io) to perform real-time ingestion by calling the `deploy_ingestion_service` function. This function allows you to read and update feature values (e.g., you can update a sliding window aggregation as part of a model serving process). 

### Train Models

Define the feature vector by calling the `get_offline_features` function to join features across different feature sets.

Input `store://feature-vectors/{project}/{feature_vector_name}` to train a model with the feature vector data.

### Serve Models

Define a serving class derived from `mlrun.serving.V2ModelServer` .
 
In the class `load` method, call the `get_online_feature_service` function with the vector name. This will return a feature service object. 

In the class `preprocess` method, call the feature service `get` method to get the values of those features.

### Further Documentation

- [MLRun Documentation](https://docs.mlrun.org/en/latest/feature-store/feature-store.html)
- [Training & Serving](https://docs.mlrun.org/en/latest/feature-store/training-serving.html)
- [Feature Store End-to-End Demo](https://docs.mlrun.org/en/latest/feature-store/end-to-end-demo/index.html)