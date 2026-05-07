# Azure AI Agents and MCP Server Hosting Samples

This repository contains sample code that demonstrates how to host **AI agents** and **Model Context Protocol (MCP) servers** on **Microsoft Azure infrastructure** for a variety of real-world use cases and deployment scenarios.

The goal of this repo is to help developers, architects, and AI engineers understand how to design, implement, deploy, and operate production-ready agentic systems on Azure.

## Purpose

This repository provides practical examples for building and hosting multi-agent systems using modern AI agent frameworks, MCP-based tool services, and Azure infrastructure.

The samples are designed to show how multiple AI agents can collaborate through the **Agent-to-Agent (A2A) protocol**, while using MCP servers to access tools, services, data sources, and external APIs.

## Scenario Overview

The primary scenario in this repository is a **multi-agent vacation planning system**.

In this scenario, an orchestrator agent acts as the main vacation planner and manager. It receives the user’s travel request, breaks the request into specialized tasks, delegates those tasks to specialist agents, and assembles the final vacation plan for the user.

## Multi-Agent Architecture

The system includes an orchestrator agent and multiple specialist agents.

### Orchestrator Agent

The orchestrator is responsible for understanding the user’s vacation goals, coordinating work across specialist agents, and producing a complete travel plan.

Example responsibilities include:

- Understanding the user’s destination, budget, dates, preferences, and constraints
- Delegating tasks to the appropriate specialist agents
- Combining results into a complete itinerary
- Managing changes, updates, and trade-offs
- Coordinating payment-related workflows when required

### Specialist Agents

Specialist agents focus on specific parts of the vacation planning process.

Examples include:

- **Flights Agent**  
  Searches for flight options, compares routes, and recommends travel schedules.

- **Hotel Agent**  
  Finds hotels, resorts, and lodging options based on location, price, amenities, and availability.

- **Cruise Agent**  
  Helps users evaluate cruise options, itineraries, cabins, ports, and packages.

- **Car Rental Agent**  
  Finds rental car options and compares pricing, pickup locations, vehicle types, and policies.

- **Theme Park Agent**  
  Helps plan theme park visits, ticket options, park reservations, attractions, and schedules.

- **Boat Rental Agent**  
  Finds boat rental options, availability, pricing, and usage requirements.

- **Payment Agent**  
  Supports payment-related workflows, checkout coordination, confirmation handling, and transaction-related actions.

## Frameworks Used

This repository will include examples using multiple AI agent frameworks and SDKs, including:

- **[Microsoft Agent Framework](https://learn.microsoft.com/en-us/agent-framework/overview/?pivots=programming-language-python)**
- **[OpenAI SDK](https://openai.github.io/openai-agents-python/)**
- **[Pydantic AI](https://pydantic.dev/docs/ai/overview/)**
- **[Google Agent Development Kit](https://adk.dev/)**
- **[Claude Agent SDK](https://code.claude.com/docs/en/agent-sdk/overview)**
- **[Langgraph Agent SDK](https://pypi.org/project/langchain-azure-ai/)**
- **[Crew AI SDK](https://docs.crewai.com/en/concepts/agents)**
- **[A2A SDK](https://a2a-protocol.org/latest/sdk/)**
- **[MCP SDK](https://modelcontextprotocol.io/docs/sdk)**

The intent is to show how different agent frameworks can participate in a broader multi-agent architecture while still collaborating through shared protocols and infrastructure patterns.

## Protocols Used

### Model Context Protocol

MCP is used to expose tools, APIs, services, and data sources to agents in a standardized way.

In this repo, MCP servers may provide capabilities such as:

- Searching travel inventory
- Looking up reservations
- Retrieving pricing
- Accessing customer preferences
- Calling external APIs
- Managing booking-related workflows
- Reading and writing operational data

### Agent-to-Agent Protocol

A2A is used to enable collaboration between agents.

In this repo, A2A is used so the vacation planner orchestrator can communicate with specialist agents such as the flights agent, hotel agent, cruise agent, and payment agent.

## Azure Hosting Options

This repository demonstrates how to host agents and MCP servers using different Microsoft Azure infrastructure options.

Examples may include:

- Azure Container Apps
- Azure Kubernetes Service
- Azure App Service
- Azure Functions
- Microsoft Fabric Notebooks
- Azure API Management
- Azure Container Registry
- Azure Virtual Network
- Azure Key Vault
- Azure Managed Identity
- Azure Monitor and Application Insights
- Microsoft Foundry


The samples will show different hosting patterns depending on the requirements for scalability, security, networking, cost, and operational complexity.

## Repository Goals

This repo is intended to help answer practical architecture and implementation questions such as:

- How do I host AI agents on Azure?
- How do I host MCP servers on Azure?
- How do agents securely call tools through MCP?
- How do multiple agents collaborate using A2A?
- How do I deploy agents built with different frameworks?
- How do I secure agent-to-tool and agent-to-agent communication?
- How do I monitor and troubleshoot multi-agent systems?
- How do I choose between Azure Functions, Container Apps, AKS, and App Service?
- How do I design agents for real production workloads instead of simple demos?

## Target Audience

This repository is designed for Microsoft colleagues, Microsoft partners and customers with the following roles:

- AI engineers
- Software engineers
- Cloud architects
- Partner solution architects
- Developer advocates
- Technical trainers
- Enterprise architecture teams
- Developers building production AI agents on Azure

## Example Use Cases

Although the main scenario is vacation planning, the patterns demonstrated in this repo can be applied to many other enterprise scenarios, including:

- Customer service orchestration
- Business process automation
- Financial services workflows
- Healthcare operations support
- Retail planning assistants
- Enterprise knowledge assistants
- Field service coordination
- Supply chain management
- Internal operations copilots

## Planned/Proposed Repository Structure

```text
├── agents/
│   ├── orchestrator-vacation-planner/
│   ├── flights-agent/
│   ├── hotel-agent/
│   ├── cruise-agent/
│   ├── car-rental-agent/
│   ├── theme-park-agent/
│   ├── boat-rental-agent/
│   └── payment-agent/
│
├── mcp-servers/
│   ├── flights-mcp-server/
│   ├── hotels-mcp-server/
│   ├── cruise-mcp-server/
│   ├── car-rental-mcp-server/
│   ├── theme-park-mcp-server/
│   ├── boat-rental-mcp-server/
│   └── payments-mcp-server/
│
├── infrastructure/
│   ├── azure-container-apps/
│   ├── azure-kubernetes-service/
│   ├── azure-functions/
│   ├── azure-app-service/
│   └── shared/
│
├── shared/
│   ├── contracts/
│   ├── schemas/
│   ├── auth/
│   ├── telemetry/
│   └── utilities/
│
├── docs/
│   ├── architecture/
│   ├── deployment/
│   ├── security/
│   └── operations/
│
└── README.md
````

## Architecture Principles

The samples in this repository are guided by the following principles:

* Design agents around user goals and user experience
* Use MCP to simplify secure tool access
* Use A2A for agent-to-agent collaboration
* Keep specialist agents focused on clear responsibilities
* Use Azure-native security wherever possible
* Prefer managed identity over stored credentials
* Use Key Vault for secrets and sensitive configuration
* Add observability from the beginning
* Design for failure, retries, and graceful degradation
* Treat infrastructure as code
* Keep samples modular and reusable

## Security Considerations

Production agentic systems require strong security boundaries.

The samples in this repository will explore patterns such as:

* Managed identity authentication
* Secretless service-to-service communication
* Private networking
* API gateway protection
* Role-based access control
* Secure MCP server hosting
* Input and output validation
* Tool permission boundaries
* Audit logging
* Monitoring and alerting

## Observability

The repo will include examples for monitoring and troubleshooting agents and MCP services using Azure-native observability tools.

Potential observability components include:

* Azure Monitor
* Application Insights
* OpenTelemetry
* Distributed tracing
* Agent execution logs
* MCP tool call logs
* A2A request and response tracing
* Latency and cost tracking
* Error and retry monitoring

## Getting Started

Clone the repository:

```bash
git clone https://github.com/projectAcetylcholine/microsoft-azure-options-for-hosting-ai-agents-mcp-servers
cd microsoft-azure-options-for-hosting-ai-agents-mcp-servers
```

Review the available samples:

```bash
ls agents
ls mcp-servers
ls infrastructure
```

Each sample will include its own README with setup instructions, deployment steps, required Azure resources, and local development guidance.

## Prerequisites

Depending on the sample, you may need some or all of the following:

* Visual Studio Code
* Azure subscription
* Azure CLI
* Docker
* Python
* C#.NET
* Typescript Node.js
* GitHub account
* Azure Developer CLI
* Terraform CLI
* Access to Azure OpenAI or Azure AI Foundry

## Roadmap

Planned work for this repository includes:

* Implement vacation planner orchestrator agent
* Implement specialist travel agents
* Build MCP servers for travel-related tools
* Demonstrate A2A-based collaboration between agents
* Add Azure Container Apps deployment samples
* Add Azure Kubernetes Service deployment samples
* Add Azure Functions deployment samples
* Add Azure App Service deployment samples
* Add security and managed identity examples
* Add private networking examples
* Add observability and tracing examples
* Add CI/CD deployment pipelines
* Add architecture diagrams and walkthroughs

## Contributing

Contributions are welcome.

Useful contribution areas include:

* New agent samples
* New MCP server samples
* Azure deployment templates
* Security improvements
* Observability examples
* Documentation
* Testing and validation
* Additional multi-agent scenarios

## License

This project is licensed under the terms specified in the repository license file.

## Summary

This repository is a practical learning and reference resource for building, hosting, securing, and operating AI agents and MCP servers on Microsoft Azure.

It demonstrates how modern agent frameworks, MCP services, A2A collaboration, and Azure infrastructure can work together to support production-ready multi-agent systems.


## References
https://learn.microsoft.com/en-us/azure/foundry/how-to/develop/langchain-agents 
https://docs.langchain.com/oss/python/langchain/agents

