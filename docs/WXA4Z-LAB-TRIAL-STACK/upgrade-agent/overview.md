# IBM Z Upgrade agent

## Overview
The IBM Z Upgrade agent enables system programmers to perform z/OS upgrades through the Watsonx Assistant for Z chat interface. It provides precise responses by leveraging z/OSMF APIs and client-specific documentation stored in ZRAG.

**Deployment Architecture**: The agent uses the Model Context Protocol (MCP) architecture with separate client and server components for improved scalability and maintainability.

## Agent capabilities

| Agent capability         |            Description                  |
|------------------------------|-----------------------------------|
| Lists software products        | Provides a comprehensive list of software products for a given system    |
Lists software instance details | Shows detailed metadata of a given software instance such as its Name, Description, Global Zone, Target Zone, and so on.
Retrieves missing FIXCATs by software instance | Identifies missing FIXCAT Updates for specific software instances and systems.
Retrieves missing FIXCATs by software product | Identifies missing FIXCAT updates for software instances associated with the specified products and systems.
Retrieves missing CRITICAL updates by software instance | Identifies missing  CRITICAL Updates such as HIPERs and PEs for specific software instances and systems.
Acquires missing FIXCAT and CRITICAL updates | Retrieves the required PTFs for the specified RESOLVERS or FIXCAT names.
Monitors PTF acquisition job status| Tracks the progress and current status of background jobs initiated to acquire PTFs.
Installs the acquired PTFs | Begins the installation or update process for the requested PTFs.
Retrieves the installation or update status | Retrieves the status of installation or update processes using either the process ID or the names of the software instance and system.
Displays HOLD data | Shows HOLD data related to any unresolved HOLDS.
Resumes installation or update process | Continues the installation or update process if the user agrees to resolve all unresolved HOLDS.
Cancels the installation or update process | Cancels the installation or update process only upon user request.
Copies installation output | Copies the installation or update output, along with the process ID, to the user-specified UNIX path (e.g., /AQFT/tmp/smpe/).
Check hardware-compatibility for upgrade | Performs a check if the given system's hardware is compatible for an upgrade to a specified version
Retrieve Content from agent documentation stored in ZRAG |  Answers the upgrade workflow-related queries using the ingested docs for the agent.
