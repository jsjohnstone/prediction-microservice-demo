# prediction-microservice-demo
## AWS Playground: Containerized python flask app for predicting housing prices

Build Status: [![CircleCI](https://circleci.com/gh/jsjohnstone/aws-predictionmicroservice/tree/master.svg?style=svg)](https://circleci.com/gh/jsjohnstone/aws-predictionmicroservice/tree/master)

This project contains a Python Flash app with a machine learning model that has been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. 

You can read more about the data, which was initially taken from Kaggle, on the data source site:
https://www.kaggle.com/c/boston-housing 

The repository contains configuration and scripts to:
- build a Dockerfile
- upload this to the docker repo
- deploy the app using kubernetes
- ...and continuously test changes to this setup with CircleCI.

## Deploying the app

### Setup the Environment

* Create a virtualenv and activate it:
```
python3 -m venv ~/.predictionapp
source ~/.predictionapp/bin/activate
```
* Run `make install` to install the necessary dependencies

#### Running `app.py`

1. Standalone:  `python app.py`
2. Run in Docker:  `./run_docker.sh`
3. Run in Kubernetes:  `./run_kubernetes.sh`

#### Kubernetes Steps

* Setup and Configure Docker locally
* Setup and Configure Kubernetes locally
* Create Flask app in Container
* Run via kubectl


## Files
```
.
├── model_data/           # Prediction Model Data
├── output_txt_files/     # Output from running app in docker and kubernetes
├── Makefile              # Makefile configuration for building/testing the app
├── Dockerfile            # Docker configuration for building image
├── app.py                # Prediction application (Python Flask app)
├── make_prediction.sh    # Script that retrieves a prediction from running app instance
├── README.md             # This document :)
├── requirements.txt      # Environment requirements
├── run_docker.sh         # Script to build and run docker image
├── run_kubernetes.sh     # Script to run app on kubernetes cluster
└── upload_docker.sh      # Script to upload built docker image to Docker repo
```
