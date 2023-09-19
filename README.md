# Secure Kubernetes Ingress with HashiCorp Boundary

## Usage 
The artifacts presented in this repository are provided in support of the blog post "Secure Kubernetes Ingress with HashiCorp Boundary".

The `build` directory contains the Containerfile to build the Boundary Worker container image.

The `deploy` directory contains the Kubernetes manifest required to deploy the Boundary Worker image. Note that the following information *must* be added to the Kubernetes manifest in order for the Boundary Worker to be deployed succesfully:

* `hcp_boundary_cluster_id` must be configured in the `boundary-enterprise-config` ConfigMap. This is the Cluster ID of the HCP Boundary cluster.
* `BOUNDARY_WORKER_ACTIVATION_TOKEN` must be configured as an environment variable within the `boundary-enterprise` StatefulSet. This value is derived from the Controller-Generated Activation Token, generated as part of the process of registering a new Boundary Worker using the Controller Led Authorisation Flow.



