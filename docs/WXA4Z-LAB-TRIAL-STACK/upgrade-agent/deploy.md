# Deploy the Upgrade Agent

Now you will deploy the Upgrade Agent to your environment.

From the `deploy` directory, run the following command to deploy the **Upgrade Agent**:
   
```
./deploy.sh up --profile upgrade-agent
```

At the end of the script's execution, you should see output similar to below:

```
[+] up 4/4
 ✔ Image cp.icr.io/cp/ibm-watsonx-assistant-for-z/upgrade-agent@sha256:86812e4b73759a64341d1d9c1faa0d4b23ee7c1a03fe6aae8be4203f1537be28 Pulled            0.8s
 ✔ Volume wxa4z-upgrade-agent-shared-data                                                                                               Created           0.0s
 ✔ Container wxa4z-upgrade-agent-mcp-server                                                                                             Healthy          31.0s
 ✔ Container wxa4z-upgrade-agent-mcp-client                                                                                             Started          31.2s
[2026-07-17T13:11:42Z] [INFO] Deployment complete
```

### Verify agent deployment 

Next, verify the successful deployment by checking the agent logs. From the same directory, run the following commands to view the agent container logs for the `mcp-client` and `mcp-server`:

```
docker logs wxa4z-upgrade-agent-mcp-client
```

Towards the end of the logs, you should see output similar to:

```
2026-07-17 13:12:03,776 - IBM_upgrade_agent_for_Z-zosmf_doc_ingestion - INFO - ✅ DOC INGESTION COMPLETED SUCCESSFULLY
2026-07-17 13:12:03,776 - IBM_upgrade_agent_for_Z-zosmf_doc_ingestion - INFO - ✅ DOC INGESTION COMPLETED SUCCESSFULLY
2026-07-17 13:12:03,776 - IBM_upgrade_agent_for_Z-zosmf_doc_ingestion - INFO - ===============================================================================
=
2026-07-17 13:12:03,776 - IBM_upgrade_agent_for_Z-zosmf_doc_ingestion - INFO - ===============================================================================
=
2026-07-17 13:12:03,776 - IBM_upgrade_agent_for_Z - INFO - Skipping agent registration: TENANT_ID not set
INFO:     Application startup complete.
```

Next, run:
```
docker logs wxa4z-upgrade-agent-mcp-server
```

Towards the end of the logs, you should see output similar to:

```
============================================================
  IBM Upgrade Agent - MCP Server
============================================================

------------------------------------------------------------
  Server Name: upgrade-agent-server
  Listening on: http://0.0.0.0:8001
  Transport: HTTP
  Tools Available: 20
  Auth Mode: basic
------------------------------------------------------------

INFO:     172.19.0.17:33902 - "POST /mcp HTTP/1.1" 200 OK
INFO:     172.19.0.17:33916 - "GET /mcp HTTP/1.1" 200 OK
INFO:     172.19.0.17:33932 - "POST /mcp HTTP/1.1" 202 Accepted
INFO:     172.19.0.17:33934 - "POST /mcp HTTP/1.1" 200 OK
2026-07-17 13:11:51,378 - mcp.server.lowlevel.server - INFO - Processing request of type ListToolsRequest
2026-07-17 13:11:51,398 - mcp.server.streamable_http - INFO - Terminating session: 18f4b6499213457992c77f4c720b70ca
INFO:     172.19.0.17:33950 - "DELETE /mcp HTTP/1.1" 200 OK
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

