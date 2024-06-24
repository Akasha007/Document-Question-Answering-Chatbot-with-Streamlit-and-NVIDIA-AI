# PDF Contextual Question Answering System

This Streamlit application leverages NVIDIA's embeddings and the LangChain library to create a robust, context-aware question answering system that processes text from PDF documents. It uses text processing and vector-based retrieval techniques to generate precise answers to user queries.

## Features

- **PDF Text Extraction**: Extracts text from uploaded PDF documents using PyPDF2.
- **Text Processing**: Splits extracted text into manageable chunks and generates embeddings.
- **Contextual Question Answering**: Utilizes NVIDIA's Mistral AI model within a conversational AI chain to answer questions based on the context extracted from the PDFs.
- **Vector-based Retrieval**: Employs FAISS (Facebook AI Similarity Search) for efficient similarity search among text chunks.

## Installation

Clone the repository and install the required dependencies (requirements.txt)

## Functionality

The PDF Contextual Question Answering System comprises several key functional components:

1. **Text Extraction**:
   - Upon uploading PDF files, the system uses `PdfReader` to extract all textual content from the documents, ensuring comprehensive access to the document data.

2. **Text Processing**:
   - **Text Splitting**: The extracted text is divided into manageable chunks using `RecursiveCharacterTextSplitter`. This process helps maintain context and manage large documents effectively.
   - **Embedding Generation**: Each text chunk is then embedded using `NVIDIAEmbeddings`, preparing the text for efficient similarity searches.

3. **Vector Store**:
   - The generated embeddings are stored in a FAISS index, `faiss_index`, facilitating efficient retrieval of text chunks based on similarity to the user's query.

4. **Conversational AI Chain**:
   - **Custom Prompt**: A tailored prompt template is used to ensure that the answers are detailed and contextually relevant, adhering to the provided information.
   - **Model Utilization**: The system employs `ChatNVIDIA`, configured with NVIDIA's state-of-the-art `mistralai/mixtral-8x22b-instruct-v0.1` model, to generate context-aware answers.

5. **Query Processing**:
   - Users can input questions related to the text in the PDFs. These are processed by the system to retrieve the most relevant text chunks from the FAISS vector store.
   - The conversational AI chain then generates answers based on these retrieved contexts, ensuring accuracy and relevance.

6. **User Interaction**:
   - The application supports uploading multiple PDF files and entering questions through a simple and intuitive user interface.
   - The answers are generated in real-time and displayed to the user, providing quick and effective access to information contained within the PDFs.

This robust architecture ensures that the application not only processes PDF documents efficiently but also provides precise answers to user queries by leveraging advanced AI and vector search technologies.

## Usage

To run the application locally:

1. **Set up your environment**:
   Ensure that you have Python installed, along with Streamlit and other dependencies listed in `requirements.txt`.

2. **Clone the repository**:
   If you haven't already, clone the repository to your local machine.

3. **Set your NVIDIA API Key**:
   - Replace the placeholder in the `app.py` file with your actual NVIDIA API key. This is crucial for the application to function properly:
     ```python
     os.environ['NVIDIA_API_KEY'] = "your_actual_nvidia_api_key"
     ```

4. **Start the application**:
   - Launch the Streamlit application by running:
     ```bash
     streamlit run app.py
     ```

5. **Access the application**:
   - Open your web browser and go to `http://localhost:8501` to view the application. You can upload PDF files and ask questions directly through the user interface.

6. **Interact with the PDFs**:
   - Upload your PDF documents using the sidebar option. Once the documents are processed, you can enter questions in the text input box. The system will display answers based on the content of the uploaded PDFs.

These steps will help you set up and use the PDF Contextual Question Answering System.


