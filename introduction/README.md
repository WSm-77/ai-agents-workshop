
# Quick Start

### Prerequisites
- [Docker](https://www.docker.com/products/docker-desktop/)
- [Task/Taskfile](https://taskfile.dev/docs/installation) (optional, but recommended)


## Option 1: Using Taskfile (Recommended)

**Start the services:**
   ```bash
   task start
   ```
   This will build the Docker images (including the Llama 3.2 model) on first run, and use cached layers on subsequent runs.

#### Available Task Commands

Run `task --list` to see all available commands, or use these common ones:

- `task start` - Start all services 
- `task stop` - Stop all services
- `task run` - Run the agent main function
- `task test` - Run the agent tests

## Option 2: Manual Docker Setup

**Start the services:**
```bash
docker compose up -d --build
```
This will build the images (including pulling the Llama 3.2 model into the Ollama image) on first run, and use cached layers on subsequent runs.

### After Setup is Done, Access Jupyter Notebooks:
   Open your browser and navigate to:
   ```
   http://localhost:8888/tree/introduction
   ```

   _You can also open it within your IDE, using the kernel link_:
   ```
   http://localhost:8888
   ```

## Course Content

The following notebooks and documents will guide you through the workshop:

- **0_theory.md**: Introduction to LLMs, tokens, and the deterministic vs. undeterministic paradigm.
- **1_simple_calls.ipynb**: Learn how to interact with LLMs via basic HTTP API calls.
- **2_function_calling.ipynb**: Using Tools/Functions with LLMs to extend their capabilities.
- **3_structured_output.ipynb**: Getting reliable, typed data from models using PydanticAI. Also covers **Chain of Thought\*** and **Few-shot\*** prompting.
- **4_lets_loop.ipynb\***: A brief dive into what an agent loop looks like under the hood.