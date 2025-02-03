# Easy LLM API

## Overview
Easy LLM API is a simple and efficient way to deploy open-source language models as an API using [LLMWare](https://pypi.org/project/llmware/). It provides an easy-to-use framework to load, process, and serve models with minimal configuration.

## Features
- Load and serve open-source LLMs easily
- API-based interaction with the models
- Supports text generation, summarization, and question-answering
- Lightweight and customizable deployment

## Customization
- **Model Selection:** Modify `ModelCatalog().load_model("your-model-name")` to use different models.
- **Advanced Configurations:** Use `LLMWare`'s configurations for fine-tuning parameters.
- **Scaling:** Deploy with Docker or integrate with cloud platforms for scalability.

# Easy LLM API Documentation  

## Overview  
Easy LLM API enables you to create and deploy an LLM-powered chatbot using open-source models via **LLMWare**.

## Installation  
Ensure you have the required dependencies:  
```bash
pip install fastapi pydantic uvicorn llmware
```

## Endpoints  

### **1. Chat Endpoint**  
**URL:** `/chat`  
**Method:** `POST`  
**Description:** Generates a response from the LLM based on the given prompt and optional context.  

#### Request Body:  
```json
{
  "prompt": "Hello, how are you?",
  "context": "Casual conversation"
}
```

#### Response:  
```json
{
  "response": "I'm good! How can I assist you today?"
}
```

## Usage  
Run the FastAPI server:  
```bash
uvicorn main:app --host 0.0.0.0 --port 8000
```

## Error Handling  
- Returns **500 Internal Server Error** for inference failures.  

🚀 **Ready to build AI-powered apps easily with open-source models!**

