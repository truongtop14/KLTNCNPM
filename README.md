# KLTN-CMPN

# MCP for Secure

**MCP for Secure** is a graduation thesis project that explores how the **Model Context Protocol (MCP)** can be used to build a secure and extensible bridge between Large Language Models (LLMs) and external tools, services, APIs, and data sources.

Modern LLMs are powerful at understanding natural language, but they should not directly access sensitive databases, system resources, or external services without appropriate control. This project introduces an MCP-based architecture in which an **MCP Server acts as a controlled security layer** between the AI assistant and external resources.

The proposed architecture follows the workflow:

```text
User
  ↓
LLM / AI Assistant
  ↓
MCP Client
  ↓
MCP Server
  ↓
Security Layer
  ↓
Authorized Tools / APIs / Data
```

Instead of giving the LLM unrestricted access, the MCP Server exposes only predefined tools. Each tool defines its purpose, accepted parameters, permissions, and accessible resources. Requests can therefore be validated before execution.

The project focuses on several security mechanisms, including **authentication, authorization, input validation, tool permission control, rate limiting, logging, and auditing**. Sensitive tools can be restricted according to user roles, while potentially dangerous or unauthorized requests can be rejected before reaching the underlying service.

Example MCP tools may include:

```text
search_document(query)
read_document(id)
search_database(query)
get_system_information()
call_external_api(service, parameters)
```

The experimental evaluation focuses on both functionality and security. A benchmark containing normal and potentially malicious requests is created to evaluate whether the system selects appropriate tools while preventing unauthorized operations.

Key evaluation metrics include **Tool Selection Accuracy, Task Success Rate, Unauthorized Request Blocking Rate, Response Time, and Security Policy Compliance**.

The expected outcome is a working prototype consisting of an AI assistant, MCP Client, secure MCP Server, multiple MCP tools, security policies, audit logs, and an evaluation dataset.

Rather than developing another standalone chatbot, **MCP for Secure** investigates MCP as a standardized security boundary for AI-to-tool communication.

The project aims to answer the central research question:

> **How can Model Context Protocol be used to enable secure, controlled, and auditable interaction between Large Language Models and external tools?**

**Keywords:** Model Context Protocol, MCP, Large Language Models, AI Security, Tool Calling, Access Control, LLM Security, Secure AI Systems.

