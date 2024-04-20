# GitLab CICD with Kubernetes
![GitLab_CICD](https://github.com/MdAhosanHabib/GitLab_CICD_1Test/assets/43145662/bdcda7b9-436e-4ab2-86b8-5b3bdb9aba2d)

## Installing GitLab:
Update System: Begin by updating the system packages using the package manager. For example, using dnf update -y.

Install Required Packages: Install necessary packages such as curl, openssh-server, policycoreutils-python-utils, perl, and postfix.

Start and Enable Services: Start and enable services like SSH and Postfix to ensure proper functioning.

Create GitLab Directory: Create a directory for GitLab installation, such as /gitlab.

Download GitLab Repository: Use curl to download the GitLab repository installation script and execute it.

Install GitLab: Install GitLab Community Edition (CE) using the downloaded repository.

Configure GitLab URL: Set the external URL for GitLab in the configuration file located at /etc/gitlab/gitlab.rb.

Reconfigure GitLab: Reconfigure GitLab to apply the changes made to the configuration file.

Reset Admin Password: Use gitlab-rake to reset the password for the admin user.

Verify Installation: Check the status of GitLab services using gitlab-ctl status and ensure that GitLab is accessible via the configured URL.


## Source Code & Image Push to GitLab:
Enable GitLab KAS: Enable GitLab Kubernetes Agent Server (KAS) by adding the configuration in gitlab.rb.

Initialize GitLab KAS: Initialize GitLab KAS by creating the necessary configuration file at k8s-conn with a blank.

Add Token: Add the token for Kubernetes Agent Server in the Kubernetes server.

Install Helm: Install Helm on the Kubernetes server and add the GitLab Helm repository.

Deploy GitLab Agent: Deploy GitLab agent in Kubernetes using Helm, specifying the necessary configurations.

Clone Repository: Clone the GitLab repository containing the source code and images.

Build and Push Images: Build Docker images for the source code and push them to the Docker registry configured in GitLab CI/CD.

## Deployment in Kubernetes:
Create Deployment YAML: Define a Kubernetes deployment YAML file (gittest_pod.yaml) specifying the deployment configuration, such as number of replicas, containers, and image.

Create Service YAML: Create a Kubernetes service YAML file (gittest_svc.yaml) defining the service configuration, such as type, ports, and selector.

Define CI/CD Stages: Define CI/CD stages in the GitLab CI/CD configuration file (.gitlab-ci.yml) such as build and deploy.

Build Docker Images: Use GitLab CI/CD pipeline to build Docker images, login to Docker registry, build images, and push them to the registry.

Deploy in Kubernetes: Use GitLab CI/CD pipeline to deploy the application in Kubernetes by configuring deployment and service using kubectl commands.

Verify Deployment: Verify the deployment by checking the status of pods and nodes in Kubernetes using kubectl commands.

