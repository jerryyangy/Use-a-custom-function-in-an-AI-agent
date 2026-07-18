# Use a custom function in an AI agent

It shows how to build an Azure AI agent that can call custom Python functions as tools. The sample agent acts as an astronomy assistant that looks up the next visible astronomical event for a location, calculates telescope observation costs, and generates a report.

## What the lab covers

- Create a Microsoft Foundry project from VS Code using the Foundry Toolkit extension.
- Deploy a `gpt-5` model for the agent.
- Clone the starter repository and configure the local Python environment.
- Add custom functions in `functions.py` and register them as agent tools.
- Create an agent with `FunctionTool` definitions and process function calls in a conversation loop.
- Test the agent with prompts that combine event lookup, cost calculation, and report generation.
- Clean up the deployed model and Azure resources after finishing.

## Main workflow

1. Install the Foundry Toolkit for VS Code and create a Foundry project.
2. Deploy a model from the Model Catalog.
3. Clone `mslearn-ai-agents` and open `Labfiles/02-agent-custom-tools`.
4. Set up the Python virtual environment and update the `.env` file with the project endpoint and model deployment name.
5. Implement `next_visible_event(location)` in `functions.py` to return the next visible astronomical event for a location.
6. Define three function tools in `agent.py`:
   - `next_visible_event`
   - `calculate_observation_cost`
   - `generate_observation_report`
7. Create an agent named `astronomy-agent` with these tools and connect it to the Foundry project.
8. Send user prompts, handle `function_call` responses, pass tool outputs back to the model, and display the final answer.
9. Delete the agent and remove Azure resources when done.

## Example usage

It uses prompts such as asking for the next event visible from South America and the cost of 5 hours of premium telescope time at normal priority. The agent can then combine tool outputs to produce a useful answer and, on follow-up, generate a structured observation report.

## Prerequisites

- Visual Studio Code
- An active Azure subscription
- Python 3.13 or later
- Git

## Notes

- Python 3.13 is recommended because some dependencies are not yet compiled for Python 3.14.
