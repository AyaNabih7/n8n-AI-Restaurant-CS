# 🤖 Smart Restaurant Customer Support Automation (n8n + Gemini AI)

This project is a sophisticated AI-driven Customer Support system designed for restaurants, built using **n8n**. It utilizes **Gemini 3 Flash** for natural language understanding and **RAG (Retrieval-Augmented Generation)** to provide accurate information from a local knowledge base.

## 🚀 Features
* **Intelligent Routing**: Automatically classifies user intent into General Support, Menu/Info Inquiry, or Order Placement.
* **RAG-Powered Knowledge**: Answers questions about menu items, prices, and opening hours by searching a **Supabase Vector Store**.
* **Order Management**: 
    * Collects customer details (Name, Phone, Address).
    * Calculates total prices dynamically.
    * Generates a unique 4-digit **Order ID** using a custom JavaScript node.
    * Saves all data to **Google Sheets** for real-time tracking.
* **Order Cancellation & Inquiry**: Allows customers to check their order status or cancel using their Order ID.

## 🛠️ Tech Stack
* **n8n**: Workflow automation platform.
* **Google Gemini 3 Flash**: Core LLM for decision making and conversation.
* **Supabase**: Vector database for storing restaurant documentation.
* **Google Sheets**: Database for order logs.
* **Telegram**: (Optional) Front-end interface for customer interaction.

## 📋 System Architecture
The workflow is divided into specialized "Expert" nodes to ensure high accuracy:
1.  **Generalist**: Handles greetings and basic small talk.
2.  **Questions Expert**: Connected to the knowledge base to answer specific queries about the restaurant.
3.  **Orders Expert**: Manages the full lifecycle of an order from data collection to final confirmation.

## ⚙️ Setup & Configuration
1.  **Import Workflow**: Download the `.json` file and import it into your n8n instance.
2.  **Credentials**: Set up your Google Gemini API Key and Supabase credentials.
3.  **Vector Store**: Upload your menu/info PDF/JSON to the Vector Store using `text-embedding-004` (Dimension: 768).
4.  **Google Sheets**: Create a sheet with headers: `Order ID`, `Name`, `Phone`, `Address`, `Order Items`, `Total Price`, `Status`.

---
*Developed as part of the "n8n with Karim" course implementation.*
