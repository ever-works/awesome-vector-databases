## Overview

Document Loaders are components in LLM frameworks (LangChain, LlamaIndex, Haystack) that fetch data from various sources and convert it into a standardized document format for downstream processing in RAG pipelines.

## Common Document Loaders

### Text-Based
- **TextLoader**: Plain text files
- **CSVLoader**: Spreadsheet data
- **JSONLoader**: Structured JSON data
- **MarkdownLoader**: Markdown documents

### Rich Documents
- **PyPDFLoader**: PDF extraction
- **UnstructuredPDFLoader**: Advanced PDF parsing with layout preservation
- **Docx2txtLoader**: Microsoft Word documents
- **UnstructuredHTMLLoader**: HTML pages with structure

### Web Sources
- **WebBaseLoader**: Website scraping
- **GitHubLoader**: GitHub repositories
- **NotionDBLoader**: Notion databases
- **ConfluenceLoader**: Confluence pages

### Databases
- **SQLDatabaseLoader**: SQL databases
- **MongoDBLoader**: MongoDB collections
- **BigQueryLoader**: Google BigQuery

### Multimedia
- **YoutubeLoader**: Video transcripts
- **AudioLoader**: Audio file transcription
- **ImageLoader**: Image content extraction

## Document Structure

Loaders typically output documents with:
```python
{
    "page_content": "The actual text content",
    "metadata": {
        "source": "file.pdf",
        "page": 1,
        "author": "...",
        "created_at": "..."
    }
}
```

## Integration with RAG Pipeline

1. **Load**: Document loader fetches and parses data
2. **Split**: Text splitter chunks documents
3. **Embed**: Embedding model creates vectors
4. **Store**: Vector database stores embeddings
5. **Retrieve**: Query retrieves relevant chunks

## Advanced Features

### Layout Preservation
Tools like Unstructured.io and LlamaParse:
- Preserve table structures
- Maintain multi-column layouts
- Extract images and captions
- Recognize document hierarchy

### Metadata Extraction
- Automatic extraction of creation dates, authors
- URL and source tracking
- Page numbers and sections
- Custom metadata fields

### Batch Processing
- Process multiple documents concurrently
- Resume from failures
- Progress tracking

## Popular Loader Libraries

### LangChain
```python
from langchain.document_loaders import PyPDFLoader
loader = PyPDFLoader("document.pdf")
documents = loader.load()
```

### LlamaIndex (LlamaHub)
- 100+ connectors
- Specialized loaders for enterprise sources
- Community-contributed loaders

### Unstructured
- Unified API for multiple formats
- Advanced parsing for complex layouts
- Pre-processing and chunking

## Best Practices

1. **Choose Right Loader**: Match loader to source format
2. **Preserve Metadata**: Keep source tracking for citations
3. **Handle Errors**: Implement retry logic and error handling
4. **Optimize for Scale**: Use batch processing for large datasets
5. **Test Extraction Quality**: Verify parsing accuracy

## Common Challenges

- PDF table extraction
- Scanned document OCR
- Multi-column layouts
- Nested document structures
- Large file handling

## Pricing

Most loaders are free and open-source. Commercial options:
- Unstructured.io API: Paid plans
- LlamaParse: Usage-based pricing
- Custom enterprise connectors: Varies