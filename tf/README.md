# Terraform description of main infrastructure

This directory manages the core infrastructure for running FarmDB and associated services for modelling and monitoring. 

The different environments can be managed through using terraform workspaces. 

Use a workspace called "dev" for the dev environment and "prod" for the prod environment respectively. All resources will be duplicated with respective name suffixes attached. 

### Sets up the following cloud resources:
- VPC
- Subnet
- Cloud SQL Instance
- Kubernetes

### Additionally configures:
- KSA - GSA pairing for cloud sql proxy
- K8s secret with database credentials
- ArgoCD


### Manual steps necessary: 
- Connect to DB using psql as postgres superuser and run (ssh into a cluster node or setup temporary VM in same VPC)
- CREATE EXTENSION postgis;
- CREATE EXTENSION postgis_topology;

