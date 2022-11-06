# Kubeflow Pipeline demo

In this repo you can find the code for Demo on how to use Kubeflow pipelines in [Charmed Kubeflow](https://charmed-kubeflow.io/). The demo was executed on AWS EC2 instance.

## Prerequisites
You need to have a working instance on kubeflow. If you need help [here](https://www.youtube.com/watch?v=EuVanbpPIDc) is my YouTube tutorial on how to deploy Charmed Kubeflow on AWS EC2 instance (eta 30 mins).

This tutorial comes with example on how to use [MlFLow](https://mlflow.org/) as part of Kubeflow pipeline as a model registry. You can install the Charmed MlFlow along Kubeflow with following steps:
```
juju deploy mlflow-server
juju deploy charmed-osm-mariadb-k8s mlflow-db
juju relate minio mlflow-server
juju relate istio-pilot mlflow-server
juju relate mlflow-db mlflow-server
juju relate mlflow-server admission-webhook
```
You can find more info about Charmed MlFlow [here](https://github.com/canonical/mlflow-operator)

If you want you can install all the requirements from `requirements.txt`.
