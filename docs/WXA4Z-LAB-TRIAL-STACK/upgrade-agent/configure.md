## Configuration of Upgrade Agent Agent

- navigate to `/stack/agents/upgrade-agent/`
- cp `.env-example` to `.env`
- edit the .env file
- Set the following env variables
  - `AGENT_AUTH_TOKEN`
  - HOST_NAME= https://<linux-ip>:8443/agents/upgrade
  - ZOSMF_ENDPOINT: https://<zdt-ip>:10443/zosmf
  - ZOSMF_USERNAME: IBMUSER
  - ZOSMF_PASSWORD: Password
