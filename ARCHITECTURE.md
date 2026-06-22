# Architecture

## System Overview

This project uses Hermes as the primary AI agent and OpenClaw as the execution and integration layer.

Human User
    |
    v
  Hermes
    |
    v
 OpenClaw
    |
    v
  Slack

## Component Responsibilities

### Human User

The human interacts with the system through Slack and provides instructions, questions, and tasks.

### Hermes (Brain)

Hermes acts as the reasoning and decision-making layer.

Responsibilities:

- Understand user intent
- Maintain conversation memory
- Load and use skills
- Route requests to the appropriate model
- Manage autonomous scheduled jobs

Hermes is the Brain of the system.

### OpenClaw (Hands)

OpenClaw acts as the execution layer.

Responsibilities:

- Connect external platforms
- Receive Slack events
- Execute actions
- Deliver responses

OpenClaw is the Hands of the system.

### Slack

Slack provides the communication interface between users and the agent system.

## Model Routing

User Request
      |
      v
    Hermes
      |
      v
 Model Selection Layer
      |
      +-- Gemini 2.5 Flash
      +-- Claude
      +-- OpenAI Models

For this project, Gemini 2.5 Flash is used as the primary model.

## Memory Flow

User Message
      |
      v
    Hermes
      |
      v
 Memory Store
      |
      v
 Future Conversations

## Skill System

User Request
      |
      v
    Hermes
      |
      v
 Installed Skills
      |
      v
 Structured Response

The custom status-report skill provides:

- What I Did
- What's Left
- What Needs Your Call

## Autonomous Execution

Cron Scheduler
      |
      v
    Hermes
      |
      v
 Scheduled Task
      |
      v
 Generated Output

Hermes cron jobs enable autonomous execution without direct user interaction.
