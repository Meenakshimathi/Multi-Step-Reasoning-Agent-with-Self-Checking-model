# Multi-Step-Reasoning-Agent-with-Self-Checking-model
 small “reasoning agent” that can solve structured problems in multiple  steps, check its own work, and only show the final answer to the user.LLM API you like (OpenAI, Anthropic, Gemini etc.) and any  programming language.
# 🧠 Multi-Step Reasoning Agent (Planner–Executor–Verifier)

This project implements a **multi-step reasoning agent** that solves structured
math, logic, and scheduling word problems using an LLM.

The agent follows a clear internal workflow:
1. **Planner** – creates a step-by-step plan
2. **Executor** – solves the problem using the plan
3. **Verifier** – validates correctness
4. **Formatter** – returns a clean JSON response

The full chain-of-thought is **not exposed to the user**, only a short explanation
and the final answer.

---

## 📂 Project Structure

.
├── app.py # Streamlit UI
├── agent.py # Reasoning agent logic
├── llm_client.py # Together.ai client
├── requirements.txt

Example Questions

If a train leaves at 14:30 and arrives at 18:05, how long is the journey?

Alice has 3 red apples and twice as many green apples. How many apples total?

A meeting needs 60 minutes. Which time slots can fit the meeting?
└── README.md

Agent Design
Planner

Parses the question

Produces a logical step-by-step plan

Does not solve the problem

Executor

Follows the planner output

Computes intermediate values

Produces a short explanation and final answer

Verifier

Re-checks the solution

Validates constraints and correctness

Determines success or failure

If verification fails, the agent can retry or return a failure status.

 Output Format

 he agent returns a structured JSON object:

{
  "answer": "final answer",
  "status": "success",
  "reasoning_visible_to_user": "short explanation",
  "metadata": {
    "plan": ["step 1", "step 2"],
    "checks": [],
    "retries": 0
  }
}

he agent returns a structured JSON object:

{
  "answer": "final answer",
  "status": "success",
  "reasoning_visible_to_user": "short explanation",
  "metadata": {
    "plan": ["step 1", "step 2"],
    "checks": [],
    "retries": 0
  }
}

Possible Improvements

Batch processing of multiple questions

Stronger verifier logic

Retry strategy with feedback

Unit tests and automated evaluation

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/46351363-510e-4488-905d-382f10d784af" />

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/a260e043-af57-40a7-bc43-bdc4ec5b353c" />

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/707602f7-cca7-4102-a8f5-8d2c18f16e26" />



