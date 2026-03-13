# Multi-Agent AI Blog Post Creator

## Overview
This project is a beginner-friendly multi-agent AI system designed to autonomously research, plan, write, and edit high-quality blog posts .

The system is built using the **OpenAI Swarm** package, a framework that facilitates the creation, interaction, and context management of multiple AI agents [3, 4].

## Key Advantages
* **Specialization:** Each AI agent focuses exclusively on a specific role (e.g., planning, researching, writing), which leads to higher quality output [2].
* **Scalability:** The architecture allows for the system to be easily expanded by simply adding new agents with new instructions [3].
* **Robustness & Accuracy:** By passing the output through a dedicated editor agent, the system significantly reduces the hallucinations commonly associated with LLMs [5, 6].
* **Parallelization:** While managed under the hood by Swarm, multiple agents can theoretically handle different aspects of a task simultaneously [2, 7].

## The Agent Workflow
The system relies on a hierarchical chain of five specialized agents that pass tasks down the line:

1. **Admin (Manager) Agent:** The user-facing agent that oversees the project, initiates the workflow, and delegates the initial task to the planner [8-10].
2. **Planner Agent:** Takes the user's initial topic and organizes it into a structured outline with clear topics, sections, and headings [11].
3. **Researcher Agent:** Takes the planner's outline and performs comprehensive, deep research to provide dense context and information for each individual section [11, 12].
4. **Writer Agent:** Uses the researcher's detailed notes to draft a clear, coherent, and engaging blog post [13].
5. **Editor Agent:** Reviews the writer's drafted blog post for quality assurance, makes necessary corrections, and finalizes the text [5, 8]. 

## Output Generation
Once the Editor Agent completes its review, the system utilizes a specialized `complete_blog_post` function [14, 15]. This function automatically generates a local Markdown (`.md`) file encoded in UTF-8, titling it appropriately and saving the fully formatted blog post content directly to your environment [16, 17]. 

## Prerequisites
* A Google Colab notebook or a standard Python environment [1].
* An active OpenAI API Key [18].

## Installation
To run this project, you need to install the OpenAI Swarm package directly from its GitHub repository [19]. 

```bash
pip install git+https://github.com/openai/swarm.git
