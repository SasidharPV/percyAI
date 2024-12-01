Sure, let's update the POC document with the new project name "Percy AI" from Percy Solutions.

---

# Proof of Concept (POC) Document

## Project Overview

### Project Name
Percy AI

### Description
Percy AI, developed by Percy Solutions, is a solution accelerator designed to enable enterprise employees to interact with their data using natural language queries. It leverages various Azure services and tools to process, analyze, and interact with data, providing a seamless experience for users to query and retrieve information from their data sources.

## Objectives

- **Enable Natural Language Interaction**: Allow users to interact with their data using natural language queries.
- **Efficient Data Processing**: Ingest, process, and generate embeddings for data to enable efficient search and retrieval.
- **Seamless User Experience**: Provide a user-friendly interface for querying data and retrieving information.
- **Scalable and Extensible**: Use Azure services to ensure scalability and extensibility of the solution.

## Key Features

1. **Data Ingestion and Processing**:
   - Ingest data from various sources.
   - Process and chunk documents using different strategies.
   - Generate embeddings for efficient search and retrieval.

2. **Natural Language Interaction**:
   - Process user queries and generate responses based on available data.
   - Use various orchestration strategies to handle user messages.

3. **Search and Retrieval**:
   - Integrate with Azure Search for efficient search and retrieval.
   - Use vector-based search to improve accuracy and relevance of search results.

4. **Frontend Application**:
   - Provide a user interface for interacting with the system.
   - Display answers, handle user interactions, and manage conversation history.

5. **Backend Services**:
   - Use Azure Functions to handle HTTP requests and queue triggers.
   - Include helper modules and utilities for interacting with Azure services and managing configuration.

6. **Infrastructure as Code**:
   - Use Bicep templates for deploying the infrastructure to Azure.
   - Provide scripts for generating ARM templates and packaging the frontend application.

## Architecture

### High-Level Architecture

1. **Frontend**:
   - React-based application for user interaction.
   - Components for displaying answers, handling user inputs, and managing conversation history.

2. **Backend**:
   - Azure Functions for processing requests and generating embeddings.
   - Helper modules for interacting with Azure services and managing configuration.

3. **Data Processing**:
   - Document chunking and loading strategies.
   - Embedding generation and search handlers.

4. **Infrastructure**:
   - Bicep templates for deploying Azure resources.
   - Scripts for automating deployment and packaging.

### Detailed Components

1. **Frontend Components**:
   - `Answer.tsx`, `Answer.module.css`, `AnswerParser.tsx`
   - `HistoryButton.tsx`, `HistoryButton.module.css`
   - `QuestionInput.tsx`, `QuestionInput.module.css`
   - `Spinner.tsx`, `Spinner.module.css`
   - `Cards.tsx`, `Cards.module.css`
   - `Chat.tsx`, `Chat.module.css`
   - `ChatHistoryList.tsx`, `ChatHistoryListItem.tsx`, `ChatHistoryPanel.module.css`
   - `Layout.tsx`, `Layout.module.css`
   - `NoPage.tsx`

2. **Backend Functions**:
   - `add_url_embeddings.py`
   - `batch_push_results.py`
   - `batch_start_processing.py`
   - `get_conversation_response.py`

3. **Data Processing**:
   - `chunking_strategy.py`, `document_chunking_base.py`, `fixed_size_overlap.py`, `layout.py`, `page.py`, `paragraph.py`
   - `document_loading_base.py`, `read.py`, `web.py`, `word_document.py`
   - `embedder_base.py`, `embedder_factory.py`, `integrated_vectorization_embedder.py`, `push_embedder.py`
   - `azure_search_handler.py`, `integrated_vectorization_search_handler.py`, `search_handler_base.py`, `search.py`

4. **Orchestration**:
   - `orchestration_strategy.py`, `orchestrator_base.py`, `open_ai_functions.py`, `lang_chain_agent.py`, `semantic_kernel.py`, `prompt_flow.py`
   - `question_answer_tool.py`, `text_processing_tool.py`, `post_prompt_tool.py`, `chat_plugin.py`, `post_answering_plugin.py`

5. **Infrastructure**:
   - Bicep templates in 

app

, 

core

, 

prompt-flow

, 

workbooks


   - Scripts in 

scripts



## Implementation Plan

### Phase 1: Setup and Configuration
- Set up the development environment using Docker and VS Code configurations.
- Configure environment variables and secrets.

### Phase 2: Data Ingestion and Processing
- Implement data ingestion and processing functions.
- Configure document chunking and loading strategies.
- Generate embeddings for documents.

### Phase 3: Natural Language Interaction
- Implement orchestration strategies for handling user queries.
- Integrate with Azure OpenAI for generating responses.

### Phase 4: Search and Retrieval
- Integrate with Azure Search for efficient search and retrieval.
- Implement vector-based search for improved accuracy.

### Phase 5: Frontend Development
- Develop React components for user interaction.
- Implement API integration for querying data and retrieving responses.

### Phase 6: Deployment
- Use Bicep templates to deploy the infrastructure to Azure.
- Use scripts to generate ARM templates and package the frontend application.

## Conclusion

This Proof of Concept (POC) document outlines the objectives, key features, architecture, and implementation plan for "Percy AI" from Percy Solutions. The solution leverages Azure services and tools to provide a seamless experience for enterprise employees to interact with their data using natural language queries. The implementation plan ensures a structured approach to developing and deploying the solution, making it scalable and extensible.

---


### Phase 1: Setup and Configuration

#### Objective
Set up the development environment to ensure all necessary tools and dependencies are installed and configured correctly. This phase ensures that developers have a consistent and functional environment to work on the project.

#### Steps

1. **Clone the Repository**
   - Clone the repository to your local machine using the following command:
     ```sh
     git clone <repository-url>
     cd <repository-directory>
     ```

2. **Set Up Environment Variables**
   - Copy the sample environment variables file and update it with your specific values:
     ```sh
     cp .env.sample .env
     ```
   - Edit the `.env` file to include the necessary environment variables. These variables include Azure service keys, connection strings, and other configuration settings.

3. **Docker and Dev Containers**
   - Ensure Docker is installed on your machine. You can download and install Docker from [here](https://www.docker.com/products/docker-desktop).
   - Build and run the Docker containers using the provided `docker-compose.yml` file:
     ```sh
     docker-compose up
     ```
   - This will set up the development environment using Docker, including all necessary dependencies and tools.

4. **VS Code Configuration**
   - Open the project in Visual Studio Code.
   - Install the recommended extensions by clicking on the notification that appears when you open the project.
   - The project includes configuration files for VS Code:
     - `extensions.json`: Recommended extensions for the project.
     - `launch.json`: Configurations for debugging the application.
     - `settings.json`: Project-specific settings for VS Code.
     - `tasks.json`: Tasks for building and running the application.

5. **Install Python Dependencies**
   - Ensure Python 3.10+ is installed on your machine. You can download and install Python from [here](https://www.python.org/downloads/).
   - Install Poetry, a dependency management tool for Python:
     ```sh
     curl -sSL https://install.python-poetry.org | python3 -
     ```
   - Install the Python dependencies using Poetry:
     ```sh
     poetry install
     ```

6. **Install Node.js Dependencies**
   - Ensure Node.js is installed on your machine. You can download and install Node.js from [here](https://nodejs.org/).
   - Navigate to the `frontend` directory and install the Node.js dependencies:
     ```sh
     cd code/frontend
     npm install
     ```

7. **Set Up Azure Services**
   - Ensure you have an Azure account and the necessary permissions to create resources.
   - Use the provided Bicep templates to deploy the required Azure resources. This includes Azure Functions, Azure Search, Azure Blob Storage, and other services.
   - Deploy the infrastructure using the following command:
     ```sh
     az deployment group create --resource-group <resource-group-name> --template-file infra/main.bicep --parameters @infra/main.bicepparam
     ```

8. **Configure Azure Functions**
   - Ensure the Azure Functions Core Tools are installed on your machine. You can download and install them from [here](https://docs.microsoft.com/en-us/azure/azure-functions/functions-run-local).
   - Start the Azure Functions host locally:
     ```sh
     func start
     ```

9. **Run the Frontend Application**
   - Navigate to the `frontend` directory and start the development server:
     ```sh
     cd code/frontend
     npm run dev
     ```

10. **Verify the Setup**
    - Open your browser and navigate to the frontend application (usually at `http://localhost:3000`).
    - Verify that the application loads correctly and that you can interact with it.
    - Test the backend functions by sending requests to the Azure Functions endpoints and verifying the responses.

### Conclusion
Phase 1 ensures that the development environment is set up correctly, with all necessary tools and dependencies installed and configured. This phase provides a consistent and functional environment for developers to work on the project, enabling them to proceed with the subsequent phases of development.

---
Let's go through the process of generating the Dockerfile for the frontend and how to update it if changes are made to the frontend application.

### Generating the Dockerfile for the Frontend

The Dockerfile for the frontend is designed to build and package the frontend application using Node.js and then serve it using a Python-based server. Here is the existing Dockerfile for the frontend:

#### Existing Dockerfile (`docker/Frontend.Dockerfile`)
```dockerfile
FROM node:20-alpine AS frontend
RUN mkdir -p /home/node/app/node_modules && chown -R node:node /home/node/app
WORKDIR /home/node/app
COPY ./code/frontend/package*.json ./
USER node
RUN npm ci
COPY --chown=node:node ./code/frontend ./frontend
WORKDIR /home/node/app/frontend
RUN npm run build

FROM python:3.11.7-bookworm
RUN apt-get update && apt-get install python3-tk tk-dev -y

COPY pyproject.toml /usr/src/app/pyproject.toml
COPY poetry.lock /usr/src/app/poetry.lock
WORKDIR /usr/src/app
RUN pip install --upgrade pip && pip install poetry uwsgi && poetry export -o requirements.txt && pip install -r requirements.txt

COPY ./code/*.py /usr/src/app/
COPY ./code/backend /usr/src/app/backend
COPY --from=frontend /home/node/app/dist/static /usr/src/app/static/
# https://github.com/docker/buildx/issues/2751
ENV PYTHONPATH="${PYTHONPATH}:/usr/src/app"
EXPOSE 80
CMD ["uwsgi", "--http", ":80", "--wsgi-file", "app.py", "--callable", "app", "-b", "32768", "--http-timeout", "230"]
```

### Explanation of the Dockerfile

1. **Stage 1: Building the Frontend**
   - **Base Image**: `node:20-alpine`
   - **Create Directory**: Creates a directory for the application and sets the appropriate permissions.
   - **Working Directory**: Sets the working directory to `/home/node/app`.
   - **Copy Package Files**: Copies the 

package.json

 and 

package-lock.json

 files to the working directory.
   - **Install Dependencies**: Installs the Node.js dependencies using `npm ci`.
   - **Copy Source Code**: Copies the frontend source code to the working directory.
   - **Build Frontend**: Runs the build command to generate the production build of the frontend application.

2. **Stage 2: Setting Up the Python Server**
   - **Base Image**: `python:3.11.7-bookworm`
   - **Install Dependencies**: Installs necessary dependencies for Python and Tkinter.
   - **Copy Poetry Files**: Copies the 

pyproject.toml

 and 

poetry.lock

 files to the working directory.
   - **Install Python Dependencies**: Installs the Python dependencies using Poetry.
   - **Copy Backend Code**: Copies the backend Python code to the working directory.
   - **Copy Frontend Build**: Copies the built frontend static files from the first stage to the `static` directory.
   - **Set Environment Variable**: Sets the `PYTHONPATH` environment variable.
   - **Expose Port**: Exposes port 80 for the application.
   - **Start Server**: Starts the server using `uwsgi`.

### Making Changes to the Frontend

If you need to make changes to the frontend application, follow these steps:

1. **Edit Frontend Source Code**
   - Make the necessary changes to the frontend source code in the 

frontend

 directory.
   - This may include editing React components, updating styles, modifying API calls, etc.

2. **Update Dependencies (if needed)**
   - If you add or update any dependencies, make sure to update the 

package.json

 and 

package-lock.json

 files.
   - Run `npm install` to install the new dependencies.

3. **Build the Frontend**
   - Navigate to the 

frontend

 directory and run the build command:
     ```sh
     npm run build
     ```

4. **Update the Dockerfile**
   - If there are any changes to the build process or dependencies, update the Dockerfile accordingly.
   - For example, if you add new environment variables or change the build commands, reflect those changes in the Dockerfile.

5. **Build and Push the Docker Image**
   - Build the updated Docker image using the Dockerfile:
     ```sh
     docker build -t your-docker-repo/percy-ai-frontend -f docker/Frontend.Dockerfile .
     ```
   - Push the updated Docker image to your Docker repository:
     ```sh
     docker push your-docker-repo/percy-ai-frontend
     ```

6. **Deploy the Updated Docker Image**
   - Update your deployment configuration (e.g., Kubernetes, Docker Compose) to use the new Docker image.
   - Deploy the updated Docker image to your environment.

### Example: Updating the Dockerfile

If you add a new environment variable to the frontend build process, update the Dockerfile as follows:

#### Updated Dockerfile (`docker/Frontend.Dockerfile`)
```dockerfile
FROM node:20-alpine AS frontend
RUN mkdir -p /home/node/app/node_modules && chown -R node:node /home/node/app
WORKDIR /home/node/app
COPY ./code/frontend/package*.json ./
USER node
RUN npm ci
COPY --chown=node:node ./code/frontend ./frontend
WORKDIR /home/node/app/frontend
# Set new environment variable
ENV REACT_APP_API_URL=https://api.percy-ai.com
RUN npm run build

FROM python:3.11.7-bookworm
RUN apt-get update && apt-get install python3-tk tk-dev -y

COPY pyproject.toml /usr/src/app/pyproject.toml
COPY poetry.lock /usr/src/app/poetry.lock
WORKDIR /usr/src/app
RUN pip install --upgrade pip && pip install poetry uwsgi && poetry export -o requirements.txt && pip install -r requirements.txt

COPY ./code/*.py /usr/src/app/
COPY ./code/backend /usr/src/app/backend
COPY --from=frontend /home/node/app/dist/static /usr/src/app/static/
# https://github.com/docker/buildx/issues/2751
ENV PYTHONPATH="${PYTHONPATH}:/usr/src/app"
EXPOSE 80
CMD ["uwsgi", "--http", ":80", "--wsgi-file", "app.py", "--callable", "app", "-b", "32768", "--http-timeout", "230"]
```

### Conclusion

By following these steps, you can make changes to the frontend application, update the Dockerfile, and deploy the updated Docker image. This ensures that your changes are reflected in the deployed application and that the environment remains consistent and functional. 


### Phase 2: Data Ingestion and Processing

#### Objective
Implement data ingestion and processing functions to efficiently handle and prepare data for search and retrieval. This phase focuses on setting up the mechanisms to ingest data from various sources, process it, and generate embeddings for efficient search and retrieval.

#### Steps

1. **Implement Data Ingestion Functions**
   - Develop functions to ingest data from various sources such as URLs, files, and databases.
   - Ensure that the data is properly formatted and stored for further processing.

2. **Configure Document Chunking and Loading Strategies**
   - Implement different strategies for chunking and loading documents to optimize processing and storage.
   - Configure the chunking and loading strategies based on the type and size of the documents.

3. **Generate Embeddings for Documents**
   - Develop functions to generate embeddings for the ingested documents.
   - Use appropriate embedding models and techniques to ensure accurate and efficient embeddings.

### Detailed Steps

#### 1. Implement Data Ingestion Functions

**File: `add_url_embeddings.py`**
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

**File: `batch_start_processing.py`**
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

#### 2. Configure Document Chunking and Loading Strategies

**File: `chunking_strategy.py`**
```python
from enum import Enum

class ChunkingStrategy(Enum):
    LAYOUT = "layout"
    PAGE = "page"
    FIXED_SIZE_OVERLAP = "fixed_size_overlap"
    PARAGRAPH = "paragraph"
```

**File: `document_chunking_base.py`**
```python
from abc import ABC, abstractmethod
from typing import List
from ..common.source_document import SourceDocument

class DocumentChunkingBase(ABC):
    @abstractmethod
    def chunk(self, documents: List[SourceDocument], chunking_settings: dict) -> List[SourceDocument]:
        pass
```

**File: `layout.py`**
```python
from typing import List
from .document_chunking_base import DocumentChunkingBase
from ..common.source_document import SourceDocument

class LayoutDocumentChunking(DocumentChunkingBase):
    def chunk(self, documents: List[SourceDocument], chunking_settings: dict) -> List[SourceDocument]:
        # Implement layout-based chunking logic
        pass
```

**File: `page.py`**
```python
from typing import List
from .document_chunking_base import DocumentChunkingBase
from ..common.source_document import SourceDocument

class PageDocumentChunking(DocumentChunkingBase):
    def chunk(self, documents: List[SourceDocument], chunking_settings: dict) -> List[SourceDocument]:
        # Implement page-based chunking logic
        pass
```

**File: `fixed_size_overlap.py`**
```python
from typing import List
from .document_chunking_base import DocumentChunkingBase
from ..common.source_document import SourceDocument

class FixedSizeOverlapDocumentChunking(DocumentChunkingBase):
    def chunk(self, documents: List[SourceDocument], chunking_settings: dict) -> List[SourceDocument]:
        # Implement fixed-size overlap chunking logic
        pass
```

**File: `paragraph.py`**
```python
from typing import List
from .document_chunking_base import DocumentChunkingBase
from ..common.source_document import SourceDocument

class ParagraphDocumentChunking(DocumentChunkingBase):
    def chunk(self, documents: List[SourceDocument], chunking_settings: dict) -> List[SourceDocument]:
        # Implement paragraph-based chunking logic
        pass
```

#### 3. Generate Embeddings for Documents

**File: `embedder_factory.py`**
```python
from ..env_helper import EnvHelper
from .push_embedder import PushEmbedder
from .integrated_vectorization_embedder import IntegratedVectorizationEmbedder

class EmbedderFactory:
    @staticmethod
    def create(env_helper: EnvHelper):
        if env_helper.AZURE_SEARCH_USE_INTEGRATED_VECTORIZATION:
            return IntegratedVectorizationEmbedder(env_helper)
        else:
            return PushEmbedder(env_helper)
```

**File: `integrated_vectorization_embedder.py`**
```python
from .embedder_base import EmbedderBase
from ..env_helper import EnvHelper

class IntegratedVectorizationEmbedder(EmbedderBase):
    def __init__(self, env_helper: EnvHelper):
        self.env_helper = env_helper

    def embed_file(self, source_url: str, file_name: str = None):
        # Implement embedding logic using integrated vectorization
        pass
```

**File: `push_embedder.py`**
```python
from .embedder_base import EmbedderBase
from ..env_helper import EnvHelper

class PushEmbedder(EmbedderBase):
    def __init__(self, env_helper: EnvHelper):
        self.env_helper = env_helper

    def embed_file(self, source_url: str, file_name: str = None):
        # Implement embedding logic using push-based approach
        pass
```

### Conclusion
Phase 2 focuses on implementing data ingestion and processing functions, configuring document chunking and loading strategies, and generating embeddings for documents. This phase ensures that the data is efficiently processed and prepared for search and retrieval, enabling the system to handle user queries effectively.

---

### Phase 3: Natural Language Interaction

#### Objective
Implement orchestration strategies to handle user queries and generate responses based on the available data. This phase focuses on setting up the mechanisms to process user queries, generate responses using various orchestration strategies, and integrate with Azure OpenAI for natural language processing.

#### Steps

1. **Implement Orchestration Strategies**
   - Develop different orchestration strategies to handle user messages and generate responses.
   - Ensure that the orchestration strategies are flexible and can be extended to support additional functionalities.

2. **Integrate with Azure OpenAI**
   - Use Azure OpenAI to process user queries and generate responses.
   - Ensure that the integration with Azure OpenAI is seamless and efficient.

3. **Handle User Queries**
   - Develop functions to handle user queries, process them using the appropriate orchestration strategy, and generate responses.
   - Ensure that the responses are accurate and relevant to the user's query.

### Detailed Steps

#### 1. Implement Orchestration Strategies

**File: `orchestration_strategy.py`**
```python
from enum import Enum

class OrchestrationStrategy(Enum):
    OPENAI_FUNCTION = "openai_function"
    LANGCHAIN = "langchain"
    SEMANTIC_KERNEL = "semantic_kernel"
    PROMPT_FLOW = "prompt_flow"
```

**File: `orchestrator_base.py`**
```python
from abc import ABC, abstractmethod
from typing import List
from ..loggers.conversation_logger import ConversationLogger
from ..helpers.config.config_helper import ConfigHelper
from ..parser.output_parser_tool import OutputParserTool
from ..tools.content_safety_checker import ContentSafetyChecker

class OrchestratorBase(ABC):
    def __init__(self) -> None:
        super().__init__()
        self.config = ConfigHelper.get_active_config_or_default()
        self.conversation_logger = ConversationLogger()
        self.content_safety_checker = ContentSafetyChecker()
        self.output_parser = OutputParserTool()

    @abstractmethod
    async def orchestrate(self, user_message: str, chat_history: List[dict], **kwargs: dict) -> list[dict]:
        pass
```

**File: `open_ai_functions.py`**
```python
import logging
from typing import List
from .orchestrator_base import OrchestratorBase
from ..helpers.llm_helper import LLMHelper
from ..tools.question_answer_tool import QuestionAnswerTool
from ..tools.text_processing_tool import TextProcessingTool

logger = logging.getLogger(__name__)

class OpenAIFunctionsOrchestrator(OrchestratorBase):
    def __init__(self) -> None:
        super().__init__()
        self.llm_helper = LLMHelper()
        self.question_answer_tool = QuestionAnswerTool()
        self.text_processing_tool = TextProcessingTool()

    async def orchestrate(self, user_message: str, chat_history: List[dict], **kwargs: dict) -> list[dict]:
        # Implement orchestration logic using OpenAI functions
        pass
```

**File: `lang_chain_agent.py`**
```python
import logging
from typing import List
from langchain.agents import Tool
from langchain.memory import ConversationBufferMemory
from langchain.agents import ZeroShotAgent, AgentExecutor
from langchain.chains.llm import LLMChain
from .orchestrator_base import OrchestratorBase
from ..helpers.llm_helper import LLMHelper
from ..tools.question_answer_tool import QuestionAnswerTool
from ..tools.text_processing_tool import TextProcessingTool

logger = logging.getLogger(__name__)

class LangChainAgent(OrchestratorBase):
    def __init__(self) -> None:
        super().__init__()
        self.llm_helper = LLMHelper()
        self.question_answer_tool = QuestionAnswerTool()
        self.text_processing_tool = TextProcessingTool()

    async def orchestrate(self, user_message: str, chat_history: List[dict], **kwargs: dict) -> list[dict]:
        # Implement orchestration logic using LangChain agent
        pass
```

**File: `semantic_kernel.py`**
```python
import logging
from semantic_kernel import Kernel
from semantic_kernel.connectors.ai.function_call_behavior import FunctionCallBehavior
from semantic_kernel.contents import ChatHistory
from semantic_kernel.contents.chat_message_content import ChatMessageContent
from semantic_kernel.contents.utils.finish_reason import FinishReason
from .orchestrator_base import OrchestratorBase
from ..helpers.llm_helper import LLMHelper
from ..plugins.chat_plugin import ChatPlugin
from ..plugins.post_answering_plugin import PostAnsweringPlugin

logger = logging.getLogger(__name__)

class SemanticKernelOrchestrator(OrchestratorBase):
    def __init__(self) -> None:
        super().__init__()
        self.kernel = Kernel()
        self.llm_helper = LLMHelper()
        self.chat_service = self.llm_helper.get_sk_chat_completion_service("cwyd")
        self.kernel.add_service(self.chat_service)
        self.kernel.add_plugin(plugin=PostAnsweringPlugin(), plugin_name="PostAnswering")

    async def orchestrate(self, user_message: str, chat_history: list[dict], **kwargs: dict) -> list[dict]:
        # Implement orchestration logic using Semantic Kernel
        pass
```

**File: `prompt_flow.py`**
```python
import logging
from typing import List
import json
import tempfile
from .orchestrator_base import OrchestratorBase
from ..helpers.llm_helper import LLMHelper
from ..helpers.env_helper import EnvHelper

logger = logging.getLogger(__name__)

class PromptFlowOrchestrator(OrchestratorBase):
    def __init__(self) -> None:
        super().__init__()
        self.llm_helper = LLMHelper()
        self.env_helper = EnvHelper()
        self.ml_client = self.llm_helper.get_ml_client()
        self.endpoint_name = self.env_helper.PROMPT_FLOW_ENDPOINT_NAME
        self.deployment_name = self.env_helper.PROMPT_FLOW_DEPLOYMENT_NAME

    async def orchestrate(self, user_message: str, chat_history: List[dict], **kwargs: dict) -> list[dict]:
        # Implement orchestration logic using Prompt Flow
        pass
```

#### 2. Integrate with Azure OpenAI

**File: `llm_helper.py`**
```python
from openai import AzureOpenAI
from typing import List
from ..env_helper import EnvHelper

class LLMHelper:
    def __init__(self):
        self.env_helper = EnvHelper()
        self.auth_type_keys = self.env_helper.is_auth_type_keys()
        self.token_provider = self.env_helper.AZURE_TOKEN_PROVIDER

        if self.auth_type_keys:
            self.openai_client = AzureOpenAI(
                azure_endpoint=self.env_helper.AZURE_OPENAI_ENDPOINT,
                api_version=self.env_helper.AZURE_OPENAI_API_VERSION,
                api_key=self.env_helper.OPENAI_API_KEY,
            )
        else:
            self.openai_client = AzureOpenAI(
                azure_endpoint=self.env_helper.AZURE_OPENAI_ENDPOINT,
                api_version=self.env_helper.AZURE_OPENAI_API_VERSION,
                azure_ad_token_provider=self.token_provider,
            )

    def get_chat_completion(self, messages: List[dict]):
        response = self.openai_client.ChatCompletion.create(
            model=self.env_helper.AZURE_OPENAI_MODEL,
            messages=messages,
        )
        return response
```

#### 3. Handle User Queries

**File: `get_conversation_response.py`**
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

### Conclusion
Phase 3 focuses on implementing orchestration strategies to handle user queries and generate responses based on the available data. This phase ensures that the system can process user queries efficiently and generate accurate and relevant responses using various orchestration strategies and Azure OpenAI.

### Phase 4: Search and Retrieval

#### Objective
Integrate with Azure Search to enable efficient search and retrieval of data. This phase focuses on setting up the mechanisms to perform search operations, retrieve relevant documents, and improve the accuracy and relevance of search results using vector-based search.

#### Steps

1. **Integrate with Azure Search**
   - Set up Azure Search service and configure the search index.
   - Implement functions to perform search operations and retrieve relevant documents.

2. **Implement Vector-Based Search**
   - Generate embeddings for documents to enable vector-based search.
   - Implement functions to perform vector-based search and improve the accuracy of search results.

3. **Handle Search Queries**
   - Develop functions to handle search queries, perform search operations, and return relevant results.
   - Ensure that the search results are accurate and relevant to the user's query.

### Detailed Steps

#### 1. Integrate with Azure Search

**File: `azure_search_helper.py`**
```python
import logging
from typing import Union
from azure.core.credentials import AzureKeyCredential
from azure.identity import DefaultAzureCredential
from azure.search.documents import SearchClient
from azure.search.documents.indexes import SearchIndexClient
from azure.search.documents.indexes.models import (
    SearchableField,
    SearchField,
    SearchFieldDataType,
    SearchIndex,
    VectorSearch,
    HnswAlgorithmConfiguration,
    HnswParameters,
    VectorSearchAlgorithmMetric,
    ExhaustiveKnnAlgorithmConfiguration,
    ExhaustiveKnnParameters,
    VectorSearchProfile,
)

from ..helpers.env_helper import EnvHelper

logger = logging.getLogger(__name__)

class AzureSearchHelper:
    def __init__(self, env_helper: EnvHelper):
        self.env_helper = env_helper
        self.search_client = self.create_search_client()

    def create_search_client(self):
        return SearchClient(
            endpoint=self.env_helper.AZURE_SEARCH_SERVICE,
            index_name=self.env_helper.AZURE_SEARCH_INDEX,
            credential=AzureKeyCredential(self.env_helper.AZURE_SEARCH_KEY)
        )

    def perform_search(self, query: str, top_k: int = 5):
        return self.search_client.search(query, top=top_k)
```

**File: `azure_search_index.py`**
```python
import logging
from azure.search.documents.indexes import SearchIndexClient
from azure.search.documents.indexes.models import (
    SearchField,
    SearchFieldDataType,
    SimpleField,
    SearchableField,
    VectorSearch,
    HnswAlgorithmConfiguration,
    HnswParameters,
    VectorSearchAlgorithmMetric,
    ExhaustiveKnnAlgorithmConfiguration,
    ExhaustiveKnnParameters,
    VectorSearchProfile,
    AzureOpenAIVectorizer,
    AzureOpenAIParameters,
    SemanticConfiguration,
    SemanticSearch,
    SemanticPrioritizedFields,
    SemanticField,
    SearchIndex,
)
from ..helpers.env_helper import EnvHelper
from azure.identity import DefaultAzureCredential
from azure.core.credentials import AzureKeyCredential
from ..helpers.llm_helper import LLMHelper

logger = logging.getLogger(__name__)

class AzureSearchIndex:
    def __init__(self, env_helper: EnvHelper, llm_helper: LLMHelper):
        self.env_helper = env_helper
        self.llm_helper = llm_helper

    def create_or_update_index(self):
        index_client = SearchIndexClient(
            endpoint=self.env_helper.AZURE_SEARCH_SERVICE,
            credential=AzureKeyCredential(self.env_helper.AZURE_SEARCH_KEY)
        )

        fields = [
            SimpleField(name="id", type=SearchFieldDataType.String, key=True),
            SearchableField(name="content", type=SearchFieldDataType.String),
            SearchField(name="content_vector", type=SearchFieldDataType.Collection(SearchFieldDataType.Single)),
            SearchableField(name="metadata", type=SearchFieldDataType.String),
        ]

        vector_search = VectorSearch(
            algorithm_configurations=[
                HnswAlgorithmConfiguration(
                    name="hnsw",
                    parameters=HnswParameters(
                        m=16,
                        ef_construction=200,
                        ef_search=100,
                        metric=VectorSearchAlgorithmMetric.Cosine
                    )
                )
            ]
        )

        index = SearchIndex(
            name=self.env_helper.AZURE_SEARCH_INDEX,
            fields=fields,
            vector_search=vector_search
        )

        index_client.create_or_update_index(index)
```

#### 2. Implement Vector-Based Search

**File: `integrated_vectorization_search_handler.py`**
```python
from typing import List
from .search_handler_base import SearchHandlerBase
from azure.search.documents import SearchClient
from azure.search.documents.indexes import SearchIndexClient
from azure.search.documents.models import VectorizableTextQuery
from azure.core.credentials import AzureKeyCredential
from azure.identity import DefaultAzureCredential
from ..common.source_document import SourceDocument

class IntegratedVectorizationSearchHandler(SearchHandlerBase):
    def create_search_client(self):
        if self._check_index_exists():
            return SearchClient(
                endpoint=self.env_helper.AZURE_SEARCH_SERVICE,
                index_name=self.env_helper.AZURE_SEARCH_INDEX,
                credential=AzureKeyCredential(self.env_helper.AZURE_SEARCH_KEY)
            )

    def perform_search(self, query: str, top_k: int = 5):
        vector_query = VectorizableTextQuery(
            search_text=query,
            top=top_k,
            vector_fields=["content_vector"]
        )
        return self.search_client.search(vector_query)

    def process_results(self, results):
        if results is None:
            return []
        data = [
            [result["id"], result["content"], result["metadata"]]
            for result in results
        ]
        return data
```

#### 3. Handle Search Queries

**File: `search.py`**
```python
from ..search.azure_search_handler import AzureSearchHandler
from ..search.integrated_vectorization_search_handler import IntegratedVectorizationSearchHandler
from ..search.search_handler_base import SearchHandlerBase
from ..common.source_document import SourceDocument
from ..helpers.env_helper import EnvHelper

class Search:
    @staticmethod
    def get_search_handler(env_helper: EnvHelper) -> SearchHandlerBase:
        if env_helper.AZURE_SEARCH_USE_INTEGRATED_VECTORIZATION:
            return IntegratedVectorizationSearchHandler(env_helper)
        else:
            return AzureSearchHandler(env_helper)

    @staticmethod
    def get_source_documents(search_handler: SearchHandlerBase, query: str) -> list[SourceDocument]:
        results = search_handler.perform_search(query)
        return search_handler.process_results(results)
```

**File: `azure_search_handler.py`**
```python
from typing import List
from .search_handler_base import SearchHandlerBase
from azure.search.documents import SearchClient
from azure.core.credentials import AzureKeyCredential
from ..common.source_document import SourceDocument

class AzureSearchHandler(SearchHandlerBase):
    def create_search_client(self):
        return SearchClient(
            endpoint=self.env_helper.AZURE_SEARCH_SERVICE,
            index_name=self.env_helper.AZURE_SEARCH_INDEX,
            credential=AzureKeyCredential(self.env_helper.AZURE_SEARCH_KEY)
        )

    def perform_search(self, query: str, top_k: int = 5):
        return self.search_client.search(query, top=top_k)

    def process_results(self, results):
        if results is None:
            return []
        data = [
            [result["id"], result["content"], result["metadata"]]
            for result in results
        ]
        return data
```

### Conclusion
Phase 4 focuses on integrating with Azure Search to enable efficient search and retrieval of data. This phase ensures that the system can perform search operations, retrieve relevant documents, and improve the accuracy and relevance of search results using vector-based search.

---

### Phase 5: Frontend Development

#### Objective
Develop the frontend application to provide a user interface for interacting with the system. This phase focuses on creating React components for displaying answers, handling user interactions, and managing conversation history. The frontend will interact with the backend through API calls to retrieve data and generate responses.

#### Steps

1. **Develop React Components**
   - Create React components for displaying answers, handling user inputs, and managing conversation history.
   - Ensure that the components are reusable and maintainable.

2. **Implement API Integration**
   - Develop functions to interact with the backend API for querying data and generating responses.
   - Ensure that the API integration is seamless and efficient.

3. **Handle User Interactions**
   - Develop functions to handle user interactions, such as submitting queries and displaying responses.
   - Ensure that the user experience is smooth and intuitive.

### Detailed Steps

#### 1. Develop React Components

**File: `Answer.tsx`**
```tsx
import { useEffect, useMemo, useState, useRef, forwardRef } from "react";
import { FontIcon, Stack, Text } from "@fluentui/react";
import styles from "./Answer.module.css";
import { AskResponse, Citation } from "../../api";
import { parseAnswer } from "./AnswerParser";
import ReactMarkdown from "react-markdown";
import remarkGfm from "remark-gfm";
import supersub from "remark-supersub";

interface Props {
  answer: AskResponse;
  onCitationClicked: (citedDocument: Citation) => void;
  onSpeak?: any;
  isActive?: boolean;
  index: number;
}

const MyStackComponent = forwardRef<HTMLDivElement, any>((props, ref) => (
  <div {...props} ref={ref} />
));

export const Answer = ({
  answer,
  onCitationClicked,
  onSpeak,
  isActive,
  index,
}: Props) => {
  const parsedAnswer = useMemo(() => parseAnswer(answer), [answer]);
  return (
    <Stack className={styles.answerContainer}>
      <ReactMarkdown
        children={parsedAnswer.markdownFormatText}
        remarkPlugins={[remarkGfm, supersub]}
      />
      <Stack horizontal>
        {parsedAnswer.citations.map((citation, idx) => (
          <Text
            key={idx}
            onClick={() => onCitationClicked(citation)}
            className={styles.citation}
          >
            {citation.content}
          </Text>
        ))}
      </Stack>
    </Stack>
  );
};
```

**File: `QuestionInput.tsx`**
```tsx
import React, { useState, useEffect } from "react";
import { Stack, TextField } from "@fluentui/react";
import { SendRegular } from "@fluentui/react-icons";
import styles from "./QuestionInput.module.css";

interface Props {
  onSend: (question: string) => void;
  disabled: boolean;
  isSendButtonDisabled: boolean;
  placeholder?: string;
  clearOnSend?: boolean;
}

export const QuestionInput = ({
  onSend,
  disabled,
  isSendButtonDisabled,
  placeholder,
  clearOnSend,
}: Props) => {
  const [question, setQuestion] = useState("");

  const handleSend = () => {
    if (question.trim() !== "") {
      onSend(question);
      if (clearOnSend) {
        setQuestion("");
      }
    }
  };

  return (
    <Stack horizontal className={styles.questionInputContainer}>
      <TextField
        className={styles.questionInputTextArea}
        placeholder={placeholder}
        value={question}
        onChange={(e, newValue) => setQuestion(newValue || "")}
        disabled={disabled}
      />
      <SendRegular
        className={styles.questionInputSendButton}
        onClick={handleSend}
        disabled={isSendButtonDisabled}
      />
    </Stack>
  );
};
```

**File: `Chat.tsx`**
```tsx
import React, { useRef, useState, useEffect } from "react";
import {
  CommandBarButton,
  DefaultButton,
  Dialog,
  DialogFooter,
  DialogType,
  PrimaryButton,
  Spinner,
  SpinnerSize,
  Stack,
  Text,
} from "@fluentui/react";
import { v4 as uuidv4 } from "uuid";
import styles from "./Chat.module.css";
import { multiLingualSpeechRecognizer } from "../../util/SpeechToText";
import { useBoolean } from "@fluentui/react-hooks";
import { Answer } from "../../components/Answer/Answer";
import { QuestionInput } from "../../components/QuestionInput/QuestionInput";
import { callConversationApi } from "../../api";

const Chat = () => {
  const [messages, setMessages] = useState([]);
  const [isLoading, { setTrue: showLoading, setFalse: hideLoading }] = useBoolean(false);

  const handleSend = async (question: string) => {
    showLoading();
    const newMessage = { id: uuidv4(), role: "user", content: question };
    setMessages([...messages, newMessage]);

    try {
      const response = await callConversationApi({ messages: [...messages, newMessage] });
      const responseData = await response.json();
      setMessages([...messages, newMessage, ...responseData.messages]);
    } catch (error) {
      console.error("Error sending message:", error);
    } finally {
      hideLoading();
    }
  };

  return (
    <Stack className={styles.chatContainer}>
      <Stack className={styles.messagesContainer}>
        {messages.map((message, index) => (
          <Answer key={index} answer={message} onCitationClicked={() => {}} index={index} />
        ))}
      </Stack>
      <QuestionInput onSend={handleSend} disabled={isLoading} isSendButtonDisabled={isLoading} />
      {isLoading && <Spinner size={SpinnerSize.large} />}
    </Stack>
  );
};

export default Chat;
```

#### 2. Implement API Integration

**File: `api.ts`**
```typescript
import { ChatMessage, ConversationRequest } from "./models";

export async function callConversationApi(options: ConversationRequest): Promise<Response> {
  const response = await fetch("/api/conversation", {
    method: "POST",
    headers: {
      "Content-Type": "application/json",
    },
    body: JSON.stringify({
      messages: options.messages,
      conversation_id: options.id,
    }),
  });

  if (!response.ok) {
    const errorData = await response.json();
    throw new Error(JSON.stringify(errorData.error));
  }

  return response;
}
```

**File: `models.ts`**
```typescript
export type AskResponse = {
  answer: string;
  citations: Citation[];
  error?: string;
};

export type Citation = {
  content: string;
  id: string;
  title: string | null;
  filepath: string | null;
  url: string | null;
  metadata: string | null;
  chunk_id: string | null;
  reindex_id: string | null;
};

export type ChatMessage = {
  role: string;
  content: string;
  id: string;
  date: string;
  feedback?: Feedback;
  context?: string;
};

export enum Feedback {
  Neutral = "neutral",
  Positive = "positive",
  Negative = "negative",
}

export type ConversationRequest = {
  messages: ChatMessage[];
  id: string;
};
```

#### 3. Handle User Interactions

**File: `ChatHistoryList.tsx`**
```tsx
import React from "react";
import { Conversation } from "../../api/models";
import { ChatHistoryListItemGroups } from "./ChatHistoryListItem";

interface ChatHistoryListProps {
  fetchingChatHistory: boolean;
  handleFetchHistory: () => Promise<void>;
  chatHistory: Conversation[];
  onSelectConversation: (id: string) => void;
  selectedConvId: string;
  onHistoryTitleChange: (id: string, newTitle: string) => void;
  onHistoryDelete: (id: string) => void;
  isGenerating: boolean;
  toggleToggleSpinner: (toggler: boolean) => void;
}

export interface GroupedChatHistory {
  title: string;
  entries: Conversation[];
}

const segregateItems = (items: Conversation[]) => {
  const groupedItems: GroupedChatHistory[] = [
    { title: "Last 7 Days", entries: [] },
    { title: "Older", entries: [] },
  ];

  items.forEach((item) => {
    const date = new Date(item.date);
    if (isLastSevenDaysRange(date)) {
      groupedItems[0].entries.push(item);
    } else {
      groupedItems[1].entries.push(item);
    }
  });

  return groupedItems;
};

const ChatHistoryList: React.FC<ChatHistoryListProps> = ({
  fetchingChatHistory,
  handleFetchHistory,
  chatHistory,
  onSelectConversation,
  selectedConvId,
  onHistoryTitleChange,
  onHistoryDelete,
  isGenerating,
  toggleToggleSpinner,
}) => {
  const groupedItems = segregateItems(chatHistory);

  return (
    <div>
      {groupedItems.map((group, index) => (
        <ChatHistoryListItemGroups
          key={index}
          group={group}
          onSelectConversation={onSelectConversation}
          selectedConvId={selectedConvId}
          onHistoryTitleChange={onHistoryTitleChange}
          onHistoryDelete={onHistoryDelete}
          isGenerating={isGenerating}
          toggleToggleSpinner={toggleToggleSpinner}
        />
      ))}
    </div>
  );
};

export default ChatHistoryList;
```

### Conclusion
Phase 5 focuses on developing the frontend application to provide a user interface for interacting with the system. This phase ensures that the frontend components are reusable and maintainable, the API integration is seamless, and the user interactions are smooth and intuitive.

---

### Phase 6: Deployment

#### Objective
Deploy the application to Azure using Infrastructure as Code (IaC) with Bicep templates. This phase focuses on automating the deployment process to ensure a consistent and repeatable deployment of the application and its infrastructure.

#### Steps

1. **Prepare Bicep Templates**
   - Use Bicep templates to define the infrastructure required for the application.
   - Ensure that the templates cover all necessary Azure resources, including Azure Functions, Azure Search, Azure Blob Storage, and other services.

2. **Deploy Infrastructure**
   - Use the Azure CLI to deploy the infrastructure defined in the Bicep templates.
   - Ensure that the deployment process is automated and repeatable.

3. **Build and Push Docker Images**
   - Build Docker images for the frontend and backend applications.
   - Push the Docker images to a container registry.

4. **Deploy the Application**
   - Deploy the frontend and backend applications using the Docker images.
   - Ensure that the applications are configured correctly and can communicate with each other.

### Detailed Steps

#### 1. Prepare Bicep Templates

**File: 

main.bicep

**
```bicep
param resourceToken string = toLower(uniqueString(subscription().id, resourceGroup().name, resourceGroup().location))

@description('Name of App Service plan')
param hostingPlanName string = 'hosting-plan-${resourceToken}'

@description('The pricing tier for the App Service plan')
@allowed([
  'F1'
  'D1'
  'B1'
  'B2'
  'B3'
  'S1'
  'S2'
  'S3'
  'P1'
  'P2'
  'P3'
  'P4'
])
param hostingPlanSku string = 'B3'

@description('The sku tier for the App Service plan')
@allowed([
  'Free'
  'Shared'
  'Basic'
  'Standard'
  'Premium'
  'PremiumV2'
  'PremiumV3'
])
param skuTier string = 'Basic'

@description('Name of Web App')
param websiteName string = '

web

-${resourceToken}'

module hostingPlan 'appserviceplan.bicep' = {
  name: 'hostingPlan'
  params: {
    name: hostingPlanName
    location: location
    tags: tags
    sku: {
      name: hostingPlanSku
      tier: skuTier
    }
  }
}

module webApp 'appservice.bicep' = {
  name: 'webApp'
  params: {
    name: websiteName
    location: location
    tags: tags
    appServicePlanId: hostingPlan.outputs.id
    runtimeName: 'python'
    runtimeVersion: '3.9'
    dockerFullImageName: 'your-docker-repo/percy-ai-frontend:latest'
    useDocker: true
  }
}
```

**File: `infra/appservice.bicep`**
```bicep
metadata description = 'Creates an Azure App Service in an existing Azure App Service plan.'
param name string
param location string = resourceGroup().location
param tags object = {}

param appServicePlanId string
param runtimeName string
param runtimeVersion string
param dockerFullImageName string = ''
param useDocker bool = dockerFullImageName != ''

resource appService 'Microsoft.Web/sites@2021-02-01' = {
  name: name
  location: location
  tags: tags
  properties: {
    serverFarmId: appServicePlanId
    siteConfig: {
      linuxFxVersion: useDocker ? 'DOCKER|${dockerFullImageName}' : '${runtimeName}|${runtimeVersion}'
    }
  }
}

output id string = appService.id
output name string = appService.name
```

**File: `infra/appserviceplan.bicep`**
```bicep
metadata description = 'Creates an Azure App Service plan.'
param name string
param location string = resourceGroup().location
param tags object = {}

param sku object

resource appServicePlan 'Microsoft.Web/serverfarms@2021-02-01' = {
  name: name
  location: location
  tags: tags
  sku: sku
}

output id string = appServicePlan.id
output name string = appServicePlan.name
```

#### 2. Deploy Infrastructure

Use the Azure CLI to deploy the infrastructure defined in the Bicep templates:

```sh
az deployment group create --resource-group <resource-group-name> --template-file infra/main.bicep --parameters @infra/main.bicepparam
```

#### 3. Build and Push Docker Images

**Build Docker Images**

Build the Docker images for the frontend and backend applications:

```sh
# Build frontend Docker image
docker build -t your-docker-repo/percy-ai-frontend -f docker/Frontend.Dockerfile .

# Build backend Docker image
docker build -t your-docker-repo/percy-ai-backend -f docker/Backend.Dockerfile .
```

**Push Docker Images**

Push the Docker images to a container registry:

```sh
# Push frontend Docker image
docker push your-docker-repo/percy-ai-frontend

# Push backend Docker image
docker push your-docker-repo/percy-ai-backend
```

#### 4. Deploy the Application

**Deploy Frontend and Backend Applications**

Deploy the frontend and backend applications using the Docker images:

```sh
# Deploy frontend application
az webapp create --resource-group <resource-group-name> --plan <app-service-plan-name> --name <frontend-app-name> --deployment-container-image-name your-docker-repo/percy-ai-frontend:latest

# Deploy backend application
az webapp create --resource-group <resource-group-name> --plan <app-service-plan-name> --name <backend-app-name> --deployment-container-image-name your-docker-repo/percy-ai-backend:latest
```

**Configure Application Settings**

Ensure that the applications are configured correctly and can communicate with each other. Update the application settings as needed:

```sh
# Update frontend application settings
az webapp config appsettings set --resource-group <resource-group-name> --name <frontend-app-name> --settings BACKEND_URL=https://<backend-app-name>.azurewebsites.net

# Update backend application settings
az webapp config appsettings set --resource-group <resource-group-name> --name <backend-app-name> --settings FRONTEND_URL=https://<frontend-app-name>.azurewebsites.net
```

### Conclusion
Phase 6 focuses on deploying the application to Azure using Infrastructure as Code (IaC) with Bicep templates. This phase ensures that the deployment process is automated and repeatable, and that the application and its infrastructure are deployed consistently.

---

### Phase 7: Testing and Validation

#### Objective
Ensure that the application is functioning correctly and meets the specified requirements. This phase focuses on testing the application, validating its functionality, and ensuring that it performs as expected.

#### Steps

1. **Unit Testing**
   - Write and execute unit tests for individual components and functions.
   - Ensure that each component and function behaves as expected in isolation.

2. **Integration Testing**
   - Write and execute integration tests to verify that different components of the application work together correctly.
   - Ensure that the integration points between the frontend, backend, and Azure services function as expected.

3. **End-to-End Testing**
   - Write and execute end-to-end tests to simulate real user interactions with the application.
   - Ensure that the entire application workflow, from data ingestion to user interaction, works seamlessly.

4. **Performance Testing**
   - Conduct performance tests to ensure that the application can handle the expected load and performs well under stress.
   - Identify and address any performance bottlenecks.

5. **User Acceptance Testing (UAT)**
   - Conduct user acceptance testing with a group of end-users to validate that the application meets their needs and expectations.
   - Gather feedback and make necessary adjustments based on user input.

### Detailed Steps

#### 1. Unit Testing

**Example: Unit Test for `add_url_embeddings.py`**

**File: `test_add_url_embeddings.py`**
```python
import unittest
from unittest.mock import patch, MagicMock
from add_url_embeddings import add_url_embeddings

class TestAddUrlEmbeddings(unittest.TestCase):
    @patch('add_url_embeddings.EmbedderFactory')
    def test_add_url_embeddings(self, mock_embedder_factory):
        mock_embedder = MagicMock()
        mock_embedder_factory.create.return_value = mock_embedder

        req = MagicMock()
        req.get_json.return_value = {"url": "http://example.com"}

        response = add_url_embeddings(req)

        self.assertEqual(response.status_code, 200)
        mock_embedder.embed_file.assert_called_once_with("http://example.com")

if __name__ == '__main__':
    unittest.main()
```

#### 2. Integration Testing

**Example: Integration Test for Search Functionality**

**File: `test_search.py`**
```python
import unittest
from unittest.mock import patch, MagicMock
from search import Search
from azure_search_handler import AzureSearchHandler

class TestSearch(unittest.TestCase):
    @patch('search.AzureSearchHandler')
    def test_search(self, mock_search_handler):
        mock_handler_instance = mock_search_handler.return_value
        mock_handler_instance.perform_search.return_value = [
            {"id": "1", "content": "Test content", "metadata": "Test metadata"}
        ]

        env_helper = MagicMock()
        search_handler = Search.get_search_handler(env_helper)
        results = Search.get_source_documents(search_handler, "test query")

        self.assertEqual(len(results), 1)
        self.assertEqual(results[0][1], "Test content")

if __name__ == '__main__':
    unittest.main()
```

#### 3. End-to-End Testing

**Example: End-to-End Test for User Interaction**

**File: `test_end_to_end.py`**
```python
import unittest
from selenium import webdriver
from selenium.webdriver.common.keys import Keys

class TestEndToEnd(unittest.TestCase):
    def setUp(self):
        self.driver = webdriver.Chrome()

    def test_user_interaction(self):
        driver = self.driver
        driver.get("http://localhost:3000")

        input_box = driver.find_element_by_name("question")
        input_box.send_keys("What is the capital of France?")
        input_box.send_keys(Keys.RETURN)

        response = driver.find_element_by_class_name("answerContainer")
        self.assertIn("Paris", response.text)

    def tearDown(self):
        self.driver.close()

if __name__ == '__main__':
    unittest.main()
```

#### 4. Performance Testing

**Example: Performance Test using Locust**

**File: `locustfile.py`**
```python
from locust import HttpUser, TaskSet, task, between

class UserBehavior(TaskSet):
    @task(1)
    def query(self):
        self.client.post("/api/conversation", json={
            "messages": [{"role": "user", "content": "What is the capital of France?"}],
            "conversation_id": "test-conversation"
        })

class WebsiteUser(HttpUser):
    tasks = [UserBehavior]
    wait_time = between(1, 5)
```

Run the performance test using Locust:
```sh
locust -f locustfile.py
```

#### 5. User Acceptance Testing (UAT)

**Steps for UAT:**
1. **Prepare Test Scenarios**: Define test scenarios that cover all major functionalities of the application.
2. **Select Test Users**: Identify a group of end-users who will participate in the testing.
3. **Conduct Testing**: Have the test users perform the test scenarios and gather their feedback.
4. **Analyze Feedback**: Analyze the feedback from the test users and identify any issues or areas for improvement.
5. **Make Adjustments**: Make necessary adjustments to the application based on the feedback.

### Conclusion
Phase 7 focuses on testing and validating the application to ensure that it functions correctly and meets the specified requirements. This phase includes unit testing, integration testing, end-to-end testing, performance testing, and user acceptance testing to ensure that the application performs as expected and provides a smooth user experience.

---

### Phase 8: Monitoring and Maintenance

#### Objective
Set up monitoring and maintenance processes to ensure the application runs smoothly and efficiently. This phase focuses on implementing monitoring tools, setting up alerts, and establishing maintenance routines to keep the application healthy and performant.

#### Steps

1. **Set Up Monitoring Tools**
   - Use Azure Monitor and Application Insights to monitor the application's performance and health.
   - Configure logging and telemetry to capture important metrics and events.

2. **Configure Alerts**
   - Set up alerts to notify the team of any issues or anomalies in the application's performance.
   - Ensure that alerts are actionable and provide enough context to diagnose and resolve issues quickly.

3. **Establish Maintenance Routines**
   - Define regular maintenance tasks to keep the application and its infrastructure up to date.
   - Implement automated processes for routine maintenance tasks.

4. **Implement Logging and Telemetry**
   - Ensure that all critical operations and events are logged.
   - Use telemetry to gather insights into the application's usage and performance.

### Detailed Steps

#### 1. Set Up Monitoring Tools

**File: 

applicationinsights.bicep

**
```bicep
metadata description = 'Creates an Application Insights instance based on an existing Log Analytics workspace.'
param name string
param dashboardName string = ''
param location string = resourceGroup().location
param tags object = {}
param logAnalyticsWorkspaceId string

resource applicationInsights 'Microsoft.Insights/components@2020-02-02' = {
  name: name
  location: location
  tags: tags
  kind: 'web'
  properties: {
    Application_Type: 'web'
    WorkspaceResourceId: logAnalyticsWorkspaceId
  }
}

module applicationInsightsDashboard 'applicationinsights-dashboard.bicep' = if (!empty(dashboardName)) {
  name: 'application-insights-dashboard'
  params: {
    name: dashboardName
    location: location
    applicationInsightsName: applicationInsights.name
  }
}

output connectionString string = applicationInsights.properties.ConnectionString
output instrumentationKey string = applicationInsights.properties.InstrumentationKey
output name string = applicationInsights.name
output id string = applicationInsights.id
```

**File: 

loganalytics.bicep

**
```bicep
metadata description = 'Creates a Log Analytics workspace.'
param name string
param location string = resourceGroup().location
param tags object = {}

resource logAnalytics 'Microsoft.OperationalInsights/workspaces@2021-12-01-preview' = {
  name: name
  location: location
  tags: tags
  properties: {
    retentionInDays: 30
    features: {
      searchVersion: 1
    }
    sku: {
      name: 'PerGB2018'
    }
  }
}

output id string = logAnalytics.id
output name string = logAnalytics.name
```

**File: 

monitoring.bicep

**
```bicep
param applicationInsightsDashboardName string = ''
param location string = resourceGroup().location
param tags object = {}

module logAnalytics 'loganalytics.bicep' = {
  name: 'loganalytics'
  params: {
    name: logAnalyticsName
    location: location
    tags: tags
  }
}

module applicationInsights 'applicationinsights.bicep' = {
  name: 'applicationinsights'
  params: {
    name: applicationInsightsName
    location: location
    tags: tags
    dashboardName: applicationInsightsDashboardName
    logAnalyticsWorkspaceId: logAnalytics.outputs.id
  }
}

output applicationInsightsConnectionString string = applicationInsights.outputs.connectionString
output applicationInsightsInstrumentationKey string = applicationInsights.outputs.instrumentationKey
output applicationInsightsName string = applicationInsights.outputs.name
output applicationInsightsId string = applicationInsights.outputs.id
output logAnalyticsWorkspaceId string = logAnalytics.outputs.id
output logAnalyticsWorkspaceName string = logAnalytics.outputs.name
```

#### 2. Configure Alerts

**File: `infra/core/monitor/alerts.bicep`**
```bicep
metadata description = 'Creates alerts for monitoring the application.'
param name string
param location string = resourceGroup().location
param tags object = {}
param applicationInsightsId string

resource alertRule 'Microsoft.Insights/metricAlerts@2018-03-01' = {
  name: name
  location: location
  tags: tags
  properties: {
    description: 'Alert rule for monitoring application performance'
    severity: 3
    enabled: true
    scopes: [
      applicationInsightsId
    ]
    evaluationFrequency: 'PT5M'
    windowSize: 'PT5M'
    criteria: {
      allOf: [
        {
          name: 'High CPU Usage'
          metricName: 'Percentage CPU'
          metricNamespace: 'Microsoft.Compute/virtualMachines'
          operator: 'GreaterThan'
          threshold: 80
          timeAggregation: 'Average'
          dimensions: []
        }
      ]
    }
    actions: []
  }
}
```

#### 3. Establish Maintenance Routines

**Example: Maintenance Script**

**File: `scripts/maintenance.sh`**
```sh
#!/usr/bin/env bash

# Update system packages
sudo apt-get update && sudo apt-get upgrade -y

# Clean up old Docker images
docker image prune -f

# Restart services
sudo systemctl restart docker
sudo systemctl restart nginx
```

**Schedule the Maintenance Script**

Use a cron job to schedule the maintenance script to run at regular intervals:

```sh
# Open the crontab file
crontab -e

# Add the following line to schedule the maintenance script to run every Sunday at 2 AM
0 2 * * SUN /path/to/scripts/maintenance.sh
```

#### 4. Implement Logging and Telemetry

**File: `app.py`**
```python
import logging
from azure.monitor.opentelemetry import configure_azure_monitor

logging.captureWarnings(True)
logging.basicConfig(level=os.environ.get("LOGLEVEL", "INFO").upper())

if os.getenv("APPLICATIONINSIGHTS_ENABLED", "true").lower() == "true":
    configure_azure_monitor()

# Application code...
```

**File: `function_app.py`**
```python
import logging
import os
import azure.functions as func
from azure.monitor.opentelemetry import configure_azure_monitor

logging.captureWarnings(True)
logging.getLogger("azure").setLevel(os.environ.get("LOGLEVEL_AZURE", "WARN").upper())

if os.getenv("APPLICATIONINSIGHTS_ENABLED", "true").lower() == "true":
    configure_azure_monitor()

app = func.FunctionApp(http_auth_level=func.AuthLevel.FUNCTION)
# Register functions...
```

### Conclusion
Phase 8 focuses on setting up monitoring and maintenance processes to ensure the application runs smoothly and efficiently. This phase includes setting up monitoring tools, configuring alerts, establishing maintenance routines, and implementing logging and telemetry to keep the application healthy and performant.

---

### Phase 9: Creating Teams Extension

#### Objective
Integrate the application with Microsoft Teams to enable users to interact with the system directly from Teams. This phase focuses on creating a Teams extension that allows users to send queries and receive responses within the Teams interface.

#### Steps

1. **Set Up the Teams Bot**
   - Create a bot that will handle interactions within Microsoft Teams.
   - Configure the bot with the necessary credentials and endpoints.

2. **Implement Bot Logic**
   - Develop the logic for handling messages and generating responses.
   - Ensure that the bot can communicate with the backend to process queries and retrieve responses.

3. **Provision and Deploy the Teams Bot**
   - Use the Teams Toolkit in Visual Studio Code to provision and deploy the bot to Azure.
   - Ensure that the bot is registered and available for use within Teams.

### Detailed Steps

#### 1. Set Up the Teams Bot

**File: `teams-extension/config.ts`**
```typescript
const config = {
  botId: process.env.BOT_ID,
  botPassword: process.env.BOT_PASSWORD,
  azureFunctionUrl: process.env.AZURE_FUNCTION_URL,
};

export default config;
```

**Explanation:**
- This configuration file sets up the necessary environment variables for the bot, including the bot ID, bot password, and the URL of the Azure Function that will handle the backend processing.

#### 2. Implement Bot Logic

**File: `teams-extension/index.ts`**
```typescript
import * as restify from "restify";
import {
  CloudAdapter,
  ConfigurationServiceClientCredentialFactory,
  ConfigurationBotFrameworkAuthentication,
  TurnContext,
} from "botbuilder";
import { TeamsBot } from "./teamsBot";
import config from "./config";

const credentialsFactory = new ConfigurationServiceClientCredentialFactory({
  MicrosoftAppId: config.botId,
  MicrosoftAppPassword: config.botPassword,
  MicrosoftAppType: "MultiTenant",
});

const botFrameworkAuthentication = new ConfigurationBotFrameworkAuthentication(
  {},
  credentialsFactory
);

const adapter = new CloudAdapter(botFrameworkAuthentication);

const onTurnErrorHandler = async (context: TurnContext, error: Error) => {
  console.error(`\n [onTurnError] unhandled error: ${error}`);
  await context.sendActivity("The bot encountered an error or bug.");
  await context.sendActivity(
    "To continue to run this bot, please fix the bot source code."
  );
};

adapter.onTurnError = onTurnErrorHandler;

const bot = new TeamsBot();

const server = restify.createServer();
server.use(restify.plugins.bodyParser());

server.post("/api/messages", (req, res) => {
  adapter.process(req, res, (context) => bot.run(context));
});

server.listen(process.env.port || process.env.PORT || 3978, () => {
  console.log(`\n${server.name} listening to ${server.url}`);
});
```

**Explanation:**
- This file sets up the bot's main logic, including creating the adapter, handling errors, and defining the endpoint for processing messages.
- The bot is configured to use the credentials specified in the `config.ts` file and is set up to listen for messages on the `/api/messages` endpoint.

**File: 

model.ts

**
```typescript
export type AskResponse = {
  answer: string;
  citations: Citation[];
  error?: string;
};

export type Citation = {
  content: string;
  id: string;
  title: string | null;
  filepath: string | null;
  url: string | null;
  metadata: string | null;
  chunk_id: string | null;
  reindex_id: string | null;
};

export enum CardType {
  OpenUrl = "Action.OpenUrl",
  ShowCard = "Action.ShowCard",
  AdaptiveCard = "AdaptiveCard",
  TextBlock = "TextBlock",
}

export type ToolMessageContent = {
  citations: Citation[];
  intent: string;
};

export type ChatMessage = {
  role: string;
  content: string;
  end_turn?: boolean;
};

export enum ChatCompletionType {
  // Define completion types here
}
```

**Explanation:**
- This file defines the types and models used by the bot, including the structure of the responses, citations, and chat messages.

#### 3. Provision and Deploy the Teams Bot

**Steps to Provision and Deploy Using Teams Toolkit in Visual Studio Code:**

1. **Install Teams Toolkit Extension**
   - Open Visual Studio Code.
   - Go to the Extensions view by clicking on the Extensions icon in the Activity Bar on the side of the window.
   - Search for "Teams Toolkit" and install the extension.

2. **Open the Teams Extension Project**
   - Open the `teams-extension` project in Visual Studio Code.

3. **Provision the Bot**
   - Click on the Teams Toolkit icon in the Activity Bar.
   - Select "Provision in the Cloud" from the options.
   - Follow the prompts to sign in to your Azure account and select the subscription and resource group where you want to provision the bot.
   - The toolkit will create the necessary Azure resources, including the Azure Bot Service and App Service.

4. **Deploy the Bot**
   - After provisioning, select "Deploy to the Cloud" from the Teams Toolkit options.
   - The toolkit will build and deploy the bot to the Azure resources created during provisioning.

5. **Register the Bot with Microsoft Teams**
   - Go to the Bot Framework portal and register the bot with Microsoft Teams.
   - Configure the Teams channel and ensure that the bot is available for use within Teams.

6. **Test the Bot in Teams**
   - Open Microsoft Teams and add the bot to a team or chat.
   - Send a message to the bot and verify that it responds correctly.

### Conclusion
Phase 9 focuses on creating a Teams extension to enable users to interact with the system directly from Microsoft Teams. This phase includes setting up the Teams bot, implementing the bot logic, and provisioning and deploying the bot using the Teams Toolkit in Visual Studio Code. By integrating with Teams, users can send queries and receive responses within the Teams interface, enhancing the overall user experience.

---

