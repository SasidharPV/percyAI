Sure, let's document the project. Here is a structured documentation based on the files you have provided:

## Project Overview

### Project Name
Percy AI Enterprise AI

[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FSasidharPV%2FpercyAI%2Fmain%2Finfra%2Fmain.json)

### Description
This project is a solution accelerator that allows users to interact with their data using natural language queries. It leverages Azure services and various tools to process, analyze, and interact with data.

## Directory Structure

### Root Directory
-

.env.sample

: Sample environment variables file.
-

.pre-commit-config.yaml

: Configuration for pre-commit hooks.
-

azure.yaml

: Azure configuration file.
-

Makefile

: Makefile for managing tasks.
-

package-lock.json

: Lock file for npm dependencies.
-

pyproject.toml

: Configuration file for Poetry.

### Code Directory
#### Backend
- `app.py`: Entry point for the application.
- `create_app.py`: Contains the function to create the application.
- `Admin.py`: Admin app for the solution accelerator.
- `Dockerfile`: Dockerfile for the backend.
- `function_app.py`: Azure Functions app configuration.
- `host.json`: Configuration for Azure Functions host.
- `setupEnv.sh`: Script to set up the environment.
- `tasks.json`: VS Code tasks configuration.
- `extensions.json`: VS Code extensions configuration.
- `launch.json`: VS Code launch configuration.
- `settings.json`: VS Code settings configuration.

#### Utilities
- `helpers`: Contains various helper modules for interacting with Azure services, configuration, logging, etc.
- `document_chunking`: Modules for chunking documents.
- `document_loading`: Modules for loading documents.
- `embedders`: Modules for embedding documents.
- `orchestrator`: Modules for orchestrating the conversation flow.
- `parser`: Modules for parsing responses.
- `plugins`: Plugins for additional functionalities.
- `search`: Modules for searching documents.

#### API
- `chat_history.py`: API for handling chat history.
- `auth_utils.py`: Utilities for authentication.
- `cosmosdb.py`: Utilities for interacting with Cosmos DB.

#### Frontend
- `src`: Source code for the frontend application.
  - `api`: API integration for the frontend.
  - `components`: React components for the frontend.
  - `pages`: Pages for the frontend application.
  - `util`: Utility functions for the frontend.
  - `index.tsx`: Entry point for the frontend application.
  - `index.css`: Global styles for the frontend application.
  - `vite-env.d.ts`: TypeScript environment configuration.
  -

package.json

: Configuration file for npm dependencies.
  - `tsconfig.json`: TypeScript configuration file.
  - `tsconfig.node.json`: TypeScript configuration for node.

### Infra Directory
- `app`: Bicep templates for deploying the application.
- `core`: Core infrastructure components.
- `prompt-flow`: Configuration for Azure Prompt Flow.
- `workbooks`: Workbooks for monitoring and logging.

### Scripts Directory
- `generate_arm_templates.sh`: Script to generate ARM templates.
- `package_frontend.ps1`: PowerShell script to package the frontend.
- `package_frontend.sh`: Shell script to package the frontend.

## Key Components

### Configuration and Setup
- **Docker and Dev Containers**: The project uses Docker and dev containers for setting up the development environment.
- **VS Code Configuration**: The project includes configuration files for VS Code extensions, settings, tasks, and launch configurations.

### Backend Services
- **Azure Integration**: The project integrates with various Azure services such as Azure Blob Storage, Azure Search, Azure Form Recognizer, and Azure OpenAI.
- **Azure Functions**: The project uses Azure Functions to handle HTTP requests and queue triggers for processing documents and generating embeddings.

### Data Processing
- **Document Chunking and Loading**: The project includes strategies for chunking and loading documents.
- **Embedding and Search**: The project uses various embedders and search handlers to process and search documents.

### Conversation and Orchestration
- **Orchestrators**: Different orchestration strategies are implemented to handle user messages and generate responses.
- **Plugins and Tools**: Various tools and plugins are used for question answering, text processing, and post-answer validation.

### Frontend
- **Components**: The frontend includes components for displaying answers and handling user interactions.
- **API Integration**: The frontend interacts with the backend through API calls.

### Utilities and Helpers
- **Environment and Configuration**: Helper classes for managing environment variables and configuration settings.
- **Logging and Safety**: Tools for logging conversations and ensuring content safety.

## How to Run

### Prerequisites
- Docker
- Node.js
- Python 3.10+
- Poetry

### Setup
1. Clone the repository.
2. Copy

.env.sample

 to `.env` and update the environment variables.
3. Run `docker-compose up` to start the services.

### Development
- Use the provided VS Code configuration for a seamless development experience.
- Run `make` to execute tasks defined in the Makefile.

### Deployment
- Use the provided Bicep templates to deploy the infrastructure to Azure.
- Use the provided scripts to package and deploy the frontend and backend.

## Conclusion
This documentation provides an overview of the project structure, key components, and instructions for setting up and running the project.

Sure, let's go through the flow of the application step-by-step:

### 1. Environment Setup
- **Docker and Dev Containers**: The project uses Docker to create a consistent development environment. The `Dockerfile` and `devcontainer.json` files define the environment, including necessary dependencies and tools.
- **VS Code Configuration**: The project includes configuration files (`extensions.json`, `launch.json`, `settings.json`, `tasks.json`) to set up the development environment in Visual Studio Code.

### 2. Backend Services
- **Azure Functions**: The backend is built using Azure Functions, which handle HTTP requests and queue triggers for processing documents and generating embeddings. Key files include:
  - `function_app.py`: Configures the Azure Functions app.
  - `host.json`: Configures the Azure Functions host.
  - `add_url_embeddings.py`, `batch_push_results.py`, `batch_start_processing.py`, `get_conversation_response.py`: Define the functions for processing documents and handling chat requests.

### 3. Data Processing
- **Document Chunking and Loading**: The project includes various strategies for chunking and loading documents. Key files include:
  - `chunking_strategy.py`, `document_chunking_base.py`, `fixed_size_overlap.py`, `layout.py`, `page.py`, `paragraph.py`: Define different chunking strategies.
  - `document_loading_base.py`, `read.py`, `web.py`, `word_document.py`: Define different loading strategies.

- **Embedding and Search**: The project uses various embedders and search handlers to process and search documents. Key files include:
  - `embedder_base.py`, `embedder_factory.py`, `integrated_vectorization_embedder.py`, `push_embedder.py`: Define different embedding strategies.
  - `azure_search_handler.py`, `integrated_vectorization_search_handler.py`, `search_handler_base.py`, `search.py`: Define different search handlers.

### 4. Conversation and Orchestration
- **Orchestrators**: Different orchestration strategies are implemented to handle user messages and generate responses. Key files include:
  - `orchestration_strategy.py`, `orchestrator_base.py`, `open_ai_functions.py`, `lang_chain_agent.py`, `semantic_kernel.py`, `prompt_flow.py`: Define different orchestration strategies.

- **Plugins and Tools**: Various tools and plugins are used for question answering, text processing, and post-answer validation. Key files include:
  - `question_answer_tool.py`, `text_processing_tool.py`, `post_prompt_tool.py`, `chat_plugin.py`, `post_answering_plugin.py`: Define different tools and plugins.

### 5. Frontend
- **Components**: The frontend includes components for displaying answers and handling user interactions. Key files include:
  - `Answer.tsx`, `Answer.module.css`, `AnswerParser.tsx`: Define the Answer component.
  - `HistoryButton.tsx`, `HistoryButton.module.css`: Define the HistoryButton component.
  - `QuestionInput.tsx`, `QuestionInput.module.css`: Define the QuestionInput component.
  - `Spinner.tsx`, `Spinner.module.css`: Define the Spinner component.
  - `Cards.tsx`, `Cards.module.css`: Define the Cards component.
  - `Chat.tsx`, `Chat.module.css`: Define the Chat component.
  - `ChatHistoryList.tsx`, `ChatHistoryListItem.tsx`, `ChatHistoryPanel.module.css`: Define the ChatHistory components.
  - `Layout.tsx`, `Layout.module.css`: Define the Layout component.
  - `NoPage.tsx`: Define the NoPage component.

- **API Integration**: The frontend interacts with the backend through API calls. Key files include:
  - `api.ts`, `models.ts`, `index.ts`: Define the API integration.

### 6. Utilities and Helpers
- **Environment and Configuration**: Helper classes for managing environment variables and configuration settings. Key files include:
  - `env_helper.py`, `config_helper.py`: Define environment and configuration helpers.

- **Logging and Safety**: Tools for logging conversations and ensuring content safety. Key files include:
  - `conversation_logger.py`, `content_safety_checker.py`: Define logging and safety tools.

### 7. Infrastructure
- **Bicep Templates**: The project uses Bicep templates to deploy the infrastructure to Azure. Key files include:
  -

app

: Contains Bicep templates for deploying the application.
  -

core

: Contains core infrastructure components.
  -

prompt-flow

: Contains configuration for Azure Prompt Flow.
  -

workbooks

: Contains workbooks for monitoring and logging.

### 8. Scripts
- **Scripts**: The project includes scripts for generating ARM templates and packaging the frontend. Key files include:
  - `generate_arm_templates.sh`: Script to generate ARM templates.
  - `package_frontend.ps1`: PowerShell script to package the frontend.
  - `package_frontend.sh`: Shell script to package the frontend.

### Flow Summary
1. **Setup**: Set up the development environment using Docker and VS Code configurations.
2. **Backend**: Use Azure Functions to handle HTTP requests and queue triggers for processing documents and generating embeddings.
3. **Data Processing**: Chunk and load documents, then embed and search them using various strategies.
4. **Conversation**: Handle user messages and generate responses using different orchestration strategies.
5. **Frontend**: Display answers and handle user interactions using React components and API integration.
6. **Utilities**: Manage environment variables, configuration settings, logging, and content safety.
7. **Infrastructure**: Deploy the infrastructure to Azure using Bicep templates.
8. **Scripts**: Use scripts to generate ARM templates and package the frontend.

This flow provides a comprehensive overview of how the application works and how its various components interact with each other.

Sure, let's dive into the backend functions and explain each one.

### Backend Functions Overview
The backend functions are implemented using Azure Functions, which handle HTTP requests and queue triggers for processing documents and generating embeddings. These functions are defined in various Python files and are responsible for different tasks related to data processing and interaction.

### Key Backend Functions

#### 1. `add_url_embeddings.py`
This function handles the addition of URL embeddings.

- **Route**: `AddURLEmbeddings`
- **Description**: This function processes a URL provided in the request, retrieves the content from the URL, and generates embeddings for the content.
- **Key Steps**:
  1. Retrieve the URL from the request.
  2. Fetch the content from the URL.
  3. Generate embeddings for the content using the appropriate embedder.
  4. Store the embeddings in the Azure Search index.

#### 2. `batch_push_results.py`
This function handles the processing of documents from a queue.

- **Queue Trigger**: `doc-processing`
- **Description**: This function processes messages from the `doc-processing` queue, generates embeddings for the documents, and stores the results.
- **Key Steps**:
  1. Retrieve the message from the queue.
  2. Extract the document URL from the message.
  3. Generate embeddings for the document.
  4. Store the embeddings in the Azure Search index.

#### 3. `batch_start_processing.py`
This function initiates the processing of all documents in the storage.

- **Route**: `BatchStartProcessing`
- **Description**: This function retrieves all documents from the Azure Blob Storage and sends messages to the `doc-processing` queue to initiate processing.
- **Key Steps**:
  1. Retrieve all files from the Azure Blob Storage.
  2. Send a message to the `doc-processing` queue for each file.

#### 4. `get_conversation_response.py`
This function handles the generation of responses for user queries.

- **Route**: `GetConversationResponse`
- **Description**: This function processes user queries, generates responses using the appropriate orchestrator, and returns the responses.
- **Key Steps**:
  1. Retrieve the user message and conversation history from the request.
  2. Use the appropriate orchestrator to generate a response.
  3. Return the generated response to the user.

### Detailed Explanation of Each Function

#### `add_url_embeddings.py`
```python
import os
import logging
import azure.functions as func
from utilities.helpers.env_helper import EnvHelper
from utilities.helpers.embedders.embedder_factory import EmbedderFactory

bp_add_url_embeddings = func.Blueprint()
logger = logging.getLogger(__name__)
logger.setLevel(level=os.environ.get("LOGLEVEL", "INFO").upper())

@bp_add_url_embeddings.route(route="AddURLEmbeddings")
def add_url_embeddings(req: func.HttpRequest) -> func.HttpResponse:
    env_helper: EnvHelper = EnvHelper()
    logger.info("Python HTTP trigger function processed a request.")

    # Get URL from request
    url = req.get_json().get("url", None)
    if not url:
        return func.HttpResponse("Please pass a URL on the query string or in the request body", status_code=400)

    # Process URL and generate embeddings
    embedder = EmbedderFactory.create(env_helper)
    embedder.embed_file(url)

    return func.HttpResponse("URL embeddings added successfully", status_code=200)
```

#### `batch_push_results.py`
```python
import os
import logging
import json
import azure.functions as func
from utilities.helpers.env_helper import EnvHelper
from utilities.helpers.embedders.embedder_factory import EmbedderFactory

bp_batch_push_results = func.Blueprint()
logger = logging.getLogger(__name__)
logger.setLevel(level=os.environ.get("LOGLEVEL", "INFO").upper())

@bp_batch_push_results.queue_trigger(arg_name="msg", queue_name="doc-processing", connection="AzureWebJobsStorage")
def batch_push_results(msg: func.QueueMessage) -> None:
    message_body = json.loads(msg.get_body().decode("utf-8"))
    logger.debug("Process Document Event queue function triggered: %s", message_body)

    # Process document and generate embeddings
    url = message_body.get("data", {}).get("url", "")
    env_helper: EnvHelper = EnvHelper()
    embedder = EmbedderFactory.create(env_helper)
    embedder.embed_file(url)
```

#### `batch_start_processing.py`
```python
import os
import logging
import json
import azure.functions as func
from utilities.helpers.env_helper import EnvHelper
from utilities.helpers.azure_blob_storage_client import AzureBlobStorageClient

bp_batch_start_processing = func.Blueprint()
logger = logging.getLogger(__name__)
logger.setLevel(level=os.environ.get("LOGLEVEL", "INFO").upper())

@bp_batch_start_processing.route(route="BatchStartProcessing")
def batch_start_processing(req: func.HttpRequest) -> func.HttpResponse:
    logger.info("Requested to start processing all documents received")
    env_helper: EnvHelper = EnvHelper()

    # Retrieve all files from Blob Storage
    azure_blob_storage_client = AzureBlobStorageClient()
    files_data = azure_blob_storage_client.get_all_files()

    # Send messages to the queue for each file
    queue_client = create_queue_client()
    for file_data in files_data:
        queue_client.send_message(json.dumps(file_data).encode("utf-8"))

    return func.HttpResponse("Batch processing started", status_code=200)
```

#### `get_conversation_response.py`
```python
import os
import logging
import json
import azure.functions as func
from utilities.helpers.env_helper import EnvHelper
from utilities.helpers.orchestrator_helper import Orchestrator

bp_get_conversation_response = func.Blueprint()
logger = logging.getLogger(__name__)
logger.setLevel(level=os.environ.get("LOGLEVEL", "INFO").upper())

@bp_get_conversation_response.route(route="GetConversationResponse")
async def get_conversation_response(req: func.HttpRequest) -> func.HttpResponse:
    logger.info("Python HTTP trigger function processed a request.")

    # Retrieve user message and conversation history
    req_body = req.get_json()
    user_message = req_body["messages"][-1]["content"]
    conversation_id = req_body["conversation_id"]
    chat_history = req_body["messages"][:-1]

    # Generate response using orchestrator
    orchestrator = Orchestrator()
    response = await orchestrator.handle_message(user_message, chat_history, conversation_id)

    return func.HttpResponse(json.dumps(response), status_code=200)
```

These functions collectively handle the core backend processing tasks, including document ingestion, embedding generation, and conversation handling.

This repository is a solution accelerator designed to enable users to interact with their data using natural language queries. It leverages various Azure services and tools to process, analyze, and interact with data, providing a seamless experience for users to query and retrieve information from their data sources.

### Key Features and Activities

1. **Data Ingestion and Processing**:
   - The repository includes functionalities to ingest data from various sources, process it, and generate embeddings for efficient search and retrieval.
   - Documents can be chunked and loaded using different strategies to optimize processing and storage.

2. **Natural Language Interaction**:
   - Users can interact with their data using natural language queries. The system processes these queries and generates responses based on the data available.
   - The application uses various orchestration strategies to handle user messages and generate accurate responses.

3. **Search and Retrieval**:
   - The repository integrates with Azure Search to provide efficient search and retrieval capabilities.
   - Embeddings are generated for documents to enable vector-based search, improving the accuracy and relevance of search results.

4. **Frontend Application**:
   - The frontend application provides a user interface for interacting with the system. It includes components for displaying answers, handling user interactions, and managing the conversation history.
   - The frontend interacts with the backend through API calls to retrieve data and generate responses.

5. **Backend Services**:
   - The backend is built using Azure Functions, which handle HTTP requests and queue triggers for processing documents and generating embeddings.
   - Various helper modules and utilities are included to interact with Azure services, manage configuration, and ensure content safety.

6. **Infrastructure as Code**:
   - The repository includes Bicep templates for deploying the infrastructure to Azure. This ensures that the deployment process is automated and repeatable.
   - Scripts are provided to generate ARM templates and package the frontend application.

### Applications in the Repository

1. **Admin Application**:
   - The admin application provides an interface for managing the system, including configuring settings, monitoring activities, and managing data ingestion and processing.

2. **User Interaction Application**:
   - The main application allows users to interact with their data using natural language queries. It provides a conversational interface for querying data and retrieving information.

### Type of Application

This repository is a **solution accelerator** for building a **conversational AI application** that interacts with data. It combines natural language processing, search, and retrieval capabilities to provide a seamless experience for users to query and interact with their data. The application leverages various Azure services, including Azure Functions, Azure Search, Azure Form Recognizer, and Azure OpenAI, to process and analyze data, generate embeddings, and handle user queries.

### Summary

- **Purpose**: Enable users to interact with their data using natural language queries.
- **Key Features**: Data ingestion and processing, natural language interaction, search and retrieval, frontend application, backend services, infrastructure as code.
- **Applications**: Admin application for managing the system, user interaction application for querying data.
- **Type**: Conversational AI application and solution accelerator.

This repository provides a comprehensive solution for building a conversational AI application that interacts with data, leveraging the power of Azure services and tools to deliver a seamless and efficient user experience.
