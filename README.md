# AI Research Automation with n8n

An AI-powered research automation workflow built with **n8n, Tavily, OpenAI, and Gmail**. It automates the process of researching a topic, organizing information, writing structured content, and generating a newsletter-style email with references.

Instead of manually searching multiple websites, collecting information, and writing a report, this workflow uses multiple AI agents to handle the research and content generation process automatically.

## Project Overview

The workflow transforms web research into a structured, AI-generated newsletter delivered directly to your email.

You simply execute the workflow, and the automation handles the remaining steps:

- Searches the web for recent information.
- Creates a research plan and identifies relevant topics.
- Performs focused searches for each topic.
- Writes individual content sections.
- Combines and edits the generated sections.
- Generates a final HTML email with sources and citations.
- Sends the completed newsletter through Gmail.

## Workflow Architecture

![AI Research Automation Workflow](screenshots/workflow-overview.png)

**Workflow sequence:**

```text
Manual Trigger
      |
      v
Tavily Web Search
      |
      v
Planning Agent
      |
      v
Split Out
      |
      v
Tavily Topic Search
      |
      v
Section Writer Agent
      |
      v
Aggregate
      |
      v
Editor Agent
      |
      v
Gmail
```

## How It Works

### 1. Manual Trigger
Starts the workflow manually.

### 2. Initial Web Search
Uses Tavily to search for recent information related to the research subject.

### 3. Planning Agent
Analyzes the initial search results and creates a structured research plan, including a newsletter title and a list of topics.

Uses an OpenAI Chat Model and Structured Output Parser to generate organized output.

### 4. Split Out
Converts the generated topics array into individual items so each topic can be processed separately.

### 5. Topic Research
Performs a focused Tavily search for each topic to gather additional information.

### 6. Section Writer Agent
Uses the research results to write a detailed section for each topic.

### 7. Aggregate
Collects the individual sections and combines them into one structured result.

### 8. Editor Agent
Reviews and organizes the generated content, producing a final email subject and HTML newsletter body with citations and a consolidated source list.

### 9. Gmail
Sends the final newsletter directly to the configured email address.

## Technologies Used

| Technology | Purpose |
|---|---|
| n8n | Workflow automation and orchestration |
| Tavily | AI-oriented web search |
| OpenAI | Planning, writing, and editing |
| AI Agents | Multi-step research and content generation |
| Structured Output Parser | Structured AI responses |
| Gmail | Newsletter delivery |

## Setup Instructions

1. Download or clone this repository.
2. Import the workflow JSON file into your n8n instance.
3. Install or enable the Tavily node required by the workflow.
4. Configure your Tavily API credentials.
5. Configure your OpenAI credentials.
6. Configure your Gmail OAuth credentials.
7. Set your intended recipient email address in the Gmail node.
8. Execute the workflow and check your inbox.

