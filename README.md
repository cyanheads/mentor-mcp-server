# mentor-mcp-server

[![TypeScript](https://img.shields.io/badge/TypeScript-5.7-blue.svg)](https://www.typescriptlang.org/)
[![Model Context Protocol](https://img.shields.io/badge/MCP-1.4.1-green.svg)](https://modelcontextprotocol.io/)
[![Version](https://img.shields.io/badge/Version-1.0.0-blue.svg)]()
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Status](https://img.shields.io/badge/Status-Stable-blue.svg)]()
[![GitHub](https://img.shields.io/github/stars/cyanheads/mentor-mcp-server?style=social)](https://github.com/cyanheads/mentor-mcp-server)

A Model Context Protocol server providing LLM Agents a second opinion via AI-powered Deepseek-Reasoning (R1) mentorship capabilities, including code review, design critique, writing feedback, and idea brainstorming through the Deepseek API. Set your LLM Agent up for success with expert second opinions and actionable insights.

<a href="https://glama.ai/mcp/servers/fdyf7qsmit"><img width="380" height="200" src="https://glama.ai/mcp/servers/fdyf7qsmit/badge" alt="Mentor Server MCP server" /></a>

## Model Context Protocol

The Model Context Protocol (MCP) enables communication between:

- **Clients**: Claude Desktop, IDEs, and other MCP-compatible clients
- **Servers**: Tools and resources for task management and automation
- **LLM Agents**: AI models that leverage the server's capabilities

## Table of Contents

- [Features](#features)
- [Installation](#installation)
- [Configuration](#configuration)
- [Tools](#tools)
- [Examples](#examples)
- [Development](#development)
- [Project Structure](#project-structure)
- [License](#license)

## Features

### Code Analysis
- Comprehensive code reviews
- Bug detection and prevention
- Style and best practices evaluation
- Performance optimization suggestions
- Security vulnerability assessment

### Design & Architecture
- UI/UX design critiques
- Architectural diagram analysis
- Design pattern recommendations
- Accessibility evaluation
- Consistency checks

### Content Enhancement
- Writing feedback and improvement
- Grammar and style analysis
- Documentation review
- Content clarity assessment
- Structural recommendations

### Strategic Planning
- Feature enhancement brainstorming
- Second opinions on approaches
- Innovation suggestions
- Feasibility analysis
- User value assessment

## Installation

```bash
# Clone the repository
git clone git@github.com:cyanheads/mentor-mcp-server.git
cd mentor-mcp-server

# Install dependencies
npm install

# Build the project
npm run build
```

## Configuration

Add to your MCP client settings:

```json
{
  "mcpServers": {
    "mentor": {
      "command": "node",
      "args": ["build/index.js"],
      "env": {
        "DEEPSEEK_API_KEY": "your_api_key",
        "DEEPSEEK_MODEL": "deepseek-reasoner",
        "DEEPSEEK_MAX_TOKENS": "8192",
        "DEEPSEEK_MAX_RETRIES": "3",
        "DEEPSEEK_TIMEOUT": "30000"
      }
    }
  }
}
```

### Environment Variables

| Variable | Required | Default | Description |
|----------|----------|---------|-------------|
| DEEPSEEK_API_KEY | Yes | - | Your Deepseek API key |
| DEEPSEEK_MODEL | Yes | deepseek-reasoner | Deepseek model name |
| DEEPSEEK_MAX_TOKENS | No | 8192 | Maximum tokens per request |
| DEEPSEEK_MAX_RETRIES | No | 3 | Number of retry attempts |
| DEEPSEEK_TIMEOUT | No | 30000 | Request timeout (ms) |

## Tools

### Code Review
```xml
<use_mcp_tool>
<server_name>mentor-mcp-server</server_name>
<tool_name>code_review</tool_name>
<arguments>
{
  "file_path": "src/app.ts",
  "language": "typescript"
}
</arguments>
</use_mcp_tool>
```

### Design Critique
```xml
<use_mcp_tool>
<server_name>mentor-mcp-server</server_name>
<tool_name>design_critique</tool_name>
<arguments>
{
  "design_document": "path/to/design.fig",
  "design_type": "web UI"
}
</arguments>
</use_mcp_tool>
```

### Writing Feedback
```xml
<use_mcp_tool>
<server_name>mentor-mcp-server</server_name>
<tool_name>writing_feedback</tool_name>
<arguments>
{
  "text": "Documentation content...",
  "writing_type": "documentation"
}
</arguments>
</use_mcp_tool>
```

### Feature Enhancement
```xml
<use_mcp_tool>
<server_name>mentor-mcp-server</server_name>
<tool_name>brainstorm_enhancements</tool_name>
<arguments>
{
  "concept": "User authentication system"
}
</arguments>
</use_mcp_tool>
```

## Examples

Detailed examples of each tool's usage and output can be found in the [examples](examples) directory:

- [Second Opinion Example](examples/second-opinion.md) - Analysis of authentication system requirements
- [Code Review Example](examples/code-review.md) - Detailed TypeScript code review with security and performance insights
- [Design Critique Example](examples/design-critique.md) - Comprehensive UI/UX feedback for a dashboard design
- [Writing Feedback Example](examples/writing-feedback.md) - Documentation improvement suggestions
- [Brainstorm Enhancements Example](examples/brainstorm-enhancements.md) - Feature ideation with implementation details

Each example includes the request format and sample response, demonstrating the tool's capabilities and output structure.

## Development

```bash
# Build TypeScript code
npm run build

# Start the server
npm run start

# Development with watch mode
npm run dev

# Clean build artifacts
npm run clean
```

## Project Structure

```
src/
├── api/         # API integration modules
├── tools/       # Tool implementations
│   ├── second-opinion/
│   ├── code-review/
│   ├── design-critique/
│   ├── writing-feedback/
│   └── brainstorm-enhancements/
├── types/       # TypeScript type definitions
├── utils/       # Utility functions
├── config.ts    # Server configuration
├── index.ts     # Entry point
└── server.ts    # Main server implementation
```

## License

Apache License 2.0. See [LICENSE](LICENSE) for more information.

---

<div align="center">
Built with the Model Context Protocol
</div>
