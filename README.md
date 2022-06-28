# SPIFFE CSI Driver Example

This example follows the blog post on the SPIFFE CSI Driver on [kusari.dev](https://www.kusari.dev/blog/spiffee-csi/).

## Prerequisites

- A running Kubernetes cluster (Docker Desktop Kubernetes, k3d, minikube)
- [Kubectl](https://kubernetes.io/docs/tasks/tools/#kubectl)

## Steps

1. Deploy SPIRE and the SPIFFE CSI Driver (which resides in the same DaemonSet as the SPIRE Agent):

    ```
    $ ./deploy-spire-and-csi-driver.sh
    ```

2. Check the workload logs to see the update received over the Workload API:

    ```
    $ kubectl logs pod/client
    ```

    You should see something like:

    ```
    2021/11/23 18:46:33 Update:
    2021/11/23 18:46:33   SVIDs:
    2021/11/23 18:46:33     spiffe://example.org/workload
    2021/11/23 18:46:33   Bundles:
    2021/11/23 18:46:33     example.org (1 authorities)
    ```
