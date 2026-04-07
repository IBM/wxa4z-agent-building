### Access the `IPL_Validator_Agent`

In this section, you will access your imported agent within your watsonx Orchestrate environment and test the agent’s execution flow. The scenario follows the following flow below, and the agent uses its two available tools to validate that your zOS system's configuration and subsystems are what you'd expect after an IPL.

***NOTE:*** **this step requires that you're already logged into your watsonx Orchestrate environment. You may have the UI already opened from earlier when retrieving your Service Instance URL. If so, you can skip steps 1-9 below.**

1. Click on the **Student URL** provided by the instructor for the **watsonx Orchestrate** environment and when prompted, enter the password. 

2. Once done, you should be taken to the environment details page for your **watsonx Orchestrate** environment.

3. As you will use **Student ID's** for accessing your cloud resource, firstly click on the **logout URL** referenced on the page:
    
    ![](_attachments/student1.png){width=50%}

    A pop-up window will open confirming you're logged out. You can then close that tab.

4. Navigate back to the environment details page, and record the **App ID User credentials** towards the bottom of the page. (Copy your **Username** and **Password** to a local notepad for reference). For example:
   
    ![](_attachments/student2.png){width=50%}

    In the above example, my Username would be `student0@techzone.ibm.com` and my Password would be `V14u8#CrmWittakd`. 

5. Then under the **App ID Instructions**, click on the `https://cloud.ibm.com/authorize/...` link in your environment details:
   
    ![](_attachments/student3.png){width=50%}

6. In the new tab, enter your recorded **Username** and **Password**, then click **Sign in**. 
   
    ![](_attachments/student4.png){width=50%}


7. Once logged in, navigate to the **Resource List** by clicking on the hamburger menu icon in the top-left corner and clicking on **Resources**. 
   
    ![](_attachments/student5.png){width=50%}

8. Expand the **AI / Machine Learning** section and you should see the following resources available:
   
    ![](_attachments/serviceurl2.png){width=50%}

9.  Click on the resource shown for the **watsonx Orchestrate** resource: 
    
    ![](_attachments/serviceurl2.png){width=50%}

10. Click **Launch watsonx Orchestrate**. 

    ![](_attachments/serviceurl3.png){width=50%}


11. Once you're logged into the **watsonx Orchestrate UI**, you may be taken to the **Chat** window. Click on the hamburger menu in the top-left corner and select **Build**. 
    
    ![](_attachments/test2.png){width=50%}

12. From there, you should see the list of all your existing agents. You should be able to see your **IPL_Validator_Agent** as shown below:
   
    ![](_attachments/test3.png){width=50%}

13. Click on your **IPL_Validator_Agent**. You'll then be taken to the Builder view for your agent, where you can see all the agent characteristics that were defined in your agent definition file, including the following:
   
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

#### **Step 1:** 
The agent calls the `operatorCommand` tool, passing `D IPLINFO` as input to the tool. The results should be displayed similarly to below:

![](_attachments/test8.png){width=50%}

#### **Step 2:** 
The agent calls the `tsoCommand` tool, passing `TIME` as the command input. This verifies that TSO is running. The output of that step should look like:

![](_attachments/test9.png){width=50%}

#### **Step 3:** 
The agent calls the `operatorCommand` tool, passing `D OMVS` as input:

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
