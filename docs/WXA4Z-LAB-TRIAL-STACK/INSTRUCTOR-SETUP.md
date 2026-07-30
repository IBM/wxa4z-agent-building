# INSTRUCTOR SETUP


  - provision the Linux VM and zDT from TZ
  
## Install docker using below commands:
    
```
sudo dnf remove -y podman buildah docker docker-client docker-client-latest docker-common docker-latest docker-latest-logrotate docker-logrotate docker-engine runc
```

```
sudo dnf install -y dnf-plugins-core
```

```
sudo dnf config-manager --add-repo https://download.docker.com/linux/rhel/docker-ce.repo    
```

```
sudo dnf install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

```
sudo systemctl enable --now docker
```

```
sudo usermod -aG docker $USER    
```

```
newgrp docker
```

## Enable networking to cp.icr.io

``
sudo cp /etc/resolv.conf /etc/resolv.conf.bak

echo -e "nameserver 8.8.8.8\nnameserver 1.1.1.1" | sudo tee /etc/resolv.conf

sudo chattr +i /etc/resolv.conf
```

Verify it's working:

```
curl -v https://cp.icr.io/v2/
```

Then login:
```
docker login cp.icr.io
```

# setup `lite-stack` folder

- use updated version in git
- tar it locally
- scp it to the linux vm
- untar it from there (no unzip)

  - Deploy core services using: `./deploy.sh up --profile core --skip-aiops`
  - Provide COS bucket connection details with docs for ingestion pre-loaded & zD&T env details:
    - **URL**
    - **Access key id**
    - **Secret Access Key**
    - **Bucket name**
