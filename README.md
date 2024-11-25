
# Chat with PDF :books:

This project enables users to upload PDF documents and interact with them using a conversational interface. Users can ask questions about the content of the PDFs, and the application provides intelligent answers by leveraging a conversational retrieval chain with memory.

---

## Features

- **PDF Upload:** Upload multiple PDF files for text extraction.
- **Text Splitting:** Splits extracted text into manageable chunks for efficient processing.
- **Vector Store Creation:** Embeds the text chunks into a FAISS vector store for semantic search.
- **Conversational Interface:** Ask questions about the PDFs and receive contextually accurate responses.
- **Memory Retention:** Retains chat history for a seamless conversation flow.

---

## Requirements

### Dependencies

The following Python packages are required:
- `streamlit`
- `PyPDF2`
- `langchain`
- `langchain-community`
- `faiss-cpu` (for FAISS vector store)

Install them using pip:

```bash
pip install streamlit PyPDF2 langchain langchain-community faiss-cpu
```

---

## Setup and Usage

1. Clone this repository or copy the code into a Python script.
2. Install the required dependencies using the above command.
3. Run the Streamlit app:

   ```bash
   streamlit run your_script_name.py
   ```

4. Upload one or more PDF files in the sidebar.
5. Ask questions about the uploaded PDFs in the text input field.

---

## Code Breakdown

### `get_pdf_text(pdf_docs)`
Extracts text from the uploaded PDFs.

### `get_text_chunks(text)`
Splits the extracted text into chunks for efficient vector storage.

### `get_vectorstore(text_chunks)`
Embeds text chunks using the Ollama Embeddings model and stores them in a FAISS vector store.

### `get_conversation_chain(vectorstore)`
Creates a conversational retrieval chain using the Ollama LLM and a conversation buffer for memory.

### `handle_userinput(user_question)`
Handles user queries, retrieves relevant information, and displays chat history.

### `main()`
Main function to render the Streamlit UI, manage user interactions, and control the overall application flow.

---

## How It Works

1. **Upload PDFs**: Upload documents in the sidebar using the file uploader.
2. **Add Data**: Click "Add Data" to extract, split, and store the document text in a vector store.
3. **Ask Questions**: Type your questions in the input field to receive AI-generated answers based on the content of the uploaded documents.
4. **Conversation Memory**: The chat history is displayed, retaining both user and bot messages.

---

## Customization

### Model and Embeddings
- The application uses the Ollama Embeddings and Mistral model. Modify the `OllamaEmbeddings` and `Ollama` calls if you wish to use a different model.

### Chat Interface
- The HTML templates for chat (`css`, `bot_template`, and `user_template`) can be customized for styling.

---

## Future Improvements
- Add support for other document formats (e.g., Word, Excel).
- Incorporate additional LLMs for varied conversational capabilities.
- Optimize vector store storage for large-scale document processing.
- Introduce multi-user session support.

---

## License

This project is released under the MIT License. Feel free to use, modify, and distribute the code.

--- 

## Credits

Developed using:
- [Streamlit](https://streamlit.io/)
- [LangChain](https://www.langchain.com/)
- [PyPDF2](https://pythonhosted.org/PyPDF2/)
- [FAISS](https://faiss.ai/)
