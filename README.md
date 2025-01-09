# JK-Tech

# LLM Model Web Application

Welcome to the **LLM Model Web Application**! This application enables users to upload PDF or TXT files, train a language model on the uploaded content, and perform question-and-answer (QA) tasks based on the document.

## Features
- Upload PDF or TXT files.
- Train a language model to process and understand document content.
- Perform QA tasks on the trained model.

## Getting Started

### Prerequisites
- Python 3.8 or higher
- Flask
- Flask-CORS
- HuggingFace Transformers
- LangChain
- FAISS
- Other dependencies (see `requirements.txt`)

### Installation Steps

1. **Clone the Repository**
   ```bash
   git clone https://github.com/cris7M/JK-Tech.git
   cd JK-Tech


2. **Create a Virtual Environment**
python -m venv venv
venv/Scripts/activate  # For Windows
source venv/bin/activate  # For Linux/Mac


**Install Dependencies**
pip install -r requirements.txt


**Run the Application**
python main.py


**Access the Web Application Open your browser and go to:**
http://localhost:5000


## Application Workflow

Home Page
Navigate to the home page to get started.

Upload File
Upload a PDF or TXT file through the /upload endpoint.

Train Model
After uploading, use the /trained endpoint to train the model.

Ask Questions
Once the model is trained, use the /ask endpoint to query the model.

Code Overview

Key Components

Flask App Initialization

app = Flask(__name__, static_folder="static", static_url_path="/static")
CORS(app)

File Upload Handling

@app.route('/upload', methods=['POST'])
def upload_file():
    # Handles file upload and saves to the uploads folder

Model Training

@app.route('/trained', methods=['POST'])
def train_model():
    # Loads the document, creates a vector store, and initializes the QA chain

Question Answering

@app.route('/ask', methods=['POST'])
def ask_question():
    # Answers questions using the trained QA chain

Folder Structure

uploads/: Stores uploaded files.

pickle/: Stores serialized QA chains.

static/: Contains static files (e.g., CSS, JS, images).

templates/: HTML templates for the web pages.

Logging

Logs important events and errors for debugging.

logging.basicConfig(level=logging.DEBUG)

Usage

Visit http://localhost:5000 to use the web interface.

Upload your document.

Train the model.

Ask questions and get answers based on your document.

Notes

Supported file formats: PDF.

The model uses HuggingFace Transformers for embeddings and FAISS for vector storage.

Troubleshooting

If you encounter errors, check the logs for details.

Ensure all dependencies are correctly installed.

Verify that your virtual environment is activated.