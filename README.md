# Policy-QA RAG System (Using Gemini Flash 2.0)

This project is a simple Retrieval-Augmented Generation (RAG) pipeline that answers HR-related policy questions using the **Gemini Flash 2.0 model**. The system retrieves the most relevant document from a local collection of policy files and uses it as context for the model to generate a short and clear answer.

## How the System Works (Simple Explanation)

1. **Load Policy Files**
   All text files inside the `data/` folder are read by the script.

2. **Create Embeddings**
   Each file is converted into vector embeddings using Google’s embedding model.

3. **Store in ChromaDB**
   These embeddings and filenames are saved in a ChromaDB collection for fast similarity search.

4. **User Asks a Question**
   The system takes the user's question.

5. **Retrieve Top Matches**
   It retrieves the top 3 most similar documents, but only uses the best one.

6. **Send to Gemini Flash 2.0**
   The text from this top document is inserted into a short prompt and sent to the **Gemini Flash 2.0 model**.

7. **Final Answer**
   The model returns a brief answer, and the script prints the question, the answer, and the document used.

## Project Structure

```
├── data/
│   └── (policy text files go here)
├── rag.py
├── requirements.txt
└── README.md
```

## Running the Script

```
python rag.py
```

## Model Used

- **Google Gemini Flash 2.0**  
- **Google Text Embedding 004**

