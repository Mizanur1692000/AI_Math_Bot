Session Gemini Chatbot

A session-based AI chatbot built with Django REST Framework, LangChain, and Google Gemini. Features email-based session management for personalized conversations.

Features

Email-based session authentication

AI-powered conversations using Google Gemini
Multilingual responses (auto-detect): English (US), Español (ES), Français (FR), Deutsch (DE), 简体中文 (CN), 日本語 (JP), עברית (IL)

Conversation history per session

RESTful API architecture

LangChain integration for AI workflows

Tech Stack

Backend: Django REST Framework

AI: Google Gemini, LangChain

Session Management: Django Sessions

API: RESTful endpoints

API Endpoints

Set Email & Create Session
POST /api/set_email/
{
"email": "user@example.com"
}

Chat with AI
POST /api/chat/
{
"message": "Hello, how are you?",
"session_id": "your_session_id"
}

Setup

Clone the repository

Install dependencies: pip install -r requirements.txt

Set up environment variables:
GEMINI_API_KEY=your_gemini_api_key

Run migrations: python manage.py migrate

Start server: python manage.py runserver

Dependencies & Notes

- The project uses the latest `langchain-google-genai` which integrates Google's `google.genai` SDK. This avoids deprecation warnings from the legacy `google.generativeai` package.
- Ensure `GEMINI_API_KEY` is set in your environment (e.g., via `.env`).

Usage

First, set your email to create a session

Use the returned session_id for all chat requests

Each session maintains its own conversation history

Language Behavior

- The chatbot auto-detects the user's language from the message and replies in the same language, limited to the following locales:
	- en-US, es-ES, fr-FR, de-DE, zh-CN, ja-JP, he-IL
- If language cannot be detected or unsupported, it defaults to English (US).