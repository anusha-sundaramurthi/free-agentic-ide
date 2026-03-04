# Free Agentic IDE Setup: VS Code + Continue + Ollama

> This guide provides instructions on how to set up a completely free, local, and private agentic IDE experience using VS Code, Ollama, and the Continue extension.

---

## Table of Contents

- [Introduction](#introduction)
- [Architecture](#architecture)
- [Prerequisites](#prerequisites)
- [Setup Guide](#setup-guide)
- [Key Features](#key-features)
- [Configuration](#configuration)

---

## Introduction

An agentic IDE integrates Large Language Models (LLMs) with AI agents that can explain source code, fix issues, and add features directly within your development environment. By using local models, you eliminate API costs and ensure your code remains private on your machine.

This project demonstrates how to bypass paid AI tools like GitHub Copilot or Windsurf by setting up a local AI agentic workflow that offers:

- Unlimited tokens
- Enhanced security
- Zero cost

---

## Architecture

To achieve performance similar to paid tools, the setup utilizes three distinct types of local models via Continue.dev:

| Role | Description | Example Models |
|------|-------------|----------------|
| **Chat Model** | Primary model for code generation and detailed explanations | Llama 3, DeepSeek, GPT-OSS |
| **Autocomplete Model** | Lightweight model designed for low-latency code suggestions and snippets | Qwen |
| **Embedding Model** | Used to index your entire codebase (Kubernetes manifests, IaC, source code), allowing the AI to perform searches and understand project-wide context | — |

---

## Prerequisites

- **Visual Studio Code** — The base open-source IDE
- **Ollama** — Must be installed and running on your machine to host the local models
- **Hardware** — While requirements vary by model, a system with sufficient RAM and GPU power (e.g., 32GB+ RAM) is recommended for larger models like GPT-OSS 20B

---

## Setup Guide

1. **Install Ollama** — Download and run Ollama from its official site.

2. **Install Continue Extension**
   - Open VS Code and navigate to the Extensions marketplace.
   - Search for "Continue" and install the official extension by continue.dev.

3. **Configure Models**
   - Click the Continue icon in the sidebar.
   - Select **Local** as your provider.
   - Download/select your three models: Chat, Autocomplete, and Embeddings.
   - Click **Connect** to finalize the setup.

---

## Key Features

- **Project Explanation** — Ask the agent to explain an entire repository. It will index the files and provide a detailed breakdown of folder structures and functionalities.

- **Code Snippet Interaction** — Highlight code, right-click, and select **Continue > Add to Chat** to ask specific questions, or **Add to Edit** to request refactoring or bug fixes.

- **Indexing & Search** — The embedding model indexes your code so you can ask complex questions about how different functions connect across the project.

- **Session Management** — Keep multiple chat sessions active or delete old ones to stay organised.

- **MCP Server Support** — Connect to Model Context Protocol (MCP) servers to access external files or internet-based data.

---

## Configuration

You can fine-tune your setup through the `config.json` file. This allows you to set specific permissions for each model, such as granting "chat" and "edit" roles to your primary LLM while restricting the embedding model to indexing only.

---

