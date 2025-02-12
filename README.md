# 🚀 Chatbot with MySQL using LangChain, LangSmith, and LangServe  

## **Overview**  
This project is a **multi-LLM-powered chatbot** built using **LangChain** that integrates with **MySQL** for data storage. It leverages **LangSmith** for observability and **LangServe** for serving the chatbot as an API.  

The chatbot supports **multiple LLMs**, allowing users to choose their preferred model, including:
- OpenAI (GPT models)  
- Groq  
- Google Cloud Gemini  
- And many more!  

Additionally, the system **tracks input/output tokens and cost usage** for every interaction, ensuring transparency and efficient cost management.  

---

## **Features**  
✅ Supports **multiple LLMs** – choose OpenAI, Groq, Gemini, and more.  
✅ Utilizes **MySQL** for persistent conversation history and data management.  
✅ Integrates **LangChain** for seamless orchestration.  
✅ Uses **LangSmith** to track and debug interactions.  
✅ Serves the chatbot via **LangServe** API.  
✅ **Tracks token usage and cost** for better monitoring.  

---

## **Tech Stack**  
- **Backend**: Python, FastAPI (via LangServe)  
- **LLM Framework**: LangChain  
- **LLM Providers**: OpenAI, Groq, Google Gemini, etc.  
- **Database**: MySQL  
- **Observability**: LangSmith  
- **Containerization**: Docker (optional)  

---

## **Setup & Installation**  

### **1️⃣ Clone the Repository**  
```sh
git clone https://github.com/your-username/chatbot-mysql-langchain.git
cd chatbot-mysql-langchain
```

### **2️⃣ Install Dependencies**  
Make sure you have **Python 3.9+** installed, then run:  
```sh
pip install -r requirements.txt
```

### **3️⃣ Configure MySQL Database**  
Create a MySQL database and update the `config.py` file with your database credentials. Example:  

```python
MYSQL_HOST = "your-mysql-host"
MYSQL_USER = "your-username"
MYSQL_PASSWORD = "your-password"
MYSQL_DB = "your-database"
```

### **4️⃣ Set Up API Keys**  
Export your API keys for LLM providers:  
```sh
export OPENAI_API_KEY="your-openai-api-key"
export GROQ_API_KEY="your-groq-api-key"
export GEMINI_API_KEY="your-gemini-api-key"
```

Or create a **.env** file:  
```ini
OPENAI_API_KEY=your-openai-api-key
GROQ_API_KEY=your-groq-api-key
GEMINI_API_KEY=your-gemini-api-key
```

### **5️⃣ Run the Chatbot Server**  
```sh
python app.py
```
Or using **LangServe**:  
```sh
langserve run chatbot:Chatbot
```

---

## **Usage**  
You can interact with the chatbot through the **API endpoint**:  

### **Example API Request (FastAPI / LangServe)**  
```sh
curl -X POST "http://localhost:8000/chat" \
     -H "Content-Type: application/json" \
     -d '{"query": "Hello, how can you help me?", "llm": "openai"}'
```

Or open `http://localhost:8000/docs` in your browser to access the FastAPI Swagger UI.

---

## **Tracking Token Usage & Cost**  
Every interaction is logged to track:  
- **Input tokens**  
- **Output tokens**  
- **Total cost**  

### **Example Log Entry:**  
```json
{
    "query": "What is LangChain?",
    "response": "LangChain is a framework for developing applications powered by large language models.",
    "input_tokens": 10,
    "output_tokens": 15,
    "total_cost": "$0.0025"
}
```

---

## **Contributing**  
Contributions are welcome! Feel free to fork the repository and submit a pull request.  

---

## **License**  
This project is licensed under the **MIT License**.

