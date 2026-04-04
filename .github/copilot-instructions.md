# GitHub Copilot Instructions for 209 Mesh Network v1

## Project Overview

This is an educational repository containing self-paced labs for learning Google Cloud's Generative AI capabilities, specifically focusing on Gemini multimodal models and Retrieval-Augmented Generation (RAG) techniques.

## Technology Stack

- **Language**: Python 3
- **Platform**: Google Cloud Platform (Vertex AI)
- **Primary Framework**: Jupyter Notebooks
- **AI Models**: Google Gemini (Pro, Pro Vision)
- **Key Libraries**:
  - `google-cloud-aiplatform` (Vertex AI SDK)
  - `pymupdf` (PDF processing)
  - `PIL/Pillow` (Image processing)

## Coding Guidelines

### Python & Jupyter Notebooks

1. **Cell Structure**: Maintain clear separation between setup, configuration, and execution cells
2. **Code Style**: Follow PEP 8 guidelines for Python code
3. **Documentation**: Include markdown cells with clear explanations for educational purposes
4. **Error Handling**: Include appropriate try-catch blocks when working with external APIs and file operations
5. **Resource Management**: Always clean up resources (close files, clear large objects from memory)

### Google Cloud & Vertex AI Best Practices

1. **Authentication**: Use proper Google Cloud authentication patterns
2. **Project Configuration**: Always specify project ID and location explicitly
3. **API Initialization**: Initialize Vertex AI at the beginning of notebooks with `vertexai.init()`
4. **Model Selection**: Use appropriate Gemini models:
   - `gemini-pro` for text-only tasks
   - `gemini-pro-vision` for multimodal (text + images/video) tasks
5. **Safety Settings**: Configure appropriate safety settings for generative content
6. **Streaming Responses**: Handle streaming responses properly when using `generate_content(stream=True)`

### Generative AI & Prompt Engineering

1. **Clear Prompts**: Write specific, well-structured prompts with clear instructions
2. **Context Management**: Keep context within model token limits
3. **Temperature Settings**: Use appropriate temperature values (0.0-1.0) based on use case
4. **Output Validation**: Always validate and handle unexpected AI outputs gracefully
5. **Educational Context**: Add explanations that help learners understand why certain prompting strategies work

### Data Processing

1. **PDF Handling**: Use PyMUPDF for efficient PDF text and image extraction
2. **Image Processing**: Use PIL/Pillow for image manipulation and format conversion
3. **File Paths**: Use `pathlib.Path` for cross-platform path handling
4. **Cloud Storage**: Use `gsutil` commands or Cloud Storage SDK for GCS operations
5. **Data Privacy**: Never commit sensitive data, API keys, or credentials

### Multimodal RAG Implementation

1. **Document Chunking**: Split documents into appropriate chunk sizes for embedding
2. **Metadata Extraction**: Capture comprehensive metadata (text, images, page numbers)
3. **Semantic Search**: Implement efficient similarity search over document embeddings
4. **Context Augmentation**: Properly format retrieved context for LLM prompts
5. **Response Quality**: Validate that RAG responses are grounded in retrieved documents

## Testing & Validation

1. **Notebook Execution**: Ensure cells can be run sequentially without errors
2. **Output Verification**: Include cells that verify expected outputs for learning objectives
3. **API Response Handling**: Test edge cases for API responses (empty, errors, timeouts)
4. **Visual Validation**: When processing images/videos, include display cells for manual verification

## Documentation Standards

1. **Learning Objectives**: Clearly state what learners will accomplish in each section
2. **Step-by-Step Instructions**: Break complex tasks into clear, numbered steps
3. **Code Comments**: Explain non-obvious code logic inline
4. **Examples**: Provide concrete examples with expected outputs
5. **Troubleshooting**: Include common issues and solutions where applicable

## Security & Privacy

1. **No Hardcoded Credentials**: Never commit API keys, tokens, or credentials
2. **Environment Variables**: Use environment variables or secure credential management
3. **Data Handling**: Be mindful of PII and sensitive data in examples
4. **API Quotas**: Implement rate limiting and quota management for API calls

## Dependencies Management

1. **Version Pinning**: Specify compatible version ranges for critical dependencies
2. **Installation Instructions**: Provide clear pip install commands in notebook cells
3. **Compatibility**: Test with Python 3.8+ environments
4. **Cloud Environment**: Optimize for both local Jupyter and Google Colab environments

## Common Patterns to Follow

### Initializing Vertex AI
```python
import vertexai

PROJECT_ID = "your-project-id"
LOCATION = "us-central1"

vertexai.init(project=PROJECT_ID, location=LOCATION)
```

### Creating Multimodal Content
```python
from vertexai.generative_models import GenerativeModel, Part

model = GenerativeModel("gemini-pro-vision")
response = model.generate_content([
    Part.from_uri("gs://bucket/image.jpg", mime_type="image/jpeg"),
    "Describe this image in detail."
])
```

### Handling Streaming Responses
```python
for chunk in response:
    print(chunk.text, end="")
```

## What to Avoid

1. ❌ Don't hardcode file paths - use configurable variables
2. ❌ Don't skip error handling for API calls
3. ❌ Don't process large files without memory management
4. ❌ Don't use deprecated Vertex AI SDK methods
5. ❌ Don't create cells that depend on out-of-order execution
6. ❌ Don't commit large binary files or datasets to the repository
7. ❌ Don't use synchronous code for long-running operations without progress indicators

## Repository-Specific Notes

- This is a **learning-focused repository** - prioritize clarity and educational value over optimization
- The primary artifact is a Jupyter notebook, not a traditional application
- Code should be runnable in both local Jupyter environments and Google Colab
- Focus on demonstrating concepts rather than production-ready implementations
