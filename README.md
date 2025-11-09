# Conversation Design Case Study (2025)
Improving AI Reliability Through Intent Mapping, Tone Control, and Safety-Aware Microcopy

### Reference: Conversational AI Foundations
- McTear, M. (2023). *The Conversational AI Handbook*.  
  https://arxiv.org/abs/2303.06745

- Google Research. *Building Better Bots: Principles of Conversational AI.*  
  https://research.google/pubs/pub48120/

- Microsoft. *Guidelines for Human-AI Interaction.*  
  https://www.microsoft.com/en-us/research/project/guidelines-for-human-ai-interaction/

- Rasa. *Conversation-Driven Development.*  
  https://cdn2.hubspot.net/hubfs/4984639/Conversation-Driven_Development.pdf

## 📌 Overview  
This project demonstrates how I design AI interactions that remain clear, safe, and trustworthy when user messages are vague or ambiguous.  
I built a structured approach combining:

- Intent modeling  
- Tone control  
- Safety-aware microcopy  
- Multi-turn flow patterns  

The aim is to reduce model errors, prevent overconfidence, and support dependable user experiences in high-ambiguity contexts.



## 🧩 Problem  
Users often write very short messages with missing context:

- “It won’t let me in.”  
- “Fix this.”  
- “I don’t see it.”  
- “Why did it do that?”

These create three risks:

1. Misinterpreting intent  
2. Overconfident or unsafe responses  
3. User frustration when the system answers the wrong question  

A consistent approach is needed to clarify intent early and manage tone responsibly.

---

## ✅ Approach  
This system has three components:

### **1. Intent Decomposition**  
Each ambiguous message is broken into:  
- Primary intent  
- Secondary possibilities  
- Disallowed interpretations  
- Required clarification questions  

### **2. Tone Control System**  
Three tones adapt based on risk:  
- Plain Helpful  
- Safety-Aware  
- Expert-Concise  

### **3. Safety Microcopy**  
Reusable phrases that expose uncertainty early and keep responses within privacy and compliance boundaries.

---

## 🗂️ Intent Maps (10 Examples)

> **Format:**  
> Primary intent → Secondary intents → Clarifying question

### 1. “It’s not letting me in again.”  
- Primary: login/access failure  
- Secondary: password issue, MFA failure, permissions  
- Clarification: `Which step fails — password, code, or permissions?`

### 2. “Why does it keep changing?”  
- Primary: inconsistent behavior  
- Secondary: UI personalization, layout shift, model variance  
- Clarification: `What’s changing — the layout, content, or settings?`

### 3. “Fix this, it’s broken.”  
- Primary: feature malfunction  
- Secondary: error state, crash, unexpected output  
- Clarification: `What happened right before it broke?`

### 4. “I didn’t ask for that.”  
- Primary: incorrect system action  
- Secondary: intent mismatch, autofill, hallucination  
- Clarification: `What did you expect to happen instead?`

### 5. “Where did my stuff go?”  
- Primary: missing data  
- Secondary: wrong tab, filter, sync delay, wrong account  
- Clarification: `Were you viewing it in the same place you saved it?`

### 6. “That’s not what I meant.”  
- Primary: misunderstood request  
- Secondary: vague phrasing, missing context  
- Clarification: `What outcome were you aiming for?`

### 7. “Why is it taking so long?”  
- Primary: performance concern  
- Secondary: network latency, heavy processing, large file  
- Clarification: `Is it stuck loading, processing, or waiting?`

### 8. “I don’t see it.”  
- Primary: missing UI output  
- Secondary: hidden panel, wrong screen, file not generated  
- Clarification: `Were you expecting a message, file, or interface element?`

### 9. “Why did it do that?”  
- Primary: unexpected system behavior  
- Secondary: automation trigger, recommendation logic  
- Clarification: `Which action are you referring to?`

### 10. “This doesn’t look right.”  
- Primary: quality concern  
- Secondary: outdated data, formatting issue, wrong version  
- Clarification: `What seems incorrect — the content, the structure, or the source?`

---

## 🎨 Tone Modes  
Each message chooses a tone mode based on risk:

### **1. Plain Helpful**  

