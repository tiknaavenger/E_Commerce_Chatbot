<h2 align="center">🛒 E-commerce Chat Bot</h2>

<p align="center"><b>An AI-powered shopping assistant that helps users discover products, ask FAQs, and chat naturally — all in a clean Streamlit UI. The bot routes each message to the best handler (FAQ, SQL, or Small Talk) and responds fast using a mix of semantic search (RAG), LLM reasoning (Groq Llama 3.3), and a local SQLite database for product lookups.</b></p>

<p align="center">
  <a href="https://www.trychroma.com/"><img alt="ChromaDB" src="https://img.shields.io/badge/🟣%20ChromaDB-1.0.16-9333ea?logo=databricks&logoColor=white"></a>
  <a href="https://groq.com/"><img alt="Groq" src="https://img.shields.io/badge/⚡%20Groq-0.30.0-facc15?logo=lightning&logoColor=black"></a>
  <a href="https://pandas.pydata.org/"><img alt="pandas" src="https://img.shields.io/badge/🐼%20pandas-2.3.1-150458?logo=pandas&logoColor=white"></a>
  <a href="https://pypi.org/project/python-dotenv/"><img alt="python-dotenv" src="https://img.shields.io/badge/🌱%20python--dotenv-1.1.1-22c55e?logo=.env&logoColor=white"></a>
  <a href="https://github.com/aurelio-labs/semantic-router"><img alt="Semantic Router" src="https://img.shields.io/badge/🔀%20semantic__router-0.1.11-2563eb?logo=github&logoColor=white"></a>
  <a href="https://streamlit.io/"><img alt="Streamlit" src="https://img.shields.io/badge/📊%20Streamlit-1.45.1-ff4b4b?logo=streamlit&logoColor=white"></a>
  <a href="https://www.sbert.net/"><img alt="Sentence Transformers" src="https://img.shields.io/badge/📝%20Sentence--Transformers-5.0.0-8b5cf6?logo=transformers&logoColor=white"></a>
  <a href="https://pypi.org/project/pysqlite3-binary/"><img alt="pysqlite3-binary" src="https://img.shields.io/badge/🗄️%20pysqlite3--binary-0.5.4-0f766e?logo=sqlite&logoColor=white"></a>
</p>


---

## Why this project?
Most e-commerce search bars only accept rigid filters. This project lets shoppers ask in plain language (e.g., “show me running shoes under ₹2000 with 500+ reviews”) and get relevant, explainable results. On top of product search, it also answers store FAQs (returns, shipping, warranty) and keeps the conversation friendly with small talk.

---

## ✨ Key Features

* **Intent-aware chat** via a **Semantic Router** that classifies each message into:
  * _faq_ → platform/policy questions (answered with RAG)
  * _sql_ → structured product search (answered via SQLite)
  * _smalltalk_ → friendly, general conversation
* **RAG** for FAQs using **ChromaDB** + **Sentence Transformers**.
* **Natural language** → SQL: converts user requests into SQL and executes on a local SQLite database.
* **Streamlit UI:** dynamic responses with product listings, FAQs, or small talk.
* **Zero external backend** — everything runs locally.
* **Config via** .env: easily switch API keys or models.

---

## 💻 Tech Stack
* **Frontend/UI:** Streamlit
* **LLM Runtime:** Groq (Llama-3.3-70B-versatile)
* **Vector Store:** ChromaDB
* **Embeddings:** Sentence Transformers
* **Router:** semantic_router
* **Database:** SQLite (built from CSV)
* **Data Handling:** pandas
* **Environment:** python-dotenv

---


## 🚀 Launch App

[https://ecommerce-chat-assistant.streamlit.app/](https://ecommerce-chat-assistant.streamlit.app/)

<img src="app/resources/Project%20Screenshot%201.JPG" alt="App Screenshot" width="600">

<img src="app/resources/Project%20Screenshot%202.JPG" alt="App Screenshot" width="600">


### Installation Steps

1. **Clone the Repository**

   ```bash
   git clone https://github.com/MindMatrixPro/E_Commerce_Chatbot.git
   cd "E-Commerce Chat bot"
   ```

2. **Install Dependencies**

   ```bash
   pip install -r requirements.txt
   ```

3. **Install Dependencies**

   ```bash
   GROQ_API_KEY=your_api_key_here
   GROQ_MODEL=llama-3.3-70b-versatile
   ```

4. **Run the Streamlit App**

   ```bash
   streamlit run app/main.py
   ```

---

## ⚙️ How It Works

**🔹 Intent Detection (Semantic Router)**
* Every user message is first passed through the Semantic Router, which identifies what type of request it is. Queries are sorted into three intent categories:
  * FAQ → questions about policies, returns, and general platform info
  * SQL → product searches that rely on structured database queries
  * Small Talk → light, conversational inputs for engagement

**🔹 Routing Logic**
* **FAQ Handling** → Uses ChromaDB with Sentence Transformers to perform semantic search across stored FAQs, returning accurate answers through a RAG pipeline.
* **SQL Handling** → Translates natural language into SQL commands, runs them against the SQLite product database, and fetches relevant results.
* **Small Talk** → Generates simple, human-like responses to casual or non-technical messages.

**🔹 Streamlit Response Layer**
* **SQL Queries** → Show product cards/tables with names, prices, ratings, and links.
* **FAQ Queries** → Deliver clear answers backed by FAQ data stored in CSV files.
* **Small Talk Queries** → Respond in a conversational style to keep the chat engaging.

---

## Contributing

To Contribute, please submit issues or pull requests for enhancements or fixes.

---

## License

Licensed under the Apache 2.0 License.

---
