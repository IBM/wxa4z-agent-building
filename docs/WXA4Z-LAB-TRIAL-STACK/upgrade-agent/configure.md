# Configuration of IBM Z Upgrade Agent

1. Copy the example `.env` file in the `agents/upgrade-agent/` directory using the following command (assuming from the `/deploy` directory:

   ```
   cp agents/upgrade-agent/.env.agent.upgrade-agent.example \
   agents/upgrade-agent/.env.agent.upgrade-agent
   ```

2. Once done, edit the `.env.agent.upgrade-agent` file using `nano` or `vi` text editor. For example:

   ```
   nano agents/upgrade-agent/.env.agent.upgrade-agent
   ```

   For the **Upgrade Agent**, there are a set of environment variables that must be configured:

   - `AGENT_AUTH_TOKEN`
   - `ZOSMF_ENDPOINT`
   - `ZOSMF_USERNAME`
   - `ZOSMF_PASSWORD`
   - `HOST_NAME`
   

3. In the editor of the `.env.agent.upgrade-agent` file, locate the `AGENT_AUTH_TOKEN` environment variable and set it to a unique value (i.e. `upgrade_auth`). 
   
    ```
    AGENT_AUTH_TOKEN=upgrade_auth
    ```

    Make note on a notepad the value you set for the **Upgrade Agent** as this will be needed later.
  
4. Next, locate the environment variables for `ZOSMF_ENDPOINT`, `ZOSMF_USERNAME`, and `ZOSMF_PASSWORD` and set them to the following:
   
    - `ZOSMF_ENDPOINT`: `https://<zdt-ip>:10443/zosmf`, where `<zdt-ip>` should be replaced with the public IP of your zD*T environment
    - `ZOSMF_USERNAME`: `IBMUSER`
    - `ZOSMF_PASSWORD`: 

5. Finally, locate the environment variable for `HOST_NAME`. 
   
    Set this variable to `https://<linux-ip>:8443/agents/upgrade` where `<linux-ip>` should be replaced with the public IP address of your Linux environment. 


6. Finally, save the file in the text editor.


