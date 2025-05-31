# Embedding Techniques

This folder contains code and notebooks for generating embeddings — numerical vector representations of text capturing semantic meaning.

## What are Embeddings?  
Embeddings convert text into vectors to enable tasks like semantic search and classification.

## Usage  
This project uses a sample text file `speech.txt` as input to generate embeddings.

Example:

```python
from langchain_openai import OpenAIEmbeddings

embeddings = OpenAIEmbeddings(model="text-embedding-3-large",dimensions=1024)

query_result= embeddings.embed_query("Hello, world!")

