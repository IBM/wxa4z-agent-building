# Deploy the zRAG Agent

Now you will deploy the zRAG Agent to your environment.

1. From the `deploy` directory, run the following command to deploy the **zRAG Agent**:
   
    ```
    ./deploy.sh up --profile zrag-external-agent
    ```

    At the end of the script's execution, you should see output similar to below:

    ```
    [+] up 2/2
    ✔ Image cp.icr.io/cp/ibm-watsonx-assistant-for-z/ibm-wxa4z-zrag-external-agent@sha256:334d6fa5331abc988f4f196bc156b334522981becc52994adbf7fa7... Pulled  0.5s
    ✔ Container wxa4z-zrag-external-agent                                  
    [2026-07-17T12:15:26Z] [INFO] Deployment complete
    ```

### Verify agent deployment 

Next, verify the successful deployment by checking the agent logs. From the same directory, run the following command to view the agent container logs:

```
docker logs wxa4z-zrag-external-agent
```

Towards the end of the logs, you should see output similar to what's shown below, indicating that the agent was successfully deployed:

```
2026-07-17 12:15:28,691 - server - INFO - zRAG agent initialized successfully
INFO:     Application startup complete.
INFO:     Uvicorn running on http://0.0.0.0:8000 (Press CTRL+C to quit)
```


### Activate Agent

Lastly, activate the agent within the **IBM watsonx Assistant for Z Management Console**. 

1. Log into the **Management Console** via web browser. 


2. Once logged in, click on the **ellipses** icon and select **Agents** from the drop-down:
   
    **IMAGE**
  

3. Next, locate the tile for the **zRAG Agent** and click on the gear icon as shown below:
   
    **IMAGE**

4. You should then see the **Agent Configuration** page:
   
    **IMAGE**

    Make the following changes to activate your agent:

    - `Connection`: Make sure the **zRAG Retriever Connection** is selected
    - `API Key`: enter the **AGENT_AUTH_TOKEN** value you set in the `Configure` section (i.e. zrag_auth)
    - `Status`: Toggle the status to **Active**

    Then click **Save**. 

    **IMAGE**

5. After activating, you should see the **zRAG Agent** tile with the **Active** flag:
   
    **IMAGE**

