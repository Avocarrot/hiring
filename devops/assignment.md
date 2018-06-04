{% include header.html %}
{% include online-assignment/intro.md %}

# Objective

You are a DevOps engineer working at an ad-tech company called Blue Banana.

The current CI/CD process automates the provision of services on virtual machines running some linux distribution.

Your team is eager to enter the world of containers, and you take the task of exploring Kubernetes as a possible solution.

You decide to make the first step with the deployment of the company's blog site, powered by Lobsters.

# Tasks

The assignment comprises two tasks.

| Task Objective | Expected Completion Time |
|---|---|
| [Task 1:](#task-1) Setup a local Kubernetes environment | ~30 minutes |
| [Task 2:](#task-2) Deploy and expose Lobsters on Kubernetes | ~60 minutes |

## Timing assumptions

The time estimates for the tasks above assume that you are familiar or have professional experience with Kubernetes and Docker.

## Task 1

You will need to deploy a functional Kubernetes cluster on your machine. The approach you take is up to you, but some are much more streamlined than others.

After being done, you should have a working cluster and be able to interact with the cluster via the `kubectl` command from a CLI.

As a rule of thumb, the command `kubectl get services --namespace kube-system` should return the provided kubernetes system services defined. The command
`kubectl get pods --all-namespaces` should return all pods running. For example:

```bash
$ kubectl get svc -n kube-system
NAME                   TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)         AGE
kube-dns               ClusterIP   10.96.0.10       <none>        53/UDP,53/TCP   1d
kubernetes-dashboard   NodePort    10.101.24.98     <none>        80:30000/TCP    1d
```

## Task 2

You will need to create the necessary definition files to have the Lobsters blog deployed on Kubernetes, including any dependencies it may require to run.

You are provided with Lobsters docker images [here](https://hub.docker.com/r/efthymiosh/lobsters/).

These images are built using the repository [here](https://github.com/jamesbrink/docker-lobsters) at the commit with SHA beginning with `d862967`.

You will find that you may configure the running container by having set some environment variables. A required subset would be:

  - MARIADB_HOST
  - MARIADB_PORT
  - MARIADB_PASSWORD
  - MARIADB_USER
  - LOBSTER_DATABASE
  - LOBSTER_SITE_NAME
  - RAILS_ENV
  - LOBSTER_HOSTNAME
  - VIRTUAL_HOST
  - RAILS_MAX_THREADS

You will need to install and expose the service on a kubernetes ingress controller.

After being done, your service should be accessible via `lobsters.local` on your local machine outside of the Kubernetes cluster.
A simple point to check would be the ability to successfully log-in.

# Deliverables

In your uploaded solution you should include:
1. The definition file(s) that you created for deploying the service and any dependencies on Kubernetes.
2. The definition file(s) that you created for exposing the service on your local machine.
3. Step-by-step instructions for deploying the stack you have defined, given a working Kubernetes cluster.
4. A `README.txt` file describing the rationale behind any interesting decisions you have taken, any work-arounds, and anything else you'd like to add about your solution.

**Note** Upload your solution as a valid `.tar.gz` or `.zip` file containing the deliverables.
