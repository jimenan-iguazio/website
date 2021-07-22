+++
title = "Feature Store End-to-End Demo "
description = "Demo: How to use the MLRun feature store step-by-step"
weight = 20
                    
+++

In this demo we will showcase:

- [Data ingestion & preparation](https://docs.mlrun.org/en/latest/feature-store/end-to-end-demo/01-ingest-datasources.html)

- [Model training & testing](https://docs.mlrun.org/en/latest/feature-store/end-to-end-demo/02-create-training-model.html)

- [Real-time data & model pipeline](https://docs.mlrun.org/en/latest/feature-store/end-to-end-demo/03-deploy-serving-model.html)

These steps are the first key steps in the MLRun architecture:

<img src="/docs//external-add-ons/feature-store/mlrun/images/end.png"
  alt="architecture steps"
  class="mt-3 mb-3 border border-info rounded">


### Patient monitoring example

In this demo we will learn how to *Ingest* different data sources to our *Feature Store*.

Healthcare facilities need to closely monitor their patients and identify early indicators for medical intervention. Time is a key factor, the earlier the medical teams can attend to an issue, the better the outcome. Therefore, an effective system with real-time alerts can save lives.

We will use encrypted COVID-19 treatment data from patients prior to their condition becoming severe or critical. Our medical dataset will include three types of data:

- *Healthcare systems*: Batch updated dataset, containing different lab test results (e.g., Blood test results).

- *Patient records*: Static dataset containing general patient details.

- *Real-time sensors*: Real-time patient metric monitoring sensor.

<img src="/docs//external-add-ons/feature-store/mlrun/images/end2png.png"
  alt="example graph"
  class="mt-3 mb-3 border border-info rounded">

We will walk through creation of ingestion pipeline for each data source with all the needed preprocessing and validation. We will run the pipeline locally within a notebook and then launch a real-time function to *ingest live data* or schedule a cron to run the task when needed.

Following the ingestion, we will create a feature vector and train several models using this vector. We will then deploy the model and showcase the feature vector and model serving. 

Visit the following links to see the step-by-step walk through this example:

- [Part 1: Data Ingestion](https://docs.mlrun.org/en/latest/feature-store/end-to-end-demo/01-ingest-datasources.html)

- [Part 2: Training](https://docs.mlrun.org/en/latest/feature-store/end-to-end-demo/02-create-training-model.html)

- [Part 3: Serving](https://docs.mlrun.org/en/latest/feature-store/end-to-end-demo/03-deploy-serving-model.html)



