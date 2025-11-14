# AI-ML-Assignment-5-Simple-RAG

# Love Is: A Poetic RAG System  
Author: Ingrid Arenas Rosas  
LLM Used: google/flan-t5-small  
Embedding Model: sentence-transformers/all-MiniLM-L6-v2  

## Project Overview

This project uses Retrieval-Augmented Generation (RAG) to answer questions about the poem "Love Is" by Nikki Giovanni. The system retrieves relevant poetic lines using semantic search and generates answers using a lightweight language model.

## Retrieval Summary

### Question 1: What is love?
Retrieved:
- "Some people forget that love is tucking you in and kissing you ‘Good night’ no matter how young or old you are."
- "Few recognize that love is commitment, responsibility — no fun at all unless love is you and me."

Generated Answer:
Q1:  commitment, responsibility


### Question 2: What does the poem say love is for all ages?
Retrieved:
- "Some people don’t remember that love is listening and laughing and asking questions no matter what your age."

Generated Answer:
Q2: listening and laughing and asking questions no matter what your age


### Question 3: What year was this poem written?
Initial Behavior:
The model guessed incorrect years like 1891 and 1892.

Fix:
Added a metadata chunk: "The poem 'Love Is' by Nikki Giovanni was published in 1997 in her collection titled 'Love Poems'."

Retrieved:
- The metadata chunk

Generated Answer:
Q3: 1997


## Analysis of Results

Without retrieval, the language model produced vague or incorrect answers, including hallucinated publication years. After adding relevant context and metadata, the RAG system generated accurate and grounded responses. This shows that retrieval successfully mitigates hallucination and improves factual reliability.

## Technologies Used

- Python
- FAISS for vector indexing
- SentenceTransformers for embeddings
- HuggingFace Transformers for generation
