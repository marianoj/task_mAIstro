# Task mAIstro

Task mAIstro allows you to track your ToDos through natural conversation: 

* Tell it about yourself 
* Tell it tasks you need to complete
* Update tasks easily through conversation
* Ask task mAIstro what to to next 

Task mAIstro combines an agent with long-term memory to produce a highly personalized task management experience. All information can be stored locally using the LangGraph Studio Desktop App or it can be deployed to LangGraph Platform.

## Key Features

### Natural Language Interface

- Create and update tasks through natural conversation
- No need to learn specific commands or syntax
- Just chat with the assistant as you would with a human

### Smart Memory System

Task mAIstro maintains three types of memory:

1. **ToDo List**
   - Tasks with descriptions
   - Estimated completion times
   - Deadlines
   - Actionable solutions
   - Status tracking

2. **User Profile**
   - Remembers personal details
   - Tracks preferences
   - Maintains context about your life and work

3. **Update Instructions**
   - Learns how you prefer tasks to be managed
   - Adapts to your organizational style
   - Maintains your preferences for task updates

## Quickstart 

You can deploy the app locally with the LangGraph Studio Desktop App or to LangGraph Cloud. 

### Locally 

Populate the `.env` file with your `OPENAI_API_KEY` key: 
```
cp .env.example .env
```

Download the LangGraph Studio desktop app for Mac [here](https://github.com/langchain-ai/langgraph-studio?tab=readme-ov-file#download).

Load this repository as a project in LangGraph Studio.

Start chatting with the task mAIstro!

### LangGraph Cloud

In your LangSmith account, create a new deployment with this repository's `main` branch.

Set your `OPENAI_API_KEY` as a secret when creating the deployment.

Interact with the deployment through the LangGraph Studio web UI.

Use the `ntbk/connecting_to_graph.ipynb` notebook to interact with the deployed graph via .

## Audio UX

See the `ntbk/audio_ux.ipynb` notebook for an example of how to add an audio interface to your graph. 

## Learning More

See [Module 5 of our LangChain Academy Course on LangGraph](https://academy.langchain.com/courses/intro-to-langgraph) to learn how to build this app from scratch! 
