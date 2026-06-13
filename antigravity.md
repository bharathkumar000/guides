# 👾 Unleashing Antigravity: Your Agentic AI Coding Partner

Welcome to **Antigravity**, your autonomous AI development assistant! Unlike simple chatbots that only spit out code snippets for you to copy and paste, Antigravity is **agentic**. This means it can read your project structure, edit files directly, run terminal commands, debug compiler errors, and orchestrate complex setups — all with your authorization.

Think of Antigravity as an eager, hyper-competent co-pilot who writes the code, handles configurations, and manages terminal execution while you steering the architecture.

---

## 🗺️ How Antigravity Works (The Collaboration Loop)

Here is a visual breakdown of how you and Antigravity collaborate on a task:

```mermaid
flowchart TD
    Prompt["👤 You send a request\n'Create a web page to calibrate motor sensors'"] --> Read["🔍 Antigravity analyzes your code\nInspects file system & active documents"]
    Read --> Plan["📝 Proposes actions\nShows plans, file updates, and commands"]
    Plan --> Approve{"🧑‍⚖️ Your Approval\nDo you want to run these changes?"}
    Approve -->|Approved| Run["⚙️ Terminal Execution\nAntigravity executes commands & writes files"]
    Approve -->|Rejected| EditPlan["💬 Modify prompt\n'Change port from 3000 to 5000'"]
    EditPlan --> Read
    Run --> Verify["✅ Verification\nTests execution, catches compiler errors"]
    Verify --> Done(["🎉 Task Completed!"])

    style Prompt fill:#74b9ff,stroke:#0984e3,color:#fff
    style Approve fill:#fdcb6e,stroke:#f39c12,color:#333
    style Run fill:#00b894,stroke:#00a884,color:#fff
```

---

## 💡 Humorous Prompts: How to Communicate with Antigravity

Antigravity understands natural language. To get the best out of it, treat it like an elite software engineer. 

### ❌ What NOT to say (Vague & Boring)
> *"Fix the bug in the app."* (Which app? What bug? Where is the error log?)

### ✅ What to say (Professional, Specific, and Fun)
> *"Antigravity, review my `motor.cpp` file. The loop starts lagging when speed exceeds 180. Write a safety dampener that caps acceleration spike rates, compile the code, and test if it builds cleanly."*

### 🤖 Fun Prompt Example: The Monday Slack Complaints Script
You want to write a Python script that checks the day of the week, and if it's Monday morning, it sends a randomized humorous complaint about Mondays to a webhook.
* **Prompt for Antigravity:**
  > *"Antigravity, write a Python script in `scratch/monday_vibes.py` that prints a random funny quote complaining about Mondays. Then run it in the terminal so I can laugh."*
* **Antigravity's Action:** Instantly writes the script, selects the python environment, launches the command, and prints the result:
  `"I need a coffee large enough to wash away my Monday responsibilities."`

---

## 🛠️ Essential Antigravity Slash Commands

You can use these special commands directly in the chat UI:

| Command | When to Use | Action |
|:---|:---|:---|
| `/goal` | Massive migrations / complex refactoring | Launches an autonomous mode where the agent works iteratively until the goal is fully achieved. |
| `/schedule` | Automation / cron jobs | Schedules recurring tasks (e.g., pulling latest code, running checks, compiling builds). |
| `/grill-me` | Alignment & Design | Initiates a friendly, interactive interview to align on design decisions before writing code. |

---

## 🕹️ Navigating Your Development Dashboard

Where would you like to go next? Click the buttons to load other guides:

<div align="center" style="margin: 20px 0;">
  <a href="file:///Users/bharathkumara/Desktop/guides/readme.md" style="text-decoration:none;">
    <button style="background-color:#6c5ce7; color:white; border:none; padding:10px 18px; font-size:14px; border-radius:6px; cursor:pointer; font-weight:bold; margin:5px; box-shadow: 0 2px 4px rgba(0,0,0,0.1);">
      🏠 Back to Hub
    </button>
  </a>
  <a href="file:///Users/bharathkumara/Desktop/guides/vibecoding.md" style="text-decoration:none;">
    <button style="background-color:#00b894; color:white; border:none; padding:10px 18px; font-size:14px; border-radius:6px; cursor:pointer; font-weight:bold; margin:5px; box-shadow: 0 2px 4px rgba(0,0,0,0.1);">
      🧘‍♂️ Vibe Coding Guide
    </button>
  </a>
</div>

---

### 👤 Author Details
* **Name**: Bharath Kumar A
* **GitHub**: [@bharathkumar000](https://github.com/bharathkumar000)
* **Email**: bharathece2006@gmail.com
