# Oracle-on-Kubernetes
**Oracle-On-Kunernetes** is a collection of example Kubernetes Manifest files to deliever Oracle on Kubernetes utilising Portworx storage


## Kubernetes Environment
The examples has been tested on Kubernetes v1.17 but should also work on more recent Kubernetes versions.


## Oracle Database Versions
1. Oracle 19.3.0 EE

## Getting Started

1. Install Portworx into Kubernetes Cluster
1. Pull this Repo
1. Vist my Blog and read relevant Oracle on Kubernetes posts 

### Examples
`
$ kubectl apply -f <mainfest>.yaml -n oracle-namespace
`

## Authors

Ron Ekins, Principal Solutions Architect, Office of the CTO at Pure Storage

Oracle ACE Director

@ronekins

## License

This module is available to use under the Apache 2.0 license, stipulated as follows:

Copyright 2018 Pure Storage, Inc.
Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at http://www.apache.org/licenses/LICENSE-2.0 Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on  an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.

## Link(s)

Oracle 19c on Kubernetes and Portworx storage (https://ronekins.com/2020/11/06/oracle-database-19c-on-kubernetes-with-portworx-storage/)

Protecting your Kubernetes Oracle database with Portworx Volume Group Snapshots (https://ronekins.com/2021/02/10/protecting-your-kubernetes-oracle-database-with-portworx-volume-group-snapshots/)


Oracle OTN (https://www.oracle.com/downloads/#category-database)

Oracle Container Registry (https://container-registry.oracle.com)

Oracle Docker GitHub Repo (https://github.com/oracle/docker-images)

Kubernetes CSI Docs (https://kubernetes-csi.github.io/docs/)

Portworx Docs (https://docs.portworx.com/)
