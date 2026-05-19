# Bootcamp 1: AI Executive Assistant

#### April 2026

#### Written By:

1. **Barry Moore**

## Overview

This is an AI executive assistant using Claude Code. You'll move from setup through deployment, creating an intelligent system that handles research, calendar management, and team coordination.

## What You'll Get

By the end of this course, you'll have an AI assistant that:

1. **Saves hours** of repetitive work
2. **Learns your patterns** and never makes you repeat yourself
3. **Scales your team** by automating routine tasks
4. **Gets stuff done** with hands-on capabilities

## How We Build It

The approach has 5 phases:

1. **Build your home** — Set up the project structure
2. **Give it life** — Add context and rules so it understands you
3. **Give it hands** — Create skills and connect external tools
4. **Grow your team** — Create sub agents to do work for you
5. **Let it grow** — Use it regularly; it improves over time

## Prerequisites

Before starting, make sure you have:

- **Visual Studio Code** installed
- **Claude Code extension** for VS Code
- **Paid Anthropic plan** ($20/month minimum)
- A folder for your assistant; e.g. (optional: name it after a fictional butler... e.g. : Jeeves, Alfred, Mr. Carson from _Downton Abbey_)

```
c:/Carson
```

## Project Structure

Your assistant's folder should follow this structure:

```
Carson/
├── CLAUDE.md                    # The brain—your assistant's core instructions
├── context/
│   ├── me.md                   # About you (role, timezone, priorities)
│   ├── work.md                 # Your business and current stage
│   ├── team.md                 # Your team members
│   └── current-priorities.md   # What matters right now
├── .claude/
│   ├── rules/
│   │   └── communication-style.md
│   ├── skills/                 # Reusable workflows
│   └── agents/                 # Specialized sub-agents
├── projects/                   # Active workstreams
├── decisions/                  # Decision log
└── brand-assets/               # Logos, fonts, style guides (optional)
```

---

# Module 0: What are we building?

                         You
                          │
                          ▼
                ┌───────────────────┐
                │   Main Agent      │
                │   (orchestrator)  │
                └───────────────────┘
                   │      │      │
         reads     │      │      │ delegates
         context   │      │      ▼
                   │      │   ┌───────────────┐
                   │      │   │ Sub-Agents    │
                   │      │   │ specialists    │
                   │      │   └───────────────┘
                   │      │
                   │      └──────── uses
                   ▼
          ┌───────────────────┐
          │ Context Files     │
          │ who you are,      │
          │ what matters,     │
          │ your team, etc.   │
          └───────────────────┘

Main agent and sub-agents can also use:

┌───────────────────┐ ┌────────────────────┐
│ Skills │ │ Tools / Connectors │
│ reusable methods │◄────►│ calendar, web, │
│ for common tasks │ │ files, APIs, MCP │
└───────────────────┘ └────────────────────┘

---

# Setup & Orientation

#### 1.1 Install and Configure VS Code and Claude Code (You can skip if you already have claude code installed)

| #     | Step                                                                                                                               |
| ----- | ---------------------------------------------------------------------------------------------------------------------------------- |
| 1.1.1 | Download VS Code from [https://code.visualstudio.com](https://code.visualstudio.com) and run the installer. Accept all defaults.   |
| 1.1.2 | Open VS Code after installation completes.                                                                                         |
| 1.1.3 | Open the Extensions panel: click the square icon in the left sidebar, or press **Ctrl+Shift+X** (Windows) / **Cmd+Shift+X** (Mac). |
| 1.1.4 | Search for **"Claude Code"** in the Extensions marketplace search bar.                                                             |
| 1.1.5 | Click **Install** on the Claude Code extension published by Anthropic.                                                             |
| 1.1.6 | Once installed, click the Claude icon that appears in the left sidebar to open the Claude Code panel.                              |
| 1.1.7 | Sign in with your Anthropic account. _(Requires a paid plan — $20/month minimum.)_                                                 |
| 1.1.8 | Confirm setup is working: the chat panel should open and you should be able to type a message.                                     |

---

#### 1.2 Create Your Project Folder

| #     | Step                                                                                                                                                   |
| ----- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 1.2.1 | Create a new folder on your computer for your assistant, e.g. `C:/Carson`. (The name is up to you — some people name theirs after a fictional butler.) |
| 1.2.2 | In VS Code, go to **File > Open Folder** and select the folder you just created.                                                                       |

---

#### 1.3 Initialize Your Assistant

| #     | Step                                                                                                                                                                                         |
| ----- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1.3.1 | Open the Claude Code chat panel in the left sidebar.                                                                                                                                         |
| 1.3.2 | Open the file `EA Initialization Prompt.txt` (provided) and copy the full contents.                                                                                                          |
| 1.3.3 | Paste the prompt into the Claude Code chat panel and press **Enter**.                                                                                                                        |
| 1.3.4 | The prompt will run. It is designed to ask you a series of questions. Based on your answers, Claude Code will begin creating files. Review each one and approve the file writes as prompted. |
| 1.3.5 | Once complete, open each generated file and verify the content looks correct. Make edits if anything doesn't apply to you.                                                                   |

---

#### 1.4 Walk Through the Main Context Files

| #     | Step                                                                                                                                                                                 |
| ----- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 1.4.1 | Open `context/me.md` — Review your name, role, timezone, and a brief description of what you do. make any changes / additions as needed                                              |
| 1.4.2 | Open `context/work.md` — describe your business, product, current stage, and key tools.                                                                                              |
| 1.4.3 | Open `context/team.md` — list your team members, their roles, and how you communicate with them.                                                                                     |
| 1.4.4 | Open `context/current-priorities.md` — write the 2–4 things that matter most to you right now. Keep this updated monthly.                                                            |
| 1.4.5 | Test that your assistant has absorbed the context: type the following into the Claude Code chat panel: `"Who am I, what am I working on, and what are my top priorities right now?"` |

---

**Deliverable:** A fully initialized assistant folder, personalized context files, and a working Claude Code setup.

---
