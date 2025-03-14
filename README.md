GPT-2 Chatbot API

Overview

This is a simple AI chatbot API built using FastAPI and the GPT-2 model from Hugging Face's Transformers library. The chatbot generates text based on a given prompt and returns up to 50 characters of generated text.

Features

FastAPI-based backend

GPT-2 text generation

Dockerized application

CI/CD pipeline with GitHub Actions

Nginx reverse proxy for deployment

Installation

1. Clone the Repository

git clone 
cd <repository_directory>

2. Install Dependencies

If you are running locally, install the required Python libraries:

pip install -r requirements.txt

3. Running the Application

Using FastAPI Directly

Run the FastAPI server locally:

uvicorn app:app --host 0.0.0.0 --port 8000

Using Docker

To build and run the application in a Docker container:

docker build -t gpt2-chatbot .
docker run -p 8000:8000 gpt2-chatbot

API Endpoints

1. Generate Text

Endpoint:

POST /generate/

Request Body:

{
  "prompt": "what is google",
  "max_length": 50
}

Response:

{
  "response": "Google is a search engine that..."
}

2. Health Check

Endpoint:

GET /

Response:

{
  "message": "GPT-2 API is running!"
}

Testing the API

To test the chatbot API, you can use curl:

curl -X POST "http://9.169.175.161/generate/" -H "Content-Type: application/json" -d '{"prompt": "What is AI?"}'

Deployment

The chatbot is deployed on a remote Ubuntu server using Docker and Nginx as a reverse proxy.

Future Enhancements

Upgrade model to GPT-J or Mistral 7B.

Implement Kubernetes for auto-scaling.

Enable HTTPS with Let's Encrypt.

Add monitoring with Prometheus & Grafana.

License

This project is open-source under the MIT License.

Author

Developed by Abdul Rehman.
tt
