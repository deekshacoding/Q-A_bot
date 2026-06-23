# 🤖 Groq-Powered Q&A Bot

A fast and intelligent Question & Answer chatbot built with **Python** and the **Groq API**. This project allows users to ask questions in natural language   

## 🚀 Features
 
* ⚡ Powered by Groq API
* 🧠 Natural Language Question Answering
* 🐍 Built with Python
* 🔒 Environment Variable Support for API Keys
* 📦 Lightweight and Easy to Deploy
* 🖥️ Command-Line Interface (CLI)
* 🔄 Easy Integration with Web Apps (Flask, FastAPI, Streamlit)

---

## 📂 Project Structure

```bash
chatbot.py

chatbot_memory.py

chatbot_stream.py
```

---

## 🛠️ Installation

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/qa-bot.git
cd qa-bot
```

### 2. Create Virtual Environment

```bash
python -m venv venv
```

Activate the environment:

**Windows**

```bash
venv\Scripts\activate
```

**Linux/Mac**

```bash
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

---

## 📦 Required Packages

Add the following to your `requirements.txt`:

```txt
groq
python-dotenv
```

Install manually:

```bash
pip install groq python-dotenv
```

---

## 🔑 Configure Groq API Key

Create a `.env` file in the project root:

```env
GROQ_API_KEY=your_groq_api_key_here
```

Get your API key from:

https://console.groq.com/

---

## 💻 Example Code

```python
from groq import Groq
from dotenv import load_dotenv
import os

load_dotenv()

client = Groq(
    api_key=os.getenv("GROQ_API_KEY")
)

while True:
    question = input("You: ")

    if question.lower() in ["exit", "quit"]:
        print("Goodbye!")
        break

    response = client.chat.completions.create(
        model="llama-3.3-70b-versatile",
        messages=[
            {
                "role": "user",
                "content": question
            }
        ]
    )

    print("Bot:", response.choices[0].message.content)
```

---

## ▶️ Run the Application

```bash
python app.py
```

Example:

```text
You: What is machine learning?

Bot: Machine learning is a branch of artificial intelligence that enables computers to learn patterns from data and improve performance without being explicitly programmed.
```

---

## 🔧 Customization

You can easily extend this project by:

* Adding chat history
* Integrating Streamlit UI
* Building a Flask/FastAPI backend
* Connecting to a database
* Implementing Retrieval-Augmented Generation (RAG)
* Uploading and querying PDF documents
* Deploying on Render, Railway, or AWS

---

## 📈 Future Improvements

* User Authentication
* Conversation Memory
* Multi-Model Support
* Voice Input & Output
* Document-Based Q&A
* Web Search Integration
* API Endpoint Support

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome.

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to your branch
5. Open a Pull Request

---

## 📄 License

This project is licensed under the MIT License.

---

## ⭐ Support

If you found this project helpful, please consider giving it a ⭐ on GitHub.

Happy Coding! 🚀
