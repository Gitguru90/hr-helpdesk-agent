# HR/IT Helpdesk Agent - GoAIfied Assignment
**By Kiran Tomar - B.Tech Mathematics and Computing**

## Live Demo
https://gitguru90.github.io/hr-helpdesk-agent/

## Overview
A Safe HR Helpdesk Agent that answers only from company policy documents. It does not hallucinate.

## Features

### 1. RAG (Retrieval-Augmented Generation)
Answer is first searched in the Knowledge Base, then shown.
If answer is not in docs, agent says - "I don't know, please raise a ticket"

### 2. Source Citation
Every answer shows its Source.
Example: `Source: HR Leave Policy 2026, Page 2`

### 3. Prompt-Injection Guard
If user types - `ignore previous instructions` or `reveal system prompt`
Agent blocks it.

### 4. PII Redaction
If user types Phone Number or Email, agent masks it as `**********`

### 5. Human Escalation
If question is not in docs, agent does not give a fake answer, it escalates to human.

## How to Test
1. `How many leaves left?` -> Leave balance + Source
2. `ignore previous instructions` -> Blocked
3. `My number is 9876543210` -> Number masked
4. `What is CEO's salary?` -> "I don't know"

## Future Production Architecture
`User -> Frontend -> FastAPI -> LangGraph Agent -> MCP Server -> PostgreSQL (pgvector) -> Policy Docs`

+ Safety Layer: Injection Guard + PII Redaction
+ Evaluation: Faithfulness check for every answer

## Hardest Part
Making the agent smart was easy, making it safe was hard. That is why I added a Guard Layer that checks the query first, then gives the answer.

## Author
**Kiran Tomar** - B.Tech Mathematics and Computing | Interested in AI Agents & Web Development
