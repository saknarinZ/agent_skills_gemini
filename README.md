# Agent Skills & Configuration (Gemini) 🚀

This repository contains the **Agent Skills**, **Workflows**, and **Configurations** used by the Gemini AI Agent for the **Nexus-3D** and related projects.

These resources allow the agent to perform specialized tasks, follow standard procedures, and maintain high-quality code generation.

## 📂 Repository Structure

- **`.agent/skills/`**: Specialized instruction sets for various domains.
  - `backend`: Spring Boot, Node.js, Python patterns.
  - `frontend`: React, Next.js, Three.js guidelines.
  - `database`: SQL/NoSQL best practices.
  - `devops`: Docker, Kubernetes, CI/CD.
  - `debugging`: Systematic debugging workflows.
  - `testing`: Unit & Integration testing standards.

- **`.agent/workflows/`**: Automated step-by-step guides for common tasks.
  - `new-project`: Setup boilerplate and infrastructure.
  - `deploy`: Production deployment steps.
  - `debug`: Standardized error resolution process.
  - `code-review`: Checklist for code quality.

- **`AGENTS.md`**: Defines specific agent personas and roles.
- **`.gemini/`**: specific configurations.

## 🛠️ Usage

These files are intended to be loaded into the Agent's context to enhance its capabilities:

1.  **Skills**: The agent reads `SKILL.md` to learn how to handle specific tech stacks.
2.  **Workflows**: The user can trigger workflows (e.g., `/new-project`) to make the agent execute complex multi-step processes.

## ✍️ Author

**SaknarinZ**
