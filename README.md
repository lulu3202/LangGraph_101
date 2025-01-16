# LangGraph_101 - Chatbot with LangGraph and LangChain

## Purpose
This project demonstrates building a simple chatbot using LangGraph and LangChain libraries. It leverages the Gemma2-9b-It language model from Groq for generating responses and LangGraph for managing the chatbot's conversational flow.

## Structure
The code is structured into four main parts:

1. **Installation and Setup:**
   - Installs necessary libraries: `langgraph`, `langsmith`, `langchain`, `langchain_groq`, and `langchain_community`.
   - Retrieves API keys for Groq and Langsmith from user data (ensure these are securely stored).
   - Sets environment variables for LangChain API key, tracing, and project name.

2. **Language Model Initialization:**
   - Imports `ChatGroq` from `langchain_groq`.
   - Initializes the language model `llm` with Groq API key and model name ("Gemma2-9b-It").

3. **Chatbot State Management with LangGraph:**
   - Defines a `State` class using `TypedDict` to manage the chatbot's conversational state, primarily storing messages.
   - Creates a `StateGraph` instance (`graph_builder`) to define the chatbot's flow.
   - Defines a `chatbot` function that updates the state by invoking the language model with the current messages and returning the response.
   - Adds a "chatbot" node to the graph and connects it to the start and end nodes, establishing the flow: `START -> chatbot -> END`.
   - Compiles the graph.

4. **Chatbot Interaction:**
   - Enters an infinite loop to continuously interact with the user.
   - Prompts the user for input.
   - If the user enters "quit" or "q", the loop breaks, ending the conversation.
   - Processes the user input by streaming it through the graph, updating the state, and printing the assistant's response.

## How it Works
- The chatbot takes user input and sends it to the Gemma2-9b-It language model via Groq.
- The language model generates a response based on the input and conversation history.
- LangGraph manages the conversational state and flow, ensuring the chatbot maintains context.
- The chatbot continues to interact with the user until they type "quit" or "q".

## Dependencies
- `langgraph`
- `langsmith`
- `langchain`
- `langchain_groq`
- `langchain_community`

## Usage

1. Install the required dependencies.
2. Set up your Groq and Langsmith API keys.
3. Run the code in a Google Colab environment.
4. Interact with the chatbot by typing messages and pressing Enter.
5. Type "quit" or "q" to end the conversation.

## Acknowledgements
[Krish Naik](https://www.youtube.com/watch?v=gqvFmK7LpDo)
