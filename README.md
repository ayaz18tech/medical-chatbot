# Medical Chatbot

## Project Overview

This Medical Chatbot is an intelligent question-answering system designed to provide information based on a given medical PDF document. Leveraging Retrieval-Augmented Generation (RAG) with Langchain, Pinecone, and HuggingFace embeddings, the chatbot can understand natural language queries and retrieve relevant information from the medical knowledge base to generate concise and accurate responses. The application features a user-friendly web interface built with Flask, allowing users to interact with the chatbot seamlessly.

## Features

*   **Intelligent Q&A**: Answers medical questions by retrieving information from a provided PDF document.
*   **Retrieval-Augmented Generation (RAG)**: Combines information retrieval with a language model for accurate and context-aware responses.
*   **HuggingFace Embeddings**: Utilizes `sentence-transformers/all-MiniLM-L6-v2` for efficient document embedding.
*   **Pinecone Vector Database**: Stores and retrieves document embeddings for fast similarity searches.
*   **Flask Web Interface**: Provides a simple and interactive chat interface for users.
*   **Concise Responses**: Designed to provide answers limited to three sentences, as per the system prompt.

## Technologies Used

The project is built using the following key technologies:

*   **Python**: Programming language.
*   **Flask**: Web framework for the user interface.
*   **Langchain**: Framework for developing applications powered by language models.
*   **Pinecone**: Vector database for efficient similarity search.
*   **HuggingFace Transformers**: For generating document embeddings.
*   **PyPDFLoader**: For loading PDF documents.
*   **python-dotenv**: For managing environment variables.
*   **HTML/CSS/JavaScript**: For the frontend chat interface.

## Installation

To set up and run the Medical Chatbot locally, follow these steps:

1.  **Clone the repository**:

    ```bash
    git clone https://github.com/ayaz18tech/medical-chatbot.git
    cd medical_chatbot
    ```

2.  **Create a virtual environment** (recommended):

    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

3.  **Install dependencies**:

    ```bash
    pip install -r requirements.txt
    ```

4.  **Set up environment variables**:

    Create a `.env` file in the root directory of the project and add your API keys:

    ```env
    PINECONE_API_KEY="YOUR_PINECONE_API_KEY"
    OPENAI_API_KEY="YOUR_OPENAI_API_KEY"
    ```

    *   **Pinecone API Key**: Obtain from [Pinecone](https://www.pinecone.io/).
    *   **OpenAI API Key**: Obtain from [OpenAI](https://platform.openai.com/).

5.  **Prepare the medical document**: 

    Place your medical PDF document (e.g., `Medical_book.pdf`) inside the `data/` directory.

6.  **Generate and store embeddings**: 

    Run the `store_index.py` script to process the PDF, generate embeddings, and store them in your Pinecone index. This step will create a Pinecone index named `medical-chatbot1`.

    ```bash
    python store_index.py
    ```

## Usage

1.  **Start the Flask application**:

    ```bash
    python app.py
    ```

2.  **Access the chatbot**: 

    Open your web browser and navigate to `http://0.0.0.0:8080` (or the address shown in your terminal).

3.  **Interact with the chatbot**: 

    Type your medical questions into the chat interface and receive AI-generated responses.

## Project Structure

```
medical_chatbot/
├── data/                       # Contains the medical PDF document
│   └── Medical_book.pdf
├── src/                        # Source code for helper functions and prompts
│   ├── __init__.py
│   ├── helper.py               # Functions for PDF loading, text splitting, and embeddings
│   └── prompt.py               # Defines the system prompt for the chatbot
├── templates/                  # HTML templates for the web interface
│   └── chat.html               # Main chat interface
├── static/                     # Static assets like CSS
│   └── style.css
├── research/                   # Jupyter notebooks for research/experimentation
│   └── trails.ipynb
├── .env                        # Environment variables (API keys)
├── app.py                      # Main Flask application
├── requirements.txt            # Python dependencies
├── setup.py                    # Project setup file
├── store_index.py              # Script to process PDF and store embeddings in Pinecone
└── README.md                   # This README file
```

## Contributing

Contributions are welcome! If you have suggestions for improvements or new features, please open an issue or submit a pull request.

## License

This project is licensed under the Apache-2.0 License. See the `LICENSE` file for details.

## Contact

For any questions or inquiries, please contact ayaz18tech@users.noreply.github.com.
