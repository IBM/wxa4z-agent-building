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

```
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

1. Download .tar file from Github: https://ibm.ent.box.com/file/2385822506233
2. SCP it directly to Linux machine in user's /home directory
3. Untar it using `tar -xvf lite-stack.tar`
4. `cd lite-stack` - folder must be named `lite-stack`
5. Modify needed variables in `.env.core`:
  - 3 LLM variables - as well as LLM (either `openai/gpt-oss-120b` or `meta-llama/llama-3-3-70b-instruct`
6. Deploy core services using `./deploy.sh up --profile core --skip-aiops`
7. Ensure all core services come up successfully
8. Provide zD&T image details and COS bucket connection details with docs for ingestion pre-loaded & zD&T env details:
    - **URL**
    - **Access key id**
    - **Secret Access Key**
    - **Bucket name**
9. Finally, enable cockpit/Linux Web Console access using the below commands on Linux:
  - sudo dnf install cockpit -y
  - sudo systemctl enable --now cockpit.socket
  - Verify connectivity to `https://<public-ip>:9090
  - Log into web console using `itzuser` and password found in environment details
