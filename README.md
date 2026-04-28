# Deep Dive — Technical Analysis Documentation Agent

[![VS Code](https://img.shields.io/badge/VS%20Code-Agent-007ACC?logo=visual-studio-code&logoColor=white)](https://code.visualstudio.com/)
[![GitHub Copilot](https://img.shields.io/badge/GitHub%20Copilot-Powered-8957e5?logo=github&logoColor=white)](https://github.com/features/copilot)
[![MCP](https://img.shields.io/badge/MCP-Notion%20%7C%20Jira%20%7C%20Confluence-FF6C37?logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0IiBmaWxsPSJ3aGl0ZSI+PGNpcmNsZSBjeD0iMTIiIGN5PSIxMiIgcj0iMTAiLz48L3N2Zz4=&logoColor=white)](https://modelcontextprotocol.io/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

This project contains a **VS Code Copilot agent** that automatically generates technical analysis documentation (deep dives) from external sources.

## Prerequisites

- **VS Code** with the **GitHub Copilot Chat** extension installed
- The following MCP servers configured in VS Code:
  - `mcp-notion` — to access Notion pages
  - `mcp-atlassian` — to access Jira tickets and Confluence pages

## Project Structure

```text
.
├── .github/
│   └── agents/
│       └── deep-dive.agent.md   # Agent definition
├── deep-dives/                   # Output folder for analyses
│   └── YYYY-MM-DD_<topic>/
│       └── README.md
└── README.md
```

## Usage

### 1. Launch the agent

In VS Code, open the Copilot chat and select the **Deep Dive** agent from the agent picker (or type `@deep-dive`).

### 2. Describe the topic

The agent will ask you for:

1. The **topic** of the deep dive
2. The **language** for the generated documentation (default: **French**)
3. The **information sources** to consult, among:
   - **Notion** — a Notion page (title or URL)
   - **Jira** — a Jira ticket (ticket key, e.g. `PROJ-123`)
   - **Confluence** — a Confluence page (title or URL)

You can select one or multiple sources.

### 3. Automatic generation

The agent will:

- Retrieve all information from the selected sources via the MCP servers
- Synthesize and structure the data into a technical analysis
- Generate the documentation in `deep-dives/<date>_<topic>/README.md`

### 4. Output

The generated documentation contains:

- **Context** — why this deep dive was initiated
- **Objective** — what the analysis aims to clarify
- **Technical Analysis** — architecture, key decisions, implementation details
- **Open Questions** — points requiring further investigation
- **References** — links to all source documents

## Updating a deep dive

To update an existing deep dive, relaunch the agent with the topic and new sources. The agent can complement or update the existing documentation.

## Customization

The agent is defined in [.github/agents/deep-dive.agent.md](.github/agents/deep-dive.agent.md). You can modify:

- The documentation template sections
- The MCP tools used
- The information gathering workflow

---

&copy; 2026 [saumon](https://github.com/saumon)
