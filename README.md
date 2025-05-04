# Multimodal Story Generation

## Overview

This project implements an AI-powered storytelling pipeline that creates immersive narratives with accompanying illustrations from minimal user input. The system uses a LangGraph-based directed workflow to orchestrate the story generation, validation, image creation, and compilation processes.

## Features

- **Story Generation from Simple Prompts**: Transform brief user inputs into rich, coherent narratives
- **Retrieval Augmented Generation (RAG)**: Enhances story context using a knowledge base of characters, locations and objects
- **Automated Quality Control**: Validates generated stories against structural and thematic criteria
- **Intelligent Image Generation**: Creates scene illustrations based on story content
- **Image Quality Validation**: Ensures generated images match their intended scene descriptions
- **PDF Compilation**: Combines validated text and images into a professionally formatted document

## Architecture

The project uses a LangGraph workflow with the following components:

1. **Context Retrieval**: Enhances user prompts with relevant contextual elements
2. **Story Generation**: Creates structured narratives using Llama 3.3 70B
3. **Story Validation**: Ensures story quality, coherence, and alignment with prompt
4. **Image Prompt Generation**: Identifies key scenes and creates image generation prompts
5. **Image Generation**: Creates illustrations using Stable Diffusion
6. **Image Validation**: Verifies image-prompt alignment and regenerates if needed 
7. **PDF Compilation**: Formats and combines story text and images into a polished document

## Requirements

```
langgraph
langchain-community
faiss-cpu
groq
torch
diffusers
transformers
reportlab
pillow
```

## Setup

1. Clone the repository
2. Install dependencies:
   ```
   pip install -r requirements.txt
   ```
3. Set up your Groq API key:
   ```python
   GROQ_API_KEY = "your-api-key-here"
   ```

## Usage

1. Run the notebook (`GenAI_Project.ipynb`)
2. Set your input prompt:
   ```python
   input_prompt = "There once was a young little girl in a magical forest. She came across a map"
   ```
3. Execute the workflow:
   ```python
   result = run_workflow(input_prompt)
   ```
4. The compiled story will be saved as `compiled_story.pdf`

## Example Output

The system will generate:
- A structured story with beginning, middle, and end
- Scene illustrations matching key moments in the narrative
- A formatted PDF with text and images arranged appropriately

## Limitations

- Image generation uses Stable Diffusion 2.1 which has limit of 75 tokens per input
- Image consistency across scenes may vary due to context window constraints
- For improved visual quality, consider integrating with more advanced image generation models

## Future Improvements

- Integration with more advanced image generation models
- Audio narration support
- Interactive elements in the final document
- Style customization options
- Multi-language support
