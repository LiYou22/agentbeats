## PersonaGym

### 1. Setup

Follow the tutorials from [AgentBeats official guide](https://github.com/agentbeats/agentbeats). Specifically, you need to:

* Set up environment

```
cd /path/to/agentbeats

python -m venv venv # Requires python>=3.11

venv\Scripts\activate # On Windows
source venv/bin/activate # On macOS/Linux

pip install agentbeats
```

* Setup your OPENAI_API_KEY and OPENROUTER_API_KEY:

```
export OPENAI_API_KEY="your-openai-api-key-here"
export OPENROUTER_API_KEY="your-openrouter-api-key-here"
```

### 2. Selfhost

Follow the docs from [AgentBeats Self-Hosting Guide](https://github.com/agentbeats/agentbeats/blob/main/docs/self_host_instruction.md). The PesonaGym integration has been tested under Local Development mode. Start by:

```
agentbeats install_frontend
agentbeats deploy
```

### 3. Launch Agents

Run the following scripts to start both white and green agents:
```
agentbeats load_scenario scenarios/personagym \
    --launch-mode current \
    --register_agents \
    --backend http://localhost:9000
```
Three agents will be launched:
* Green agent runs at `http://localhost:8031`
* Two white agents runs at `http://localhost:8021` and `http://localhost:8011`
* You will need these information to register the agents

### 4. Host A Battle

* Navigate to `http://localhost:5173`. Follow the tutorials from [AgentBeats official guide](https://github.com/agentbeats/agentbeats) to register your agents. When registering the green agents, the task index specifies the persona index from PersonaGym benchmark. Feel free to change index to switch the persona.
* Navigate to **"Stage Battle"**
    * Choose **"PersonaGym Evaluator"** as the Green Agent
    * Choose two white agents as opponents
    * Start the battle
    * The battle last for half an hour. Please stay patient.
