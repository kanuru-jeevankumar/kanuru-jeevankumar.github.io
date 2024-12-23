---
sidebar_position: 1
---
# Install single node mongo

Label the node where you want to run the container `kubectl label nodes quixydevops minio-node=true`

All the required configurations are defined here, you can use them for deploying the minio single in the same order as defined below

1. [Minio Single NodeNamespace](https://bitbucket.org/quixydev/quixy-devops/src/main/minio-single-node/minio-single-node/Namespace.yaml)
2. [Minio Single NodePV](https://bitbucket.org/quixydev/quixy-devops/src/main/minio-single-node/minio-single-node/PersistentVolume.yml) 
3. [Minio Single NodePVC](https://bitbucket.org/quixydev/quixy-devops/src/main/minio-single-node/minio-single-node/PersistentVolumeClaim.yml) 
4. [Minio Single NodeSecret](https://bitbucket.org/quixydev/quixy-devops/src/main/minio-single-node/minio-single-node/Secrets.yml) 
5. [Minio Single NodeDeployment](https://bitbucket.org/quixydev/quixy-devops/src/main/minio-single-node/minio-single-node/Deployment.yml) 
6. [Minio Single NodeService](https://bitbucket.org/quixydev/quixy-devops/src/main/minio-single-node/minio-single-node/Service.yml)
