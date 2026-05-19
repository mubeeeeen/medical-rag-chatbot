# Medical RAG Chatbot - Version 1

This project is a basic Medical Retrieval-Augmented Generation (RAG) chatbot built using the MedQuAD dataset.

The chatbot retrieves relevant medical question-answer chunks using semantic search and generates grounded answers using a Groq-hosted LLM.

## Features

- Loads the MedQuAD medical QA dataset
- Cleans missing values from the dataset
- Creates text chunks from medical questions and answers
- Generates embeddings using Sentence Transformers
- Stores embeddings in a FAISS vector database
- Retrieves relevant medical documents based on user query
- Generates answers using Groq LLM
- Displays retrieved sources and matched questions

## Tech Stack

- Python
- Google Colab
- Hugging Face Datasets
- Sentence Transformers
- FAISS
- LangChain Groq
- Groq LLM

## Workflow

```text
User Question
      ↓
Sentence Transformer Embedding
      ↓
FAISS Vector Search
      ↓
Top Relevant Medical Chunks
      ↓
Groq LLM
      ↓
Final Answer
```

## Example Query

```text
How is high blood pressure treated?
```

## Example Output

```text
High blood pressure is treated with lifestyle changes and medicines.
Medicines may include diuretics, beta blockers, ACE inhibitors, ARBs,
calcium channel blockers, alpha blockers, central acting agents, and vasodilators.
```

## Retrieved Source Example

```text
Dataset Source: NIHSeniorHealth
Matched Question: What are the treatments for High Blood Pressure?
```

## Current Status

This is Version 1 of the project.

Implemented:

- Data loading
- Data cleaning
- Embedding generation
- FAISS vector database
- Semantic retrieval
- LLM-based answer generation
- Source display

## Future Improvements

- Add citations inside the final answer
- Add relevance score threshold
- Remove duplicate retrieved chunks
- Add query expansion
- Add Streamlit interface
- Deploy the chatbot
- Add RAG evaluation

## How to Run

1. Clone this repository or open the notebook in Google Colab.
2. Install the required libraries:

```bash
pip install -r requirements.txt
```

3. Add your Groq API key when prompted.
4. Run the notebook cells step by step.

## Disclaimer

This project is for educational purposes only.

It is not intended to provide medical advice, diagnosis, or treatment.

Always consult a qualified healthcare professional for medical concerns.
