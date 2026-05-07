
### Testing the `db2Command` tool

In this step of the scenario, you will firstly test the usage of the `db2Command` tool by adding **Instructions** that define the behavior of your agent. In order to test the agent's execution of the tool, you will add very simple instructions to ensure the tool works as expected and returns the relevant output. 

1. Scroll down to the **Behavior** section. In the **Instructions field**, copy and paste the following text:
   
    ```
    You are going to run various Db2 for z/OS commands using the tools you have available to issue DISPLAY commands via TSO/E REST API’s and return the command output back to the user. You will print out to the user what command you’re issuing and the full output of the command in a pretty format. ALWAYS INCLUDE THE FULL OUTPUT OF EACH COMMAND. 

    DO NOT GUESS. DO NOT SPECULATE. ONLY USE THE INFORMATION RETURNED FROM RUNNING YOUR TOOLS

    When the user asks to "get db2 details", use the "db2Command" tool, passing the "-DISPLAY GROUP" command as input. Then return the full output back to the user. 
    ```

    ![](_attachments/build9.png){width=50%}

    The purpose is to test that the `db2Command` tool works as expected.

2. Once done, click on the agent chat window on the right-side of the screen, and issue the prompt: `get db2 details`

    ![](_attachments/build10.png){width=50%}

3. Wait until the full output is returned. It should look something like this:
  
    ![](_attachments/build11.png){width=50%}

    In the output, it should show details about the Db2 for z/OS subsystem, including:

    - Current Function Level
    - Highest Activated Function Level
    - Subsystem ID
    - Status
    - Db2 Level
    - IRLM Proc

4. At the top of the response, click on **Show reasoning**, then **Step 1**. 
   
    Notice the tool that's listed (`db2Command`) and the **command** that was used as input (`-DISPLAY GROUP`).
    
    ![](_attachments/build12.png){width=50%}

    This command was of course hard-coded in the **Instructions** you used previously. But in the next section you will enable dynamic command inputs according to what the user would like to retrieve. 