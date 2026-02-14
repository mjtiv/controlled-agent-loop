# Agentic Role Check Demo

A lightweight demonstration of structured, agent-driven document
evaluation using the OpenAI API.

This project showcases how to:

-   Parse individual text files representing people profiles
-   Send them to a structured AI agent
-   Classify whether the person matches a specified role (e.g., "baker")
-   Avoid cognitive drift by keeping prompts small and controlled

The goal is not just classification --- it's demonstrating **controlled
AI execution**.

------------------------------------------------------------------------

## 📁 Project Structure

Place your files in the following layout:

    people_demo/
      sample_people/
        01_amelia_hart_true_baker.txt
        02_marcus_lee_false_baker_label.txt
        03_priya_nair_data_analyst.txt
        04_jose_alvarez_chef_trap_overlap.txt
        05_sarah_kim_flight_attendant.txt
      run_role_check.py
      .env

------------------------------------------------------------------------

## ⚙️ Installation

Install required dependencies:

    pip install openai python-dotenv

------------------------------------------------------------------------

## 🔑 Setting Up OpenAI API Access

To run this project, you need an OpenAI API key.

### 1️⃣ Create an OpenAI Account

1.  Go to https://platform.openai.com\
2.  Sign up or log in.\
3.  Verify your email if prompted.

------------------------------------------------------------------------

### 2️⃣ Add Billing (Buy Tokens)

The OpenAI API is usage-based (pay per token).

1.  Navigate to **Billing** in the dashboard.\
2.  Add a payment method (credit/debit card).\
3.  Optionally set a monthly spending limit for safety.

For small demos like this, usage typically costs only a few cents.

------------------------------------------------------------------------

### 3️⃣ Generate an API Key

1.  Go to **API Keys** in the dashboard.\
2.  Click **Create new secret key**.\
3.  Copy the key immediately (you won't be able to see it again).

It will look like:

    sk-xxxxxxxxxxxxxxxxxxxxxxxx

------------------------------------------------------------------------

## 🔐 Environment Setup

Create a `.env` file in the root directory:

    OPENAI_API_KEY=your_key_here
    OPENAI_MODEL=gpt-4o-mini

Using `python-dotenv` keeps credentials out of source control and makes
the demo clean and portable.

------------------------------------------------------------------------

## 🧠 Agentic API Design Philosophy

This demo uses structured, agent-style prompting:

-   Each file is evaluated independently
-   Prompts are minimal and role-focused
-   Output is structured JSON
-   No long context windows
-   No stuffing multiple documents into a single call

This avoids a major hidden failure mode of large language models.

------------------------------------------------------------------------

# 🚨 Biggest Issue with AI + API Calling

## Cognitive Drift + Hallucination

Once you stuff a large amount of text into the context window, model
performance often degrades instead of improving.

This is counterintuitive.

Engineers frequently assume:

> "More context = more accuracy."

In practice:

-   Attention becomes diluted
-   Signal-to-noise ratio drops
-   Subtle contradictions get ignored
-   The model begins inferring beyond the provided evidence

Large prompts increase:

-   Hallucination risk
-   Instruction drift
-   Cost
-   Latency

This demo intentionally keeps calls small and controlled.

------------------------------------------------------------------------

## 📏 Token Planning Guide

For engineering estimation:

**1,000 words ≈ 1,300--1,500 tokens**\
**Tokens ≈ words × 1.3**

### Easy Mental Conversions

  Tokens    Approx Words
  --------- --------------
  1,000     \~750
  5,000     \~3,800
  10,000    \~7,500
  100,000   \~75,000

------------------------------------------------------------------------

## 🏗 Engineering Takeaway

For agentic document parsing systems:

-   Keep prompts small
-   Chunk larger documents
-   Use retrieval (RAG) when needed
-   Keep API calls under \~10--20k tokens
-   Never assume bigger context equals better reasoning

Well-designed small calls often outperform massive context dumps.

------------------------------------------------------------------------

## ▶️ Running the Demo

Once your `.env` is configured and dependencies are installed:

    python run_role_check.py

The script will:

-   Iterate over the `sample_people` folder
-   Evaluate each profile
-   Output structured results (e.g., JSON)

------------------------------------------------------------------------

## 🎯 Why This Matters

This project demonstrates:

-   Controlled AI execution
-   Deterministic evaluation pipelines
-   Structured output enforcement
-   Practical token budgeting
-   Real-world API design discipline

AI systems should be architected --- not prompted casually.



