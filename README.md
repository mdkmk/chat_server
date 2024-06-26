# socktalk - A Robust Socket-based AI Chat Server and Multi-user Chat Client

**socktalk** is a chat server and client developed using Python's socket programming. It affords real-time, multi-user interactions and integrates with OpenAI's GPT models to offer an AI-driven chatting experience.

## Features
- **Multi-User Support**: Manages multiple connections simultaneously to support multi-user interactions.
- **Efficient Message Handling**: Uses non-blocking sockets and `select.select()` for real-time, concurrent message processing.
- **AI Integration**: Augments multi-user chat with AI-driven responses, configurable for different operational modes.
- **Standardized Protocol**: Implements a simple message protocol with fixed-length headers to streamline communication.
- **Versatile Client Options**: Offers both a sophisticated graphical user interface and a lightweight terminal-based client.

For further details, visit the [GitHub repository for socktalk](https://github.com/mdkmk/socktalk/tree/main).
## Installation

### From GitHub
To install "socktalk" from GitHub:
1. Clone the repository:
   ```bash
   git clone https://github.com/mdkmk/socktalk
   cd socktalk
2. Install the package:
    ```bash
    python setup.py install

### Using pip
- To install using pip directly from PyPI:
    ```bash
    pip install socktalk

## Usage - Run different components of "socktalk" using the following commands:
Set up the .env file in your working directory to configure AI behaviors and server/client settings without using command-line flags.
Alternatively, you can use command-line flags to override .env file or default settings.
### **AI-enhanced chat server:**
```bash
socktalk --ai
```
With flag override:
```bash
socktalk --ai --openai_api_key=YOUR_OPENAI_API_KEY_HERE --ai_mode2_active=False --ai_mode1_interval=3
```
---
### **Chat server without AI integration:**
```bash
socktalk --server
```
With flag override:
```bash
socktalk --server --server_ip=127.0.0.1 --server_port=1234
```
---
### **GUI-enabled multi-user chat client:**
```bash
socktalk --client
```
With flag override:
```bash
socktalk --client --server_ip=127.0.0.1 --server_port=1234
```
---
### **Terminal-based chat client:**
```bash
socktalk --terminal
```
With flag override:
```bash
socktalk --terminal --server_ip=127.0.0.1 --server_port=1234
```
---
## AI Chatbot Configuration
### AI Client Modes:
1. Respond every N lines: The AI reads the conversation and responds after every N lines.
2. Respond every N seconds: The AI generates new content at specified intervals.

### Example .env File Configuration
 Below is an example .env file. Update the OpenAI chatgpt API key and ensure you have at least $5 credit on your OpenAI account.
 A valid OPENAI_API_KEY is required for AI functionality. The AI client has two modes which can be toggled on or off.
 AI response intervals, model, and content prompt are configurable. Full chat history can be sent to the API for context.
 If the remaining .env variables are not specified or called as a flag, defaults in the example below will be used.

    OPENAI_API_KEY=YOUR_OPENAI_API_KEY_HERE
    SERVER_IP=127.0.0.1
    SERVER_PORT=1234
    SEND_FULL_CHAT_HISTORY=True
    AI_MODE1_ACTIVE=True
    AI_MODE1_INTERVAL=1
    AI_MODE1_MODEL=gpt-3.5-turbo
    AI_MODE2_ACTIVE=True
    AI_MODE2_INTERVAL=60
    AI_MODE2_MODEL=gpt-3.5-turbo
    AI_MODE2_CONTENT="Say something interesting from a random Wikipedia page and start your response with 'Did you know', but don't mention the source."


