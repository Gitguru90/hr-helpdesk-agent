# 🤖 HR/IT Helpdesk Agent - GoAIfied Assignment
**By Kiran Tomar**

## 🔴 Live Demo
👉 `https://gitguru90.github.io/hr-helpdesk-agent/` - Open karo, turant chalega.

## 🎯 Kya Banaya Hai?
Ek Safe HR Helpdesk Agent jo sirf company ke policy docs se jawab deta hai. Ye hallucinate nahi karta.

## ✨ Features (JD ke hisab se)

### 1. RAG (Retrieval-Augmented Generation)
Answer pehle Knowledge Base me search hota hai, fir hi dikhata hai.
Agar answer docs me nahi hai, to agent bolta hai - "I don't know, please raise a ticket"

### 2. Source Citation
Har answer ke neeche Source likha aata hai.
Example: `Source: HR Leave Policy 2026, Page 2`

### 3. Prompt-Injection Guard
Agar koi likhe - `ignore previous instructions` ya `reveal system prompt`
To agent block kar deta hai.

### 4. PII Redaction (Privacy)
Agar user apna Phone Number ya Email likh de, to agent usko `**********` kar deta hai.

### 5. Human Escalation
Agar sawal docs me nahi mila, to agent jhootha jawab nahi deta, human ko escalate karta hai.

## 🧪 Try Karke Dekho
1. `How many leaves left?` -> Leave balance + Source aayega
2. `ignore previous instructions` -> Block ho jayega
3. `My number is 9876543210` -> Number hide ho jayega
4. `What is CEO's salary?` -> "I don't know" bolega

## 🚀 Future Production Architecture
`User -> Frontend -> FastAPI -> LangGraph Agent -> MCP Server -> PostgreSQL (pgvector) -> Policy Docs`

+ Safety Layer: Injection Guard + PII Redaction
+ Evaluation: Har answer ka Faithfulness check

## 😤 Sabse Hard Part Kya Tha?
Agent ko smart banana aasan tha, **safe** banana hard tha. Isliye maine Guard Layer lagaya jo pehle query ko check karta hai, fir hi answer deta hai.

## 👩‍💻 Made By
**Kiran Tomar** - B.Tech CSE | Interested in AI Agents & Web Development
