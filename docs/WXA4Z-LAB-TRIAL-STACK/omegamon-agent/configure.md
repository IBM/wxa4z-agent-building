# Configuration of IBM Z OMEGAMON Insights Agent

1. Copy the example `.env` file in the `agents/omegamon-insight-agent/` directory using the following command (assuming from the `/deploy` directory:

   ```
   cp agents/omegamon-insight-agent/.env.agent.omegamon-insight.example \
   agents/omegamon-insight-agent/.env.agent.omegamon-insight
   ```

2. Once done, edit the `.env.agent.omegamon-insight` file using `nano` or `vi` text editor. For example:

   ```
   nano agents/omegamon-insight-agent/.env.agent.omegamon-insight
   ```

   For the **OMEGAMON Insights Agent**, most of the configuration is done already via the core services, including the AIOps server to connect to SMU. The only required environment variable for the Agent is the `AGENT_AUTH_TOKEN` variable.

3. Locate the  `AGENT_AUTH_TOKEN` variable in the `.env.agent.omegamon-insight` file and set a unique value (i.e. `omegamon_auth`).

   ```
   AGENT_AUTH_TOKEN=omegamon_auth
   ```

4. Make note on a notepad the value you set for the **OMEGAMON Insights Agent** as this will be needed later.


5. Finally, save the file in the text editor.




