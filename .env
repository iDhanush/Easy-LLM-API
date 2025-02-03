import os
from llmware.models import ModelCatalog
from typing import Union
from pydantic import BaseModel
from fastapi import FastAPI, HTTPException
from fastapi.middleware.cors import CORSMiddleware
from dotenv import load_dotenv
import nest_asyncio
from pyngrok import ngrok
import uvicorn

# Load environment variables
load_dotenv()

NGROK_AUTH_TOKEN = os.getenv("NGROK_AUTH_TOKEN")
NGROK_HOSTNAME = os.getenv("NGROK_HOSTNAME")
MODEL_NAME = os.getenv("MODEL_NAME", "bartowski/Meta-Llama-3-8B-Instruct-GGUF")

# Load the model
model = ModelCatalog().load_model(MODEL_NAME)

app = FastAPI()
app.add_middleware(
    CORSMiddleware,
    allow_origins=['*'],
    allow_credentials=True,
    allow_methods=['*'],
    allow_headers=['*'],
)

def get_response(prompt: str, context: Union[None, str] = ""):
    response = model.inference(prompt, add_context=context)
    return response

class ChatRequest(BaseModel):
    prompt: str
    context: Union[str, None] = None

@app.post("/chat")
async def chat_endpoint(chat_request: ChatRequest):
    try:
        result = get_response(chat_request.prompt, chat_request.context)
        return result
    except ValueError as e:
        raise HTTPException(status_code=500, detail=str(e))

# Set the authtoken
if NGROK_AUTH_TOKEN:
    ngrok.set_auth_token(NGROK_AUTH_TOKEN)

# Connect to ngrok
ngrok_tunnel = ngrok.connect(8000, hostname=NGROK_HOSTNAME)
print('Public URL:', ngrok_tunnel.public_url)

# Apply nest_asyncio
nest_asyncio.apply()

# Run the uvicorn server
uvicorn.run(app, port=8000)
