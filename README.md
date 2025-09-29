# CUSTOMER SUPPORT CHATBOT

## Overview
This is a customer support chatbot built with:

- **Groq LLM** for natural language classification
- **Keyword-based fallback** for offline categorization
- **Gradio UI** for a clean, interactive web interface
- **Escalation detection** for routing sensitive queries

It automatically classifies user queries into one of three categories:
- **Billing**
- **Technical Support**
- **General Inquiry**

If a query cannot be confidently classified via keywords, the chatbot uses Groq’s LLM to determine the best category and provide a concise response.

----

## Features
- Keyword-first classification with LLM fallback
- Escalation detection based on emotional keywords
- Simple Gradio interface for web-based interaction
- Modular code for easy extension and deployment

----

##  Its Creation Story.

### Step 1: Define Categories and Sample Questions
The chatbot supports three main categories:
- **Billing**
- **Technical Support**
- **General Inquiry**

----

### Step 2: Create Keyword Lists for Each Category
Each category is associated with common keywords:
- **Billing**: `payment`, `invoice`, `bill`, `charge`
- **Technical Support**: `error`, `problem`, `not working`, `issue`, `crash`
- **General Inquiry**: `hours`, `location`, `contact`

These keywords are used for fast, offline classification.

----

### Step 3: Write Simple Classification Logic
When a user submits a question:
- Count how many keywords match each category.
- Assign the question to the category with the highest match score.
- If no keywords match, classify as `"Unknown"` and use the Groq LLM to determine the category.

---

### Step 4: Prepare Responses
Each category has a predefined, friendly response:
- **Billing**: “For billing questions, please check your account settings or contact billing support.”
- **Technical Support**: “Please try restarting your device. If the problem persists, contact technical support.”
- **General Inquiry**: “Our business hours are 9 AM to 5 PM, Monday to Friday.”
- **Unknown**: “I'm not sure I understand. Could you please rephrase your question?”

---

### Step 5: Build the Chatbot Interface
The chatbot uses Gradio to create a simple web interface:
- Input box for customer questions
- Output boxes for:
  - Category
  - Response
  - Classification method (Keyword or LLM)
  - Escalation note (optional)

This makes the chatbot easy to test, demo, and deploy.

---

