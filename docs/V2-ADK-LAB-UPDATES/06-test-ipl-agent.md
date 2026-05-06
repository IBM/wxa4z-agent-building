### Access the `IPL_Validator_Agent`

In this section, you will access your imported agent within your watsonx Orchestrate environment and test the agent’s execution flow. The scenario follows the following flow below, and the agent uses its two available tools to validate that your zOS system's configuration and subsystems are what you'd expect after an IPL.

1. Minimize the VS Code window you've previously been working in, then open Google Chrome. 

    You should see a pre-opened tab with the **watsonx Orchestrate UI**. 

    ![](_attachments/win-test1.png)

2. Click on **Manage agents** to view your imported agent.

    ![](_attachments/win-test2.png)

3. From there, you should see the list of all your existing agents, including the **IPL_Validator_Agent** you previously imported:
   
    ![](_attachments/win-test3.png)

4. Click on your **IPL_Validator_Agent**. You'll then be taken to the Builder view for your agent, where you can see all the agent characteristics that were defined in your agent definition file, including the following:
   
    ***`Description`***
  
      ![](_attachments/test4.png){width=50%}
  
    ***`Agent style`***

  
      ![](_attachments/test5.png){width=50%}

    ***`Tools`***

      ![](_attachments/test6.png){width=50%}

    ***`Instructions`***

      ![](_attachments/test7.png){width=50%}

    
    Verify that your two tools exist and are available to your agent. 


### Test the `IPL_Validator_Agent`

Now you can test the execution flow of your agent. When the user prompts the agent to `run IPL check` or `validate my IPL` or something similar, the agent will kick off a series of steps as defined in the **Instructions** section of your agent definition. 

***In the agent chat window on the right-side of the screen, prompt the agent with `run IPL check`***. The agent will then call the appropriate tool according to the current step in the process. Wait until the agent processing is completed and the full output is returned. 

**Step 1:** The agent calls the `operatorCommand` tool, passing `D IPLINFO` as input to the tool. The results should be displayed similarly to below:

![](_attachments/test8.png){width=50%}

**Step 2:** The agent calls the `tsoCommand` tool, passing `TIME` as the command input. This verifies that TSO is running. The output of that step should look like:

![](_attachments/test9.png){width=50%}

**Step 3:** The agent calls the `operatorCommand` tool, passing `D OMVS` as input:

![](_attachments/test10.png){width=50%}

**Step 4:** The agent calls the `operatorCommand` tool, passing `D OMVS,MF` as input:

![](_attachments/test11.png){width=50%}


**Step 5:** The agent verifies if z/OSMF is running:

![](_attachments/test12.png){width=50%}

**Step 6:** The agent checks to see if JES is running by calling the `operatorCommand` tool, passing `$D JES2` as input. 

![](_attachments/test13.png){width=50%}

**Step 7:** The agent checks the status of JES2 by running the `operatorCommand` tool, passing `D A,JES2` as input:

![](_attachments/test14.png){width=50%}

**Step 8:** The agent then provides a summarized list of the previous checks, with an explanation:

![](_attachments/test15.png){width=50%}

***Congratulations! You've successfully imported and tested your first agent using the ADK with custom tools. In the following section, you will create a new custom agent using the 'low-code approach' which provides multi-agent orchestration, using other agents (including this one) as collaborators***
