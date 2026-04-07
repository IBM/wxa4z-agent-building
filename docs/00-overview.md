# Background and Lab Overview

**IBM® watsonx Assistant for Z** leverages generative AI solutions to simplify and optimize the way developers, operators, and programmers interact and manage the IBM Z® platform. A key part of the solution is a set of capabilities that enable conversational AI, featuring advanced agentic AI to drive greater productivity and operational efficiency. It provides intelligent, data-driven automation that understands conversational context and navigates complex, multi-step interactions.

## Key features of watsonx Assistant for Z agents

#### Foundational agentic framework
A scalable architecture designed to support the creation and management of AI agents across the mainframe ecosystem. It features multi-agent orchestration, enabling seamless collaboration between AI agents and assistants to automate complex workflows. The framework also provides an environment to run the agents and simplifies the deployment of pre-built watsonx Assistant for Z agents, IBM Z product agents, and custom third-party agents.

#### Agent integration services
Integration services allow agents to interact with the operating system or middleware to retrieve the data they need for making informed decisions. This includes support for integration with Model Context Protocol (MCP) servers, simplifying the process of importing external tools and extending the capabilities of your agents.

#### AI agent builder experience
The enhanced Agent Builder empowers teams to develop custom agents for a wide range of workflows from simple tasks to complex processes. It includes:

- A no-code interface for rapid creation of task-specific agents
- pro-code Agent Development Kit (ADK) for building advanced agent capabilities

#### Accelerated value with pre-built AI agents
Watsonx Assistant for Z includes a suite of pre-built AI agents and services, enabling teams to achieve immediate productivity gains. Customers also have the flexibility to create their own AI agents or leverage pre-built agents provided by IBM Z software products. These agents, embedded with AI chat capabilities, support decision-making and automate workflows using the watsonx Assistant™ for Z agentic AI framework. Developed across the IBM Z software stack, these agents offer an extensive set of capabilities to streamline operations and accelerate outcomes.

## Agent Development Kit (ADK)

Built on top of IBM watsonx Orchestrate, the watsonx Assistant for Z offering also enables flexible agent development for all users, empowering both business users and developers with a unified studio supporting low-code and pro-code development for key Z-specific use cases.

The **watsonx Orchestrate Agent Development Kit (ADK)** is a set of tools designed to make it easy to build and deploy agents. It is packaged as a Python library and command-line tool that allows builders to configure agents that run on the platform. The ADK also supports integrating agents and tools built on other frameworks.

The Agent Development Kit (ADK) is set of CLI utilities and python modules that helps you create agents and tools for watsonx Orchestrate.

The ADK also provides a framework for developers to easily define new tools and agents programmatically.

1. Tools are defined using one of the available binding types (Python, OpenAPI, MCP, etc.) and then imported into the Orchestrate platform using the Orchestrate CLI.

2. Agents are defined using the ADK and then imported into the Orchestrate platform using the Orchestrate CLI. Agents use the tools defined in step 1.

3. Once an agent is imported, it can be used to start conversations with users either through the Orchestrate Agent Chat UI or through the Orchestrate API.

For more information on the ADK, reference the ADK documentation **<a href="https://developer.watson-orchestrate.ibm.com/" target="_blank">here</a>**.


## Lab Overview

For this Hands-on Agent Builder Lab, you will build multiple agents augmented with tools for calling various z/OSMF REST API endpoints to assist in verifying the status and health of different z/OS components. 

You will first build an ***IPL Validator Agent*** using the **pro-code** ADK approach which has two different pre-defined tools available to it. 

Following the successful deployment and testing of this agent, you will then create a new Orchestrator Agent using the **low-code** approach which will enable multi-agent collaboration. This agent, named the **z/OS Helper Agent**, will collaborate with the previously created **IPL Validator Agent** as well as the **zRAG Agent** which is a pre-built agent included in watsonx Assistant for Z and is being made available to you as part of the Lab. 

This hands-on lab shows how easy it is to create your own agents for key IBM Z use cases, in addition to the set of pre-built Z agents that ship with the product.

The steps you will execute include:

- Installing and setting up your local ADK environment
- Configuring a connection and setting credentials
- Importing the provided tools
- Importing and testing the `IPL_Validator_Agent`
- Creating a custom `z/OS Helper Agent` which is an orchestrator agent with collaborator agents and additional tools


