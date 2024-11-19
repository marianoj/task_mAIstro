# Task mAIstro

Managing tasks effectively is a universal challenge. Task mAIstro is an AI-powered task management agent that combines natural language processing with long-term memory to create a more intuitive and adaptive experience.

Key features:
* Natural conversation through text and voice to update or add tasks
* Adaptive learning of your management style and preferences
* Persistent memory of tasks, context, and preferences
* Flexible deployment options - local or hosted

## Quickstart

1. Populate the `.env` file: 
```
$ cp .env.example .env
```

2. Download the LangGraph Studio desktop app for Mac [here](https://github.com/langchain-ai/langgraph-studio?tab=readme-ov-file#download).

3. Load this repository as a project in LangGraph Studio.

4. Start chatting with the task mAIstro through the text interface in LangGraph Studio.

5. Interact with your deployment through voice in `ntbk/audio_ux.ipynb`.

## Task mAIstro Application

### Architecture

Task mAIstro leverages [LangGraph](https://langchain-ai.github.io/langgraph/) to maintain three memory types:

1. **ToDo List Memory**
   - Task descriptions and deadlines
   - Time estimates and status tracking
   - Actionable next steps

2. **User Profile Memory**
   - Personal preferences and context
   - Work/life patterns
   - Historical interactions

3. **Interaction Memory**
   - Task management style
   - Communication preferences
   - Organizational patterns

The schema for each memory type as well as the graph flow is defined in `task_maistro.py`. 
The graph flow is orchestrated by a central `task_maistro` node that:
- Chooses to update one of the three memories based on the user's input
- Uses tool calling with the [Trustcall library](https://github.com/hinthornw/trustcall) to update the chosen memory type

For a detailed walkthrough of how this graph is built, check out [Module 5 of our LangGraph Course](https://academy.langchain.com/courses/intro-to-langgraph): 
- All notebooks are available [here](https://github.com/langchain-ai/langchain-academy/tree/main/module-5)
- All notebooks have accompanying videos

### Deployment Options

Task mAIstro offers three flexible deployment paths:

#### 1. LangGraph Studio (Recommended for quickstart)
The fastest way to get started is with [LangGraph Studio](https://github.com/langchain-ai/langgraph-studio):
- Download the [desktop app](https://github.com/langchain-ai/langgraph-studio?tab=readme-ov-file#download)
- Ensure [Docker Desktop](https://docs.docker.com/engine/install/) is running
- Load this repository as a project

#### 2. LangGraph CLI
For developers who prefer the command line:
- Use the [LangGraph CLI](https://langchain-ai.github.io/langgraph/concepts/langgraph_cli/#up)
- Deploy locally with a single command
- Full control over deployment configuration

#### 3. LangGraph Cloud
For production deployments:
- Deploy to [LangGraph Cloud](https://langchain-ai.github.io/langgraph/concepts/langgraph_cloud/)
- Manage through your LangSmith account
- Access via LangGraph Studio web UI

Want to learn more about deployments? Check out [Module 6 of our LangGraph Course](https://academy.langchain.com/courses/intro-to-langgraph) ([notebooks](https://github.com/langchain-ai/langchain-academy/tree/main/module-6))!

## Voice Interface

Task mAIstro supports voice interactions using:
- [OpenAI's Whisper](https://platform.openai.com/docs/guides/speech-to-text) for speech-to-text
- [ElevenLabs](https://github.com/elevenlabs/elevenlabs-python) for text-to-speech

### Setup

1. Install FFmpeg (required for ElevenLabs):
```bash
# macOS
brew install ffmpeg
```

2. See `ntbk/audio_ux.ipynb` for implementation details

### Connecting Voice Interface

In `audio_ux.ipynb`, connect to your deployment using the URL endpoint:
- **Studio**: Found in Studio UI
- **CLI**: Printed to console (e.g., typically `http://localhost:8123`)
- **Cloud**: Available in LangGraph Deployment page

Learn more about voice agents: [MIT Tech Review](https://www.technologyreview.com/2024/09/24/1104422/openai-released-its-advanced-voice-mode-to-more-people-heres-how-to-get-it/) | [OpenAI Blog](https://openai.com/index/introducing-the-realtime-api/). 