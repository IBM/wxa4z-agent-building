# Access Windows ADK and Environment Overview

In order to execute the Lab exercises, there are two environments provisioned for you:
  - Windows VM
  - Z Dev & Test for z/OS (zD&T) 

The Windows VM is pre-configured with the **Agent Development Kit(ADK)** and all necessary tools to quickly get started with building your own agents. This is the environment you will be accessing for this Lab. 

You will not be accessing the **zD&T** environment directly, but rather using the environment details provided to you in order to connect your agents to it through the ADK. 

### Access the Windows VM

1. Click on the **Student URL** provided by the instructor for the **Windows ADK** environment, and when prompted, enter the password.

2. Once done, you should be taken to the environment details page for your **Windows ADK** environment.
   
   **IMAGE**


3. Open the Windows VM Console
   
    **IMAGE**

4. You should now see the Windows VM Desktop as shown below:
   
    **IMAGE**



### Tips for using the Windows VM



- re-format screen
- copy and paste
  - don't use the built-in 'Send Text' option
  - Rather, any commands or prompts needed are in a local .txt file on the Windows Desktop




### Windows VM Layout 



- VS Code with agent files pre-loaded in workspace
- Google Chrome opened with ADK/wxo UI and Lab Guide
- Notepad on desktop with zD&T env details, and text to help quickly copy and paste

### Verify whether ADK is configured 

Before moving on, verify that the ADK is successfully configured by running the following command in the **Terminal** of your VS Code window:

```
orchestrate agents list
```

It should return something similar to what's shown below:

**IMAGE**

If it is, you can proceed to the following section. 
If it's not, let an instructor know. 





**FLOW:**
As mentioned previously, the ADK environment has already been setup for you with all the agent configuration files. In this section you will access the ADK command-line and log into your environment.

```
orchestrate agents list
```


- How to access Windows VM
- Discuss layout of screens/windows
- Notepad on Desktop with the following:
  - zD&T env details
  - Agent instructions to copy and paste
  - commands?
- Have users verify whether ADK is configured
  - orchestrate agents list
  - If not, provide troubleshooting
- Describe steps to re-format screen, copy and paste, etc. 
- 