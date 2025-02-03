# Easy LLM API

Easy LLM API allows you to quickly deploy any open-source Large Language Model (LLM) with optimized performance using platforms like Kaggle or Google Colab. This is perfect for projects like hackathons, where you need an instant and efficient LLM deployment.

## Features
- Run any open-source LLM easily.
- Supports platforms like Kaggle and Google Colab for seamless execution.
- Provides an API endpoint to interact with the model.
- Uses Ngrok for instant public access.
- Built with FastAPI for high performance.
- CORS enabled for flexible integrations.

## Quick Start

### Run on Kaggle  
Click the button below to open and run the notebook on Kaggle:

[![Run in Kaggle](https://kaggle.com/static/images/open-in-kaggle.svg)](https://www.kaggle.com/code/idhanush/easy-llm-api)

### Run on Google Colab  
Click the button below to run the notebook on Google Colab:

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/iDhanush/Easy-LLM-API/blob/main/EASY_LLM_API.ipynb)

## Installation

1. Clone this repository:
   ```sh
   git clone https://github.com/{YOUR_GITHUB_USERNAME}/easy-llm-api.git
   cd easy-llm-api
   ```

2. Install dependencies:
   ```sh
   pip install -r requirements.txt
   ```

3. Run the API locally:
   ```sh
   python main.py
   ```

## API Usage

### Chat Endpoint
**POST /chat**

#### Request Body:
```json
{
    "prompt": "Hello, how are you?",
    "context": ""
}
```

#### Response:
```json
{
    "response": "I am fine, how can I assist you?"
}
```

## TODO List (Enhancements & Features)
- [ ] Support for additional LLM models.
- [ ] Implement model selection via API request.
- [ ] Add authentication for API access.
- [ ] Optimize inference speed with quantization.
- [ ] Provide WebSocket support for real-time chat.
- [ ] Add a front-end UI for easier interaction.
- [ ] Deploy on cloud platforms (AWS, GCP, Azure).
- [ ] Enable multi-user handling for production use.
- [ ] Enhance logging and monitoring.
- [ ] Improve documentation with example use cases.

## License
This project is licensed under the MIT License.

