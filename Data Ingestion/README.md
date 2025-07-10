## 📚 Document Loaders Summary (LangChain)

This project uses [LangChain](https://python.langchain.com/docs/integrations/document_loaders/) document loaders to ingest and structure data from various sources. These loaders help transform raw files or web content into a standardized format for downstream LLM pipelines like chunking, embedding, and retrieval.

### 🚀 Supported Loaders

| #  | Loader Type                | Import Path                                      | Best Used For                             |
|----|----------------------------|--------------------------------------------------|-------------------------------------------|
| 1  | `TextLoader`               | `langchain_community.document_loaders.text`      | Plain text files (`.txt`, logs, notes)    |
| 2  | `PyPDFLoader`              | `langchain_community.document_loaders`           | Multi-page PDFs (e.g., syllabi, reports)  |
| 3  | `WebBaseLoader`            | `langchain_community.document_loaders`           | Full website or blog ingestion            |
| 4  | `WebBaseLoader (Custom)`   | `langchain_community.document_loaders` + `bs4`   | Selective HTML parsing using CSS classes  |
| 5  | `ArxivLoader`              | `langchain_community.document_loaders`           | Arxiv.org research papers by ID/query     |
| 6  | `WikipediaLoader`          | `langchain_community.document_loaders`           | General knowledge topics from Wikipedia   |

### 🧠 Notes

- For **local file ingestion**, use `TextLoader` or `PyPDFLoader`.
- For **web scraping**, `WebBaseLoader` provides a flexible way to fetch full or partial content.
- `ArxivLoader` and `WikipediaLoader` are great for **domain knowledge ingestion** from external sources.
- All loaded documents return a list of LangChain `Document` objects, ready for chunking and embedding.

### 📦 Next Steps

Once data is loaded:
1. **Chunk** it into manageable sizes (e.g., 500 tokens with overlap)
2. **Embed** it using models like OpenAI or BGE
3. **Store** in a vector DB (e.g., Chroma, Pinecone)
4. Use for **retrieval-augmented generation (RAG)** or **multi-agent workflows**

---

> 💡 Tip: To extract only relevant content from a webpage, use `bs4.SoupStrainer` with `WebBaseLoader`.


