🤖 Conversational Chatbot API using n8n, OpenAI & PostgreSQL

📌 Overview

This project implements a webhook-based conversational chatbot API using n8n, integrated with OpenAI for intelligent responses and PostgreSQL for persistent chat storage.

The chatbot supports session-based conversations, allowing users to continue interactions seamlessly. The workflow is designed and tested in n8n and validated using Thunder Client.

⚙️ Key Features

✅ Webhook-based chatbot API

✅ Session ID generation and management

✅ OpenAI-powered conversational responses

✅ PostgreSQL-based chat memory and conversation storage

✅ Persistent multi-turn conversation tracking

✅ Tested using Thunder Client

✅ Easy to integrate with frontend or applications


🧠 How the Workflow Works

A POST request is sent via Thunder Client to the webhook.

The Session Manager:

  Checks if a sessionId exists
  
  Generates a new session ID if not provided
  
The input message is passed to the AI Agent (OpenAI model).

The response is generated using the LLM.

The conversation is stored in PostgreSQL:

Chat memory table (n8n_chat_history)

Session conversation table (chat_sessions)

The chatbot response and session ID are returned via webhook.


🔗 API Endpoint
POST /webhook/<your-webhook-id>

Request Body
{
  "chatInput": "Hello",
  "sessionId": ""
}


Response
{
  "response": "Hello! How can I assist you?",
  "sessionId": "generated_session_id"
}


📂 Workflow File
Conversational_Chatbot_With_Postgress_&_Webhook.json

Import this file into n8n to run the chatbot workflow.

🛠️ Setup Instructions

Open n8n

Import the provided JSON workflow

Configure credentials:

OpenAI API Key

PostgreSQL connection

Activate the workflow

Copy the webhook URL

Test using Thunder Client:

Method: POST

Body: JSON

Send chatInput and optional sessionId

🗄️ Database Structure

n8n_chat_history

Stores short-term conversational memory

Used by the AI agent for context

chat_sessions

Stores full conversation in JSON format

Tracks conversation turns with timestamps

💡 Use Cases

Conversational chatbot backend

AI-powered API service

Customer interaction automation

Integration with web/mobile applications

🔒 Notes

Keep API keys secure (do not expose in public repositories)

Use environment variables or n8n credentials

Ensure PostgreSQL tables are properly created before execution


👤 Author

S K Patel

Exploring Generative AI, Agentic AI, and workflow automation using n8n.


🚀 Project Focus

This project is part of hands-on learning in:

Generative AI (LLMs)

Agent-based workflows

API-driven AI applications

Automation using n8n
