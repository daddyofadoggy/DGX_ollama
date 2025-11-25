# DGX Ollama Chat Client

A Python client for interacting with Ollama models running on a DGX server through Open WebUI. This client uses the OpenAI Python SDK to send chat completion requests to your locally hosted Ollama instance.

## Description

This project provides a simple and efficient way to communicate with Ollama models hosted on a DGX server. It leverages the OpenAI-compatible API interface provided by Open WebUI, making it easy to integrate with existing OpenAI-based workflows.

## Prerequisites

- Python 3.7 or higher
- Access to a DGX server running Ollama with Open WebUI
- API key for your Open WebUI instance

## Installation

1. Clone the repository:
```bash
git clone https://github.com/daddyofadoggy/DGX_ollama.git
cd DGX_ollama
```

2. Create and activate a virtual environment:
```bash
python3 -m venv myvenv
source myvenv/bin/activate  # On Windows: myvenv\Scripts\activate
```

3. Install required packages:
```bash
pip install -r requirements.txt
```

## Configuration

1. Create a `.env` file in the project root directory:
```bash
touch .env
```

2. Add your Ollama API key to the `.env` file:
```
OLLAMA_KEY=your_api_key_here
```

3. Update the `chat_client.py` file with your server details:
   - `SERVER_URL`: Your DGX server URL (default: `http://10.0.0.194:8080/`)
   - `MODEL`: The Ollama model you want to use (default: `gpt-oss:20b`)

## Usage

Run the chat client:
```bash
python chat_client.py
```

The script will send a test message to your Ollama instance and print the response.

## Customization

To modify the chat interaction, edit the `messages` parameter in `chat_client.py`:

```python
response = client.chat.completions.create(
    model=MODEL,
    messages=[{"role": "user", "content": "Your question here"}],
)
```

## Requirements

- `openai` - OpenAI Python SDK
- `python-dotenv` - Environment variable management

## License

MIT

## Contributing

Feel free to open issues or submit pull requests for improvements.
