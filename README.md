# Oracle-on-Kubernetes
**Oracle-On-Kunernetes** is a collection of example Kubernetes Manifest files to deliever Oracle on Kubernetes utilising Portworx storage


## Kubernetes Environment
The examples has been tested on Kubernetes v1.21 but should also work on more recent Kubernetes versions.

### You can check the version of Kubernetes using:
`
$ kubectl version --short | awk -Fv '/Server Version: / {print $3}'
`

## PortWorx Environment
To determine Portworx version use kubectl

`
$ kubectl get StorageCluster -A
`

### Use Portworx CLI pxctl
Alteratively use pxctl

`
export PX_POD=$(kubectl get pods -l name=portworx -n portworx -o jsonpath='{.items[0].metadata.name}')
alias pxctl='kubectl exec -n portworx ${PX_POD}  -it -- /opt/pwx/bin/pxctl'
$ pxctl -v
`

## Oracle Database Versions
Supported Oracle versions

1. Oracle 12.2.0.1 EE
1. Oracle 18.4.0.1 EX
1. Oracle 19.3.0.0 EE
1. Oracle 21.3.0.0 EE

## Getting Started

1. Install Portworx into your Kubernetes Cluster
1. Pull this Repo

### Create oracle-namespace
`
$ kubectl apply -f oracle-namespace.yaml
`
### Create Orcle Container Registry Secret
Logon to the Oracle Container Registry (OCR) using SSO credentials
`
$ kubectl create secret generic regcred --from-file=.dockerconfigjson=$HOME/.docker/config.json  --type=kubernetes.io/dockerconfigjson -n oracle-namespace
`
### Create ConfigMap
`
$ kubectl create configmap oradb --from-env-file=oracle.properties -n oracle-namespace
`
### Create Portworx Storage Class
`
$ kubectl apply -f px-ora-sc.yaml 
`
### Oracle 21c

`
$ kubectl apply -f 21c_statefulset_PX.yaml -n oracle-namespace
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

Oracle OTN (https://www.oracle.com/downloads/#category-database)

Oracle Container Registry (https://container-registry.oracle.com)

Oracle Docker GitHub Repo (https://github.com/oracle/docker-images)

Kubernetes CSI Docs (https://kubernetes-csi.github.io/docs/)

Portworx Docs (https://docs.portworx.com/)
