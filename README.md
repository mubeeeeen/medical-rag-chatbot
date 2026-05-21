# Medical RAG Chatbot

This project is a Medical Retrieval-Augmented Generation (RAG) chatbot built using the MedQuAD dataset.

The chatbot retrieves relevant medical question-answer chunks using semantic search and generates grounded answers using a Groq-hosted LLM. The project is developed version by version, starting from a basic RAG pipeline and gradually improving retrieval quality, citations, safety, and query handling.

## Features

- Loads the MedQuAD medical QA dataset
- Cleans missing values from the dataset
- Creates text chunks from medical questions and answers
- Generates embeddings using Sentence Transformers
- Stores embeddings in a FAISS vector database
- Retrieves relevant medical documents based on user query
- Generates answers using Groq LLM
- Displays retrieved sources and matched questions
- Supports citation-based answers
- Handles unrelated questions using a fallback response
- Uses query expansion for better retrieval in Version 3

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
Query Expansion
      ↓
Sentence Transformer Embedding
      ↓
FAISS Vector Search
      ↓
Top Relevant Medical Chunks
      ↓
Relevance Filtering
      ↓
Groq LLM
      ↓
Final Answer with Citations
```

## Project Versions

### Version 1: Basic RAG

Version 1 implements the first working RAG pipeline.

Implemented:

- Loaded the MedQuAD medical QA dataset
- Cleaned missing values
- Created text chunks from questions and answers
- Generated embeddings using Sentence Transformers
- Stored embeddings in FAISS
- Retrieved relevant medical chunks
- Generated answers using Groq LLM
- Displayed retrieved sources

### Version 2: Safer RAG with Citations

Version 2 improves the basic RAG pipeline by making the chatbot safer and easier to verify.

Added:

- Citation-based answers using `[Source 1]`, `[Source 2]`, etc.
- Duplicate retrieved-question removal
- Relevance threshold for weak retrieval
- Fallback response for unrelated questions
- Cleaner source display with matched question and retrieval score
- Safer medical response style

### Version 3: Improved Retrieval

Version 3 improves retrieval quality and user-style question handling.

Added:

- Cosine similarity using normalized embeddings
- FAISS inner product search for similarity-based retrieval
- LLM-based query expansion
- Better handling of patient-style wording
- Source filtering using similarity scores
- Improved fallback for out-of-scope questions

Example:

```text
User Question:
What are signs of sugar disease?

Expanded Query:
sugar disease diabetes high blood sugar symptoms thirst urination fatigue

Result:
The system retrieves diabetes-related chunks and generates an answer with citations.
```

## Example Query

```text
How is high blood pressure treated?
```

## Example Output

```text
High blood pressure can be treated through a combination of lifestyle changes and medication.
Lifestyle changes may include healthy eating, physical activity, maintaining a healthy weight,
quitting smoking, limiting salt intake, and managing stress.

Medications may include diuretics, beta blockers, ACE inhibitors, ARBs, calcium channel blockers,
alpha blockers, central acting agents, and vasodilators. [Source 1], [Source 2]
```

## Retrieved Source Example

```text
Dataset Source: NIHSeniorHealth
Matched Question: What are the treatments for High Blood Pressure?
Similarity Score: 0.6304
```

## Out-of-Scope Example

```text
Question:
Who won the FIFA World Cup?

Answer:
The provided medical documents do not contain enough information.
```

## Repository Structure

```text
medical-rag-chatbot/
│
├── notebooks/
│   ├── medical_rag_v1.ipynb
│   ├── medical_rag_v2.ipynb
│   └── medical_rag_v3.ipynb
│
├── README.md
├── requirements.txt
└── .gitignore
```

## How to Run

1. Clone this repository or open the notebook in Google Colab.
2. Install the required libraries:

```bash
pip install -r requirements.txt
```

3. Add your Groq API key when prompted.
4. Run the notebook cells step by step.

## Future Improvements

- Add LLM-based relevance checking
- Add corrective RAG
- Add medical safety classification
- Add RAG evaluation metrics
- Add Streamlit chatbot interface
- Deploy the chatbot
- Add screenshots and architecture diagram

## Disclaimer

This project is for educational purposes only.

It is not intended to provide medical advice, diagnosis, or treatment.

Always consult a qualified healthcare professional for medical concerns.
