# HR/IT Helpdesk Agent - GoAIfied Assignment
By Kiran Tomar

## Live Demo
Open index.html - No setup needed

## What I Built
A safe HR Helpdesk Agent that answers only from company policy docs (RAG approach).

## Features (As per JD)
1.  **RAG:** Answers retrieved from Knowledge Base, not hallucinated.
2.  **Source Citation:** Every answer shows Source Doc.
3.  **Prompt-Injection Guard:** Blocks "ignore previous instructions" attacks.
4.  **PII Redaction:** Phone numbers & Emails auto-masked to ***.
5.  **Human Escalation:** If answer not in docs, it says "I don't know" and escalates.

## Future Architecture (Production)
Frontend -> FastAPI -> LangGraph Agent -> PostgreSQL (pgvector) via MCP Server -> Policy Docs
+ Evaluation: Faithfulness check on every answer.

## Hardest Part
Handling unclear queries like "leave" - I solved with intent keywords + showing source so user can verify.
