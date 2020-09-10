# LAB: Google Cloud Fundamentals: Getting Started with GKE

## OBJECTIVES:
		*Provision a Kubernetes cluster using Kubernetes Engine.
		*Deploy and manage Docker containers using kubectl.

## STEPS:
		
	1. Confirm that needed APIs are enabled
	 --Set Project Core	
		gcloud config set project [YOUR_PROJECT_ID]
	 
	 --Get a list of services that you can enable in your project:
		gcloud services list --available ("If you don't see the Kubernetes Engine API or Container Registry API listed, that means you haven't been granted access to enable the API.")
		 Enable the service IF it isnt enabled:
		gcloud services enable [SERVICE_NAME]
	
	
	2. Start a Kubernetes Engine cluster
	 --place the zone you've been giving into an environment variable called MY_ZONE
		export MY_ZONE=us-central1-a
	 
	 --Start a Kubernetes cluster managed by Kubernetes Engine. Name the cluster webfrontend and configure it to run 2 nodes:
		gcloud container clusters create webfrontend --zone $MY_ZONE --num-nodes 2
	 
	 --After the cluster is created, check your installed version of Kubernetes using the kubectl version command:
		kubectl version
		("The gcloud container clusters create command automatically authenticated kubectl for you")
	 
	 --View your running nodes 
		kubectl get nodes
	 
	3.  Run and deploy a container
	 --launch a single instance of the nginx container. 	
		kubectl create deploy nginx --image=nginx:1.17.10
	 
	 --View the pod running the nginx container:
		kubectl get pods
	 
	 --Expose the nginx container to the Internet:	
		kubectl expose deployment nginx --port 80 --type LoadBalancer
	 
	 --View the new service:
		kubectl get services
	 
	 --Open a new web browser tab and paste your cluster's external IP address into the address bar
		Result: The default home page of the Nginx browser is displayed.
	 
	 --Scale up the number of pods running on your service:
		kubectl scale deployment nginx --replicas 3
	 
	 --Confirm that Kubernetes has updated the number of pods:	
		kubectl get pods
	 
	 --Confirm that your external IP address has not changed:
		kubectl get services	
		Return to the web browser tab in which you viewed your cluster's external IP address. Refresh the page to confirm that the nginx web server is still responding.

## End of lab:
		In this lab, you configured a Kubernetes cluster in Kubernetes Engine. You populated the cluster with several pods containing an application, exposed the application, and scaled the application.






















