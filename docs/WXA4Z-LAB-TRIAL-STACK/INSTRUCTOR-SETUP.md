# INSTRUCTOR SETUP

- Setup:
  - provision the Linux VM and zDT from TZ
  - Copy the updated trial stack zip 
  - Install docker using below commands:
    
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

  - run `docker login cp.icr.io`
  - Deploy core services using: `./deploy.sh up --profile core --skip-aiops`
  - Provide COS bucket connection details with docs for ingestion pre-loaded:
    - **URL**
    - **Access key id**
    - **Secret Access Key**
    - **Bucket name**