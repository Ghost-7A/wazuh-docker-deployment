Wazuh Docker Deployment
This repository contains the necessary configuration and steps for deploying Wazuh in a Docker environment. Wazuh is a comprehensive security monitoring platform, and in this setup, we use Docker to simplify its installation and management for single-node deployment.

Features:
Docker-based Deployment: Easy-to-follow instructions for deploying Wazuh in a Docker container.
Single-node Setup: Full installation with a single-node architecture for testing and development purposes.
Dashboard Access: Secure and intuitive web-based dashboard to monitor and manage security alerts.
Installation Steps:
System Update: Ensure your system is up to date.

sudo apt update && sudo apt upgrade -y
Clone the Wazuh Docker Repository: Clone the repository and checkout the appropriate version.

git clone https://github.com/wazuh/wazuh-docker.git -b v4.9.1
Install Docker Compose: Install Docker Compose for easier management of multi-container applications.

sudo apt install docker-compose
Generate Certificates: Navigate to the single-node directory and run the certificate generator.

cd /wazuh-docker/single-node
sudo docker-compose -f generate-indexer-certs.yml run --rm generator
Start the Deployment: Use Docker Compose to start Wazuh in the foreground or background.

sudo docker-compose up   # Foreground
sudo docker-compose up -d # Background
Access the Dashboard: Open your browser and go to https://localhost:443. The default login credentials are:

Username: admin
Password: SecretPassword
Notes:
This deployment is designed for development or testing environments. It is not intended for production use without further security hardening.
For additional configurations or multi-node deployments, refer to the official Wazuh documentation.
