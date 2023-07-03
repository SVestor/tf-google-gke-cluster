# Google Kubernetes Engine (GKE) Cluster Terraform module

This module deploys a Kubernetes cluster on Google Cloud Platform (GCP) using the Google Kubernetes Engine (GKE) service. The GKE cluster is provisioned with a single node pool, and it comes with a generated Kubernetes configuration file (`kubeconfig`) that is stored locally.

## Usage

```terraform
module "gke_cluster" {
  source           = "https://github.com/SVestor/tf-google-gke-cluster?ref=gke-kbot"
  GOOGLE_REGION    = var.GOOGLE_REGION
  GOOGLE_PROJECT   = var.GOOGLE_PROJECT
  GKE_NUM_NODES    = var.GKE_NUM_NODES
  GKE_CLUSTER_NAME = var.GKE_CLUSTER_NAME
  GKE_MACHINE_TYPE = var.GKE_MACHINE_TYPE
}
```

## Inputs

|       Name       |            Description           |  Type  |     Default     | Required |
|:----------------:|:--------------------------------:|:------:|:---------------:|:--------:|
| GOOGLE_PROJECT   | GCP project name                 | string | no              |    no    |
| GOOGLE_REGION    | GCP region name                  | string | "us-central1-c" |    no    |
| GKE_MACHINE_TYPE | GKE node machine type            | string | "g1-small"      |    no    |
| GKE_NUM_NODES    | Number of nodes in the node pool | number | 2               |    no    |

## Outputs
kubeconfig - Generated Kubernetes configuration file

## Requirements
This module requires Terraform 0.12 or later, and the following provider:

hashicorp/google 4.52.0

## License
This module is licensed under the MIT License. See the LICENSE file for details.

[![infracost](https://img.shields.io/endpoint?url=https://dashboard.api.infracost.io/shields/json/8cf09eaf-8e9a-478b-89ae-fe701870135b/repos/dc30a3c6-a3ca-428b-accb-eeafdfeae2ca/branch/060cc73f-9fe6-4b9b-9362-2547ee3a421e/SVestor%252Ftf-google-gke-cluster)](https://dashboard.infracost.io/org/sasvestor/repos/dc30a3c6-a3ca-428b-accb-eeafdfeae2ca?tab=settings)
