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

1. Similarly to what you did previously to active the zRAG Agent, navigate back to the **Management Console**, click on the **Agents** icon in the drop-down, and locate the tile for the **IBM Z OMEGAMON Insights Agent**.

    ![](_attachments/om1.png)

2. Click on the gear icon, then you should see the **Agent Configuration** page.

3. Make the following changes to activate your agent:
   
    - `API Key`: enter the **AGENT_AUTH_TOKEN** value you set in the `Configure` section (i.e. omegamon_auth)
    - `Status`: Toggle the status to **Active**

    Then click **Save**. 

    ![](_attachments/om2.png)

4. After activating, you should see the **IBM Z OMEGAMON Insights Agent** tile with the **Active** flag:
   
    ![](_attachments/om3.png)

