# Full Stack RAG Application with Chat History

This repository contains a Full Stack Retrieval-Augmented Generation (RAG) application with chat history functionality. Below are the step-by-step instructions to set up and run the application.

# Prerequisites

### Ensure the following tools are installed on your machine before proceeding:
•	Poetry (for managing Python dependencies)

•	Node.js (for running the frontend)

•	PostgreSQL and pgvector extension (for database management)

# Getting Started
1. Clone the Repository
   
```bash
git clone https://github.com/TechnoNexus/rag-with-chat-history.git
```
```bash
cd rag-with-chat-history
```

Alternatively, you can download the repository as a zip file and extract it.

## Organize Project Files

Create a backend folder and move all the files to backend folder (make it root).

```bash
mkdir backend
```

## Install Backend Dependencies

Navigate to the backend folder and install the Python dependencies using Poetry.

```bash
cd backend
```
```bash
poetry install
```
## Install Frontend Dependencies

Move into the frontend directory and install the required Node.js packages.

```bash
cd ../frontend
```
```bash
npm install
```

## Set Up PostgreSQL (If Not Installed)

If PostgreSQL is not installed, follow these steps to install and set up the database:

a. Install PostgreSQL and Start the Service (macOS using Homebrew):

```bash
brew install postgresql
```
```bash
brew services start postgresql
```

b. Install pgvector Extension:

```bash
brew install pgvector
```

c. Create Required Databases:

```bash
createdb mydatabase
```
```bash
psql -U postgres
```
```sql
CREATE DATABASE database164;
```
```sql
CREATE DATABASE pdf_rag_history;
```
```sql
\q
```
```bash
psql -d database164 -c "CREATE EXTENSION vector;"
```

## Configure Environment Variables

In the backend folder, create a '.env' file to store your API keys and other environment variables.

Add the following keys to your .env file, replacing YOUR_KEY with your actual API keys:

```bash
OPENAI_API_KEY=YOUR_KEY
LANGCHAIN_API_KEY=YOUR_KEY
LANGCHAIN_ENDPOINT=https://api.smith.langchain.com
LANGCHAIN_PROJECT=RAG with Chat History
```

## Run the Backend

In the backend folder, start the backend service with the following command:

```bash
poetry run langchain serve
```

## Run the Frontend

In the frontend folder, start the frontend by running:

```bash
npm start
```

## Access the Application

Once both the backend and frontend are running, open your browser and navigate to http://localhost:3000 to interact with the application.

