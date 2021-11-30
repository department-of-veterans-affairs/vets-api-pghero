# vets-api-pghero
A repository for PgHero running on K8s


## Local setup
Prerequisites:
1. Kubernetes is running on your local machine 
	- MacOS: Check the Kubernetes box in Docker Desktop Preferences => Kubernetes => Enable Kubernetes
2. Install the Kubernetes command-line tool, `kubectl`
    *   See the [installation doc](https://kubernetes.io/docs/tasks/tools/) for your operating system.
3. Clone this repo locally

## Running via K8s locally
1. cd into the vets-api-pghero directory locally
2. run: `kubectl create configmap pghero --from-file=configmap/pghero.yml`
This will create a local configmap from the pghero.yml file
3. run: `kubectl get configmaps pghero -o yaml`
Run this to view the confimap in a yaml format
4. Launch the pod/create the deployment via: `kubectl apply -f pghero-pod.yml`
5. Run `kubectl get pods` to list the running pods
6. Local port fowarding: `kubectl port-forward name-of-your-pod-here 8080:8080`
7. Visit `localhost:8080` for the PgHero UI