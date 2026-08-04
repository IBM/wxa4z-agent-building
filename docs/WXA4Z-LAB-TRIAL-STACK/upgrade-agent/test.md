# Testing IBM Z Upgrade Agent

Finally, test the capabilities of the **IBM Z Upgrade Agent** by referencing the full list in the [Overview section](./overview.md).

The example prompts below are shown only for reference. Your results may differ. 

Questions:
- What are the steps to upgrade to z17?


### **Retrieve all software instance**:

`Show all software instances defined on my z/OS system`

![alt text](image.png)


### **Retrieve missing fixcats for a software instance**:

For example:

`Retrieve missing fixcats for software instance IMS on system VS01_003`

![alt text](image-1.png)

### **Fetch the latest status of missing FIXCAT retrieval**:

`What's the latest status on missing FIXCAT retrieval?`

![alt text](image-2.png)

### **Refresh HOLD DATA**

`Refresh HOLD DATA on software instance IMS on system VS01_003`

![alt text](image-3.png)

### **Get status of job**:

For example:

`What is the status of job JOB00062?`

![alt text](image-4.png)

*Continue checking status until the job successfully completes*.

### **Get refreshed list of missing FIXCATS**

For example:

`Retrieve missing fixcats for software instance IMS on system VS01_003`

### **Receive the missing PTFs for FIXCAT xxx**



### **Ask about upgrade workflow-related queries using the ingested docs**

`What are important considerations to make when upgrading to z17?`

![alt text](image-5.png)
