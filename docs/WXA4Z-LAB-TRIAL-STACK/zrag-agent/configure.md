## Configuration of zRAG Agent

1. Copy the example `.env` file in the `agents/zrag-external-agent/` directory using the following command (assuming from the `/deploy` directory:

   ```
   cp agents/zrag-external-agent/.env.agent.zrag-agent.example \
   agents/zrag-external-agent/.env.agent.zrag-agent
   ```

2. Once done, edit the `.env.agent.zrag-agent` file using `nano` or `vi` text editor. For example:

   ```
   nano agents/zrag-external-agent/.env.agent.zrag-agent
   ```

   For the **zRAG Agent**, most of the configuration is done already via the core services. The only required environment variable for the zRAG Agent is the `AGENT_AUTH_TOKEN` variable.

3. Locate the  `AGENT_AUTH_TOKEN` variable in the `.env.agent.zrag-agent` file and set a unique value (i.e. `zrag_auth`).

   ```
   AGENT_AUTH_TOKEN=zrag_auth
   ```

4. Make note on a notepad the value you set for the **zRAG Agent** as this will be needed later.

   Finally, save the file in the text editor.


