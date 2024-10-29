# LangChain Graph Chatbot with Arxiv and Wikipedia Integration

This project is a chatbot application built using **LangChain** and **LangGraph**, designed to retrieve real-time information from **Wikipedia** and **Arxiv**. With the help of **ChatGroq**, it enhances responses using contextual data, making it suitable for answering questions on academic topics or general knowledge.

## Features

- **Wikipedia and Arxiv Integration**: Provides accurate responses using up-to-date information.
- **Event-Based Chatbot Flow**: Utilizes **LangGraph** to create a state-based, conditional graph for conversational flow.
- **Powered by ChatGroq LLM**: Uses **ChatGroq** for natural language processing and response generation.

## Setup Instructions

1. **Open the Colab Notebook**: Access the notebook from GitHub: [LANG_GRAPH_CHATBOT GitHub Repository](https://github.com/DarshanG12/LANG_GRAPH_CHATBOT.git).

2. **Install Dependencies**:
   - Install packages listed in `requirements.txt`:
     ```bash
     pip install -r requirements.txt
     ```
   - Or, if in Google Colab:
     ```python
     !pip install langgraph langsmith langchain langchain_groq langchain_community arxiv wikipedia
     ```

## Setting Up the Environment

To use **ChatGroq**, set up your Groq API key in Colab:

```python
from google.colab import userdata
groq_api_key = userdata.get("groq_api_key")
```

Usage
Initialize Tools: Configure ArxivAPIWrapper and WikipediaAPIWrapper to retrieve top results.

Run the Chatbot: Define user inputs and process them through the graph. For example:

```python
user_input = "What is data science?"
events = graph.stream(
    {"messages": [("user", user_input)]},
    stream_mode="values"
)
for event in events:
    event["messages"][-1].pretty_print()
```
Dependencies
LangChain, LangGraph, LangChain Community: Provides tooling and state graph flow.
Arxiv, Wikipedia: For data retrieval from academic and general knowledge sources.
ChatGroq: Processes input and generates responses based on groq_api_key

