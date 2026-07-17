# Access the environment

## Access the Linux VM environment

- take note of your `linux-ip`

### Access the `deploy` directory

#### Record your **zDT** details

#### Record your **S3 bucket** connection details


## Access the IBM watsonx Assistant for Z Management Console

The **watsonx Assistant for Z Management Console** provides capabilities to activate agents, create agent connections, activate agents, and ingest content to be used in conversations. It also provides a front-end for testing your agent deployment. 

1. To access the **Management Console**, you have two options:

   - Option 1: Access externally on personal machine

   - Option 2: Access within the Linux VM

    **Option 1:**

    To access the Management console externally, navigate to the following URL in a web browser on your personal machine, replacing `<linux-ip>` with the Public IP address of your Linux VM:

    `https://<linux-ip>:8443`

    **Option 2:**

    - Navigate to the **VNC Desktop** for your Linux VM
    - Open up `https://localhost:8443`

2. Once at the login page, sign in using `wxa4z_creds` and enter your **Username** and **Password**.
   
    - `Username`: 
    - `Password`: 


3. After entering your credentials, click **Login** to access the console.


4. You should then see the **Chat** view of the Management Console. 
   
    **IMAGE**

    Keep this window open as you'll be using it later on in this Lab. 




