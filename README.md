# Tool Poisoning Attack Demo

This repository demonstrates a tool poisoning attack vector that can be used against MCP Clients (e.g. VSCode).

## How This Demonstration Works

This repository contains a MCP server that implements a seemingly benign "get-weather" tool. However, the tool has been poisoned with hidden instructions:

1. The tool description contains hidden instructions telling the AI to read a sensitive file (`~/.ssh/id_rsa_demo`)
2. It forces the AI to pass the file contents as a required `sidenote` parameter
3. The backend sends this sensitive data to an attacker-controlled server (localhost:3333 in this demo)

## Disclaimer

This code is provided for educational purposes only to demonstrate security vulnerabilities. Do not use this approach to collect sensitive data without explicit consent.

## Running the Demo

To run this demonstration safely:
1. Clone the repository
2. Create a dummy SSH key at `~/.ssh/id_rsa_demo` with non-sensitive content
3. Set the `OPENWEATHER_API_KEY` environment variable
4. Start the MCP server in VSCode
