# AKS-using-helm-gitlabCICD-gitlabregistry
deploying Helm Charts on a Kubernetes cluster using GitLab CI/CD pipelines and Gitlab registry for storing image and creating kube config file for context creation
# GitLab CI/CD Pipeline for Kubernetes Deployment using Helm Charts 
This guide will walk you through the process of setting up a GitLab CI/CD pipeline to deploy your application to a Kubernetes cluster using Helm charts. 
## Prerequisites
1. Two GitLab projects: - `k8s-helm-data`: Contains your application code and GitLab CI pipeline configuration. - `k8s-helm-connection`: Contains the Kubernetes cluster connection configuration and Helm chart definitions. 2. Access to a Kubernetes cluster, such as AKS (Azure Kubernetes Service), with `kubectl` and `helm` configured.
2.  ## Steps
3.  ### 1. Configure Kubernetes Cluster Connection 1. In the `k8s-helm-connection` project, add the Kubernetes cluster connection details. 2. Generate a `kubeconfig` file with appropriate permissions to access the Kubernetes cluster. 3. Test the connection using `kubectl` commands to ensure proper connectivity.
4.   ### 2. Prepare Application Image 1. Build your application Docker image. 2. Push the Docker image to the GitLab Container Registry. - Ensure that you have appropriate permissions to push images to the registry.
5.    ### 3. Create Helm Charts 1. Define Helm charts for your application in the `k8s-helm-connection` project. 2. Include necessary Kubernetes manifests, such as Deployment, Service, ConfigMap, etc., in the Helm chart templates.
6.  ### 4. Publish Helm Charts 1. Publish Helm charts to a Helm repository. 2. Ensure that the Helm repository is accessible by the GitLab CI/CD pipeline.
7.  ### 5. Configure GitLab CI/CD Pipeline 1. In the `k8s-helm-data` project, create or update the `.gitlab-ci.yml` file to define the CI/CD pipeline. 2. Configure stages and jobs for building, testing, and deploying the application. 3. Utilize GitLab CI/CD variables to store sensitive information such as Kubernetes cluster credentials and Helm repository details.
8.  ### 6. Deploy to Kubernetes using CI/CD 1. Configure the CI/CD pipeline to trigger deployment to the Kubernetes cluster upon successful build and testing. 2. Use `kubectl` commands or Helm CLI to apply changes to the Kubernetes cluster.
9.  ### 7. Monitor Deployment 1. Monitor the CI/CD pipeline execution for any errors or failures. 2. Verify successful deployment by checking the status of Kubernetes resources using `kubectl` commands or Kubernetes dashboard. ## Additional Considerations - Ensure proper RBAC (Role-Based Access Control) permissions are set up for accessing the Kubernetes cluster from the CI/CD pipeline. - Implement automated tests within the CI/CD pipeline to validate application functionality before deployment. - Use GitLab's environment and review features to manage different deployment environments and review changes before promoting to production.



###            https://www.youtube.com/watch?v=qSbE7NOXm8U
