***Retrieval-Augmented Generation (RAG) Chatbot***

This project implements a Retrieval-Augmented Generation (RAG) chatbot using OpenAI's GPT models and Pinecone for vector storage and retrieval. The chatbot stores conversation history, retrieves relevant context using vector embeddings, and generates responses based on the retrieved context.

**Features**

Conversation History Storage    : Chat history is stored in Pinecone as dense vector embeddings for efficient retrieval.

Contextual Response Generation  : Uses OpenAI's GPT model to generate responses based on retrieved context.

Token Management                : Ensures that prompts and responses stay within a specified token limit.

Custom Embeddings               : Uses the intfloat/e5-small-v2 model for generating embeddings for text inputs.

**Project Structure**

store_chat_history       : Stores chat history in Pinecone by converting text into vector embeddings.

fetch_relevant_messages  : Retrieves the most relevant chat history entries using a query embedding.

generate_response        : Generates a response using OpenAI's GPT model, including relevant context.

process_user_input       : Combines the above functions to handle user queries end-to-end.

test_final_prompt        : A test function to validate the RAG mechanism and ensure proper token usage.

**Requirements**

Python 3.8+

Libraries:

openai

pinecone-client

torch

transformers

tiktoken

**Usage**

OpenAI API key              : Set as an environment variable OPENAI_API_KEY.

Pinecone API key            : Replace the placeholder in the script or set as an environment variable.

Initialize Pinecone         : Create a Pinecone index with a dimensionality matching the embedding size (e.g., 768 for intfloat/e5-small-v2).

Store Conversation History  : The store_chat_history function will upsert the provided conversation into Pinecone.

Query the Chatbot           : Enter a query, and the chatbot will:

Retrieve relevant history using Pinecone.

Generate a response based on the retrieved context.

Test the System             : Use the test_final_prompt function to validate the chatbot's response.

Pinecone Dependency         : Requires a valid Pinecone index for storage and retrieval.

**Future Enhancements**

Integrate more advanced GPT models.
Add a frontend interface for user interaction.
Implement real-time chat functionality with a web framework.
