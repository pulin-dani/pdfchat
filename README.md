# Chat with Multiple PDFs Application
This repository contains a Streamlit application that allows users to upload multiple PDF documents, process their text, and interact with the content using an AI-powered conversational interface.

## Introduction

This application leverages Streamlit, Langchain, Qdrant, and OpenAI to enable users to upload and interact with multiple PDF documents. It processes the text content from the PDFs, stores it in a vector database (Qdrant), and uses a conversational AI model to answer user questions based on the document content.

### Install a Virtual Environment
Install the virtual Environment library, if already not available:
```
sudo apt-get install python3-venv
```

### Creating a Virtual Environment

It is recommended to use a virtual environment to manage dependencies. You can create and activate a virtual environment using the following commands:

```bash
# Create a virtual environment
python3.9 -m venv venv

# Activate the virtual environment
source venv/bin/activate
```
## Environment Variables
Create a **.env** file in the root directory of your project and add your OpenAI API key:
```
OPENAI_API_KEY=your_openai_api_key
```
## Installing Dependencies
After activating the virtual environment, install the required dependencies using the **requirements.txt** file:

```
pip install -r requirements.txt
```

## Run Qdrant Container
Run the following command to run the container of Qdrant vector database:
```
docker run -p 6333:6333 -p 6334:6334 -d -v $(pwd)/qdrant_storage:/qdrant/storage:z qdrant/qdrant

```

## Creating a Docker Image
To containerize the application, execute the following command in the directory where the Dockerfile is located:
```
docker build -t chat-with-pdfs .
```

## Running the Docker Container
Run the Docker container using the following command:
```
docker run -p 8501:8501 --env-file .env chat-with-pdfs
```
Now, open the browser and type **localhost:8501**, and you can interact with the app.
##### Author
- Jazay Ahmad
