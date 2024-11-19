![Logo](https://miro.medium.com/v2/resize:fit:750/0*aIZxbsDU4eREgGf8.jpg)

### **Wazuh Docker Deployment**

This repository contains the necessary configuration and steps for deploying Wazuh in a Docker environment. Wazuh is a comprehensive security monitoring platform, and in this setup, we use Docker to simplify its installation and management for single-node deployment.

### **Features:**

- **Docker-based Deployment**: Easy-to-follow instructions for deploying Wazuh in a Docker container.
- **Single-node Setup**: Full installation with a single-node architecture for testing and development purposes.
- **Dashboard Access**: Secure and intuitive web-based dashboard to monitor and manage security alerts.

### **Installation Steps:**

1. **System Update**: Ensure your system is up to date.
    
    ```bash
    sudo apt update && sudo apt upgrade -y
    ```
    
2. **Clone the Wazuh Docker Repository**:
Clone the repository and checkout the appropriate version.
    
    ```bash
    git clone https://github.com/wazuh/wazuh-docker.git -b v4.9.1
    ```
    
3. **Install Docker Compose**:
Install Docker Compose for easier management of multi-container applications.
    
    ```bash
    sudo apt install docker-compose
    ```
    
4. **Generate Certificates**:
Navigate to the `single-node` directory and run the certificate generator.
    
    ```bash
    cd /wazuh-docker/single-node
    sudo docker-compose -f generate-indexer-certs.yml run --rm generator
    ```
    
5. **Start the Deployment**:
Use Docker Compose to start Wazuh in the foreground or background.
    
    ```bash
    sudo docker-compose up   # Foreground
    sudo docker-compose up -d # Background
    ```
    
6. **Access the Dashboard**:
Open your browser and go to `https://localhost:443`. The default login credentials are:
    - Username: `admin`
    - Password: `SecretPassword`

### **Notes**:

- This deployment is designed for development or testing environments. It is not intended for production use without further security hardening.
- For additional configurations or multi-node deployments, refer to the official [Wazuh documentation](https://wazuh.com/).
