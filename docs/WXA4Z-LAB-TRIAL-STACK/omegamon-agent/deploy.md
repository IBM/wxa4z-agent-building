# Deploy the zRAG Agent

Now you will deploy the zRAG Agent to your environment.

1. From the `deploy` directory, run the following command to deploy the **OMEGAMON Insights Agent**:
   
    ```
    ./deploy.sh up --profile omegamon-insight-agent
    ```

    At the end of the script's execution, you should see output similar to below:

    ```
    [+] up 3/3
    ✔ Image cp.icr.io/cp/ibm-watsonx-assistant-for-z/wxa4z-aiops-agent@sha256:62445b790ad6c3cd981cccfdf5b50a40ba552469dfd5ea1423aa1afda6679011 Pulled   
    ✔ Volume wxa4z-agent-runtime-data
    ✔ Container wxa4z-omegamon-insight-agent                           
    [2026-07-17T12:51:31Z] [INFO] Deployment complete
    ```

### Verify agent deployment 

Next, verify the successful deployment by checking the agent logs. From the same directory, run the following command to view the agent container logs:

```
docker logs wxa4z-omegamon-insight-agent
```

Towards the end of the logs, you should see output similar to what's shown below, indicating that the agent was successfully deployed

```
INFO:     Started server process [1]
INFO:     Waiting for application startup.
2026-07-17 12:51:38,371 - aiops_agent.server - INFO - Skipping agent registration: TENANT_ID is not set
INFO:     Application startup complete.
INFO:     Uvicorn running on http://0.0.0.0:8050 (Press CTRL+C to quit)
```


### Activate Agent

Lastly, activate the agent within the **IBM watsonx Assistant for Z Management Console**. 

1. Log into the **Management Console** via web browser. 


2. Once logged in, click on the **ellipses** icon and select **Agents** from the drop-down:
   
    **IMAGE**
  

3. Next, locate the tile for the **IBM Z OMEGAMON Insights Agent** and click on the gear icon as shown below:
   
    **IMAGE**

4. You should then see the **Agent Configuration** page:
   
    **IMAGE**

    Make the following changes to activate your agent:

    - `API Key`: enter the **AGENT_AUTH_TOKEN** value you set in the `Configure` section (i.e. omegamon_auth)
    - `Status`: Toggle the status to **Active**

    Then click **Save**. 

    **IMAGE**

5. After activating, you should see the **IBM Z OMEGAMON Insights Agent** tile with the **Active** flag:
   
    **IMAGE**

