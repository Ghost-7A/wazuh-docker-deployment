# wazuh-docker-deployment
Step:1
```jsx
sudo apt update && sudo apt upgrade -y
```

Step:2

Clone the Wazuh repository to your system:
```jsx
//Check the latest version from wazuh officel document
git clone https://github.com/wazuh/wazuh-docker.git -b v4.9.1
```

Step:3

Install docker-compose
```jsx
sudo apt install docker-compose
```

Step:4

Generate certificates:
```jsx
//change the directory
cd /wazuh-docker/single-node

//Execute the following command to get the certificates:
sudo docker-compose -f generate-indexer-certs.yml run --rm generator
```

Step: 5

Start the Wazuh single-node deployment using docker-compose:
```jsx
//Foreground:
sudo docker-compose up

//Background:
sudo docker-compose up -d
```

Step: 6

Access the dashboard :
https://localhost:443 (By default wazuh dashboard use the port 443 )
Note: The default username and password for the Wazuh dashboard are `admin` and `SecretPassword`
