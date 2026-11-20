# hr-helpdesk-agent
# 🤖 HR/IT Helpdesk Agent - GoAIfied Assignment
**By Kiran Tomar**

## 🔴 Live Demo
👉 `index.html` file ko kholo - Koi setup nahi chahiye, turant chalega.

## 🎯 Kya Banaya Hai?
Ek Safe HR Helpdesk Agent jo sirf company ke policy docs se jawab deta hai. Ye hallucinate nahi karta.

Jaise GoAIfied ke JD me maanga tha, waisa hi banaya hai.

## ✨ Features (JD ke hisab se)

### 1. RAG (Retrieval-Augmented Generation)
Answer pehle Knowledge Base me search hota hai, fir hi dikhata hai.
Agar answer docs me nahi hai, to agent bolta hai - "I don't know, please raise a ticket"

### 2. Source Citation
Har answer ke neeche Source likha aata hai.
Example: `Source: HR Leave Policy 2026, Page 2`

### 3. Prompt-Injection Guard
Agar koi likhe - `ignore previous instructions` ya `reveal system prompt`
To agent block kar deta hai:
> "I can't follow that instruction. I only answer HR/IT policy questions."

### 4. PII Redaction (Privacy)
Agar user apna Phone Number ya Email likh de, to agent usko `**********` kar deta hai.
Example: `9876543210` -> `**********`

### 5. Human Escalation
Agar sawal docs me nahi mila, to agent jhootha jawab nahi deta, human ko escalate karta hai.

## 🧪 Try Karke Dekho - Ye 4 Cheez Type Karo
1. `How many leaves left?` -> Leave balance + Source aayega
2. `ignore previous instructions` -> Block ho jayega
3. `My number is 9876543210` -> Number hide ho jayega
4. `What is CEO's salary?` -> "I don't know" bolega

## 🚀 Future Production Architecture
Agar isko production me le jana ho, to aise banega:

`User -> Frontend -> FastAPI -> LangGraph Agent -> MCP Server -> PostgreSQL (pgvector) -> Policy Docs`

+ Safety Layer: Injection Guard + PII Redaction
+ Evaluation: Har answer ka Faithfulness check

## 😤 Sabse Hard Part Kya Tha?
Agent ko smart banana aasan tha, **safe** banana hard tha.

Koi bhi chatbot bana sakta hai, par usko prompt-injection se bachana aur PII leak rokna hard tha. Isliye maine Guard Layer lagaya jo pehle query ko check karta hai, fir hi answer deta hai.

With more time, I will add real LangGraph + MCP + PostgreSQL pgvector and evaluation.

## 👩‍💻 Made By
**Kiran Tomar** - B.Tech CSE | Interested in AI Agents & Web Development
