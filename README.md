# E-Commerce Chatbot with LangGraph & SQLAlchemy

## Overview
This project implements an AI-powered chatbot for an e-commerce platform. The chatbot is built using **LangGraph** and integrates with an SQL database (SQLite) via **SQLAlchemy** to provide intelligent responses based on product data.

## Features
- **Conversational Product Search**: Users can ask about product availability, pricing, and recommendations.
- **SQL Query Generation & Execution**: LangGraph workflow generates, cleans, and executes SQL queries dynamically.
- **Database Integration**: Uses SQLAlchemy to interact with an SQLite product database.
- **AI-Powered Responses**: Converts raw database results into user-friendly responses using an LLM.
- **Multi-Step Processing with LangGraph**: Implements a structured workflow for handling queries efficiently.

## Installation
**1. Clone the repository:**
   ```bash
   git clone <repo-url>
   cd <repo-folder>
   ```
**2. Install dependencies:** 
   ```bash
   pip install -qU langgraph langchain-groq langchain-community sqlalchemy
   ```
**3. Set up the database:** <br>
   Ensure the `products.db` file is correctly placed in the specified path.

   ```bash
   DB_PATH = "/content/drive/MyDrive/product-database/products.db"
   DATABASE_URL = f"sqlite:///{DB_PATH}"
   ```
**4. Set Up API Key:** <br>
   Ensure you have a Groq API key and store it securely. The project retrieves the key from Google Drive.

   ```bash
   from google.colab import userdata
   GROQ_API_KEY = userdata.get('GROQ_API_KEY')
   ```
## Model & Database
- **LLM**: Uses `llama3-70b` via the Groq API.
- **Database**: SQLite database (`products.db`) containing e-commerce product details.

## Workflow
**1. User Input:** Accepts a natural language query. <br>
**2. SQL Query Generation:** LangGraph generates a corresponding SQL query. <br>
**3. Query Cleaning:** Ensures SQL syntax is valid. <br>
**4. Query Execution:** Runs the SQL query on the product database. <br>
**5. Response Generation:** Converts the query result into a user-friendly response. <br>

## Repository Structure

```bash
ecommerce-chatbot/
│
├── ecommerce_chatbot.ipynb
├── products.db
└── README.md
```
