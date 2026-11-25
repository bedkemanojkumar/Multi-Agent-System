# Multi-Agent Research Automation System

**An autonomous AI-powered research and report generation system that uses multiple specialised agents to plan research, gather information, generate structured reports, and validate the final output.**

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![CrewAI](https://img.shields.io/badge/Framework-CrewAI-purple)
![LLM](https://img.shields.io/badge/AI-LLM%20Powered-green)
![Streamlit](https://img.shields.io/badge/Interface-Streamlit-red?logo=streamlit)
![Automation](https://img.shields.io/badge/System-Multi--Agent%20AI-orange)

## Overview

Researching a topic often involves multiple stages, including understanding the research objective, planning information collection, gathering relevant sources, organising findings, writing reports, and reviewing the final content.

This project implements a **Multi-Agent Research Automation System** using CrewAI, where multiple specialised AI agents collaborate to automate this workflow.

Instead of relying on a single LLM prompt to perform the entire task, the system distributes responsibilities among five specialised agents: Manager, Planner, Researcher, Writer, and Validator.

Each agent performs a dedicated role within the research pipeline. The agents coordinate through task orchestration, information sharing, and validation mechanisms to produce structured research reports.

The system supports automated web research, report generation, validation, and export in Markdown and PDF formats through a Streamlit interface.

## Key Features

### 1. Multi-Agent Architecture

The system consists of five specialised AI agents working together.

| Agent | Responsibility |
|---|---|
| Manager Agent | Coordinates the research workflow and manages task delegation |
| Planner Agent | Breaks down the research query into actionable research tasks |
| Researcher Agent | Searches the internet and gathers relevant information |
| Writer Agent | Organises research findings into a structured report |
| Validator Agent | Reviews the generated report for correctness, completeness, clarity and structure |

Each agent is assigned a specific role, objective, and task within the overall workflow.

### 2. Autonomous Task Planning

The Planner Agent analyses the user's research query and decomposes it into smaller tasks.

Its responsibilities include:

- Understanding the research objective.
- Identifying important subtopics.
- Defining the research strategy.
- Organising research tasks.
- Providing structured instructions to subsequent agents.

This helps transform a broad research question into a more organised research workflow.

### 3. Internet-Based Research

The Researcher Agent gathers information from online sources using DuckDuckGo Search (DDGS).

The research process includes:

- Searching for relevant information.
- Gathering supporting material.
- Identifying useful online resources.
- Organising research findings for report generation.

The collected information is passed to the subsequent agents as research context.

### 4. Automated Report Generation

The Writer Agent converts gathered research information into a structured report.

The report generation process focuses on:

- Organising information into meaningful sections.
- Maintaining logical flow.
- Producing readable explanations.
- Structuring research findings.
- Generating Markdown and PDF reports.

### 5. Automated Validation and Self-Correction

The Validator Agent reviews the generated report before final output.

The validation workflow uses a PASS/FAIL mechanism.

- **PASS:** The report satisfies the configured validation requirements.
- **FAIL:** The report is sent through the configured retry and regeneration process.

The validation process helps identify issues relating to report structure, clarity, completeness, grammar and consistency.

This introduces an iterative quality-control stage into the multi-agent workflow.

### 6. Hierarchical Task Orchestration

The system uses CrewAI's hierarchical task execution approach.

The Manager Agent coordinates the workflow and delegates responsibilities to specialised agents.

This allows the research process to be divided into smaller tasks rather than depending on one agent to handle every stage.

### 7. Interactive Streamlit Interface

The project provides a Streamlit-based interface through which users can submit research topics and generate reports.

Key capabilities include:

- Research query input.
- Automated multi-agent execution.
- Research report generation.
- Report presentation.
- Markdown export.
- PDF export.

The system also supports execution through the terminal.

## System Architecture

The system follows a multi-agent architecture in which specialised agents collaborate through a coordinated research and report-generation pipeline.

```text
                  USER INPUT
                      |
               Research Query
                      |
                      v
                MANAGER AGENT
             Workflow Coordination
                      |
                      v
                PLANNER AGENT
             Research Task Breakdown
                      |
                      v
               RESEARCHER AGENT
             Internet-Based Research
                  (DDGS)
                      |
                      v
                 WRITER AGENT
             Structured Report Creation
                      |
                      v
               VALIDATOR AGENT
              Report Quality Check
                      |
                +-----+-----+
                |           |
               PASS        FAIL
                |           |
                v           v
           Final Report   Retry /
                |         Regeneration
                |           |
                |-----------+
                |
                v
            OUTPUT FORMAT
                |
          +-----+-----+
          |           |
       Markdown      PDF
```

## Agent Workflow

### Stage 1 – Research Query

The user submits a topic or research question through the Streamlit application or terminal.

### Stage 2 – Planning

The Manager coordinates the workflow and the Planner decomposes the research topic into smaller tasks.

### Stage 3 – Information Gathering

The Researcher performs internet-based searches using DDGS and collects relevant information.

### Stage 4 – Report Writing

The Writer organises the gathered information into a structured research document.

### Stage 5 – Validation

The Validator checks the generated report against its configured quality requirements.

### Stage 6 – Final Output

If validation succeeds, the final report is made available for export in Markdown or PDF format. If validation fails, the configured retry mechanism initiates another generation cycle.

## Technology Stack

| Category | Technologies |
|---|---|
| Programming Language | Python |
| Multi-Agent Framework | CrewAI |
| LLM Integration | OpenRouter API |
| Language Model | DeepSeek Chat |
| Web Search | DuckDuckGo Search (DDGS) |
| User Interface | Streamlit |
| PDF Generation | ReportLab |
| Report Formatting | Markdown |
| Execution Environment | Python, Terminal |

## Project Structure

The project is organised around agent definitions, task orchestration, report generation and application interfaces.

```text
Multi-Agent-System/
│
├── README.md
│
├── agents/
│
├── tasks/
│
├── tools/
│
├── app.py
│
├── main.py
│
├── requirements.txt
│
├── .env.example
│
└── ...
```

*Note: Update this directory tree to match the actual repository structure before publishing. The folders above represent the logical components of the system.*

## Installation and Setup

### 1. Clone the Repository

```bash
git clone https://github.com/bedkemanojkumar/Multi-Agent-System.git
```

### 2. Navigate to the Project Directory

```bash
cd Multi-Agent-System
```

### 3. Create a Virtual Environment

```bash
python -m venv venv
```

Activate it:

**Windows:**

```bash
venv\Scripts\activate
```

**Linux / macOS:**

```bash
source venv/bin/activate
```

### 4. Install Dependencies

```bash
pip install -r requirements.txt
```

### 5. Configure API Credentials

The project uses the OpenRouter API to access the configured language model.

Create a `.env` file in the project root and configure the required API credentials according to the application's environment-variable names.

Example:

```env
OPENROUTER_API_KEY=your_api_key_here
```

Never commit API keys or other sensitive credentials to GitHub.

### 6. Run the Application

For the Streamlit interface:

```bash
streamlit run app.py
```

For terminal execution:

```bash
python main.py
```

*Use the actual entry-point filenames from your repository if they differ.*

## Output Formats

The system supports two report formats:

| Format | Description |
|---|---|
| Markdown (`.md`) | Structured, editable research report |
| PDF (`.pdf`) | Formatted report suitable for sharing and reading |

PDF generation is implemented using ReportLab.

## Key Engineering Concepts

This project provides practical exposure to:

- Multi-agent system architecture.
- Role-based AI agent design.
- Hierarchical task orchestration.
- Autonomous task delegation.
- LLM integration through APIs.
- Internet-based information retrieval.
- Automated report generation.
- Agent-based validation workflows.
- Iterative regeneration and quality control.
- Integration of AI workflows with Streamlit applications.

## Challenges and Engineering Decisions

### Coordinating Multiple Specialised Agents

A research workflow involves several dependent tasks. Managing all these responsibilities through a single agent can make the process difficult to organise.

**Approach:** Divided the workflow into specialised agents with clearly defined responsibilities and used CrewAI to coordinate task execution.

### Gathering Relevant Research Information

Generating a research report requires relevant information from external sources.

**Approach:** Integrated DDGS-based web search into the Researcher Agent to collect online information for downstream report generation.

### Maintaining Report Quality

Automatically generated reports may contain incomplete sections, unclear explanations or structural issues.

**Approach:** Introduced a dedicated Validator Agent with PASS/FAIL evaluation and a retry mechanism to improve report quality.

### Generating Shareable Reports

Research findings need to be presented in a format that is easy to read and distribute.

**Approach:** Implemented Markdown report generation and PDF export using ReportLab.

## Limitations

- Research quality depends on the relevance and reliability of retrieved online sources.
- LLM-generated content may contain inaccurate or unsupported information.
- Automated validation does not guarantee factual correctness.
- Output quality depends on the configured model and its API availability.
- Research execution may involve latency and API usage costs.
- The system does not replace expert review or independent verification of research findings.

## Future Improvements

- Introduce source citations and reference verification in generated reports.
- Add retrieval quality and factual consistency evaluation.
- Implement source credibility scoring.
- Add persistent research memory across sessions.
- Support additional LLM providers.
- Introduce human-in-the-loop report approval.
- Add structured report templates for academic and technical research.
- Develop a research dashboard with agent execution monitoring.
- Improve validation using independent evaluation criteria.

## Author

**Manojkumar Shriniwas Bedke**

B.Tech – Computer Science Engineering, 2027

Interested in Artificial Intelligence, Machine Learning, Generative AI, Multi-Agent Systems and Applied AI Research.

- **GitHub:** [bedkemanojkumar](https://github.com/bedkemanojkumar)
- **LinkedIn:** [manojkumar-bedke01](https://linkedin.com/in/manojkumar-bedke01)

---

*This project explores how collaborative AI agents can automate research workflows through task planning, information retrieval, structured report generation and iterative validation.*
