# Simple Chatbot
Constructing a chatbot using the OpenAI Legacy Completion API

Chatbots
In this exercise, we will construct our own chatbot using the OpenAI Legacy Completion API. All TODOs are located in the get_response function.

## Creating a Single String
### Why not Chat Completion API? Why are we using v0 instead of v1 of this package?
As we have seen earlier, the input to a transformer is a string of text. Similarly, the Legacy Completion API accepts a single string prompt as input.

Whereas the OpenAI Chat Completion API accepts a list of JSON elements, indicating that OpenAI is performing processing of our input under the hood to transform the input list of JSONs into a single string.

To best understand how chatbots are built atop the transformer, in this exercise, we use the more "bare bones" Legacy Completion API from openai v0 rather than the Chat Completion API from openai v1. Please ensure that you are running this code in a Udacity Workspace, or in another environment where openai v0 is installed, otherwise you will encounter errors.

### Action 1
Implement the logic to create the flattened_convo variable. The convo variable is a list of strings, and flattened_convo is  a single string.

### Managing Chat History
We will also explore how to manage an ever-growing chat history. We need to keep the token length of our single string prompt under the LLM's attention window while also allocating headroom for the LLM response. So, we will need to prioritize what context is retained and what is removed.

### Action 2
Your second and third action are to implement two different approaches to managing chat history. Both of them involve removing part of the chat history.

Simple truncation: Removing the oldest element in the conversation (keeping the elements at index 1 and beyond)
Retaining system prompt: Keeping the oldest element in the conversation and removing the second oldest element (removing the element at index 1)
