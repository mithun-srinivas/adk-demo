# LinkedIn Content Assistant

A Python application that uses Google's Agent Development Kit (ADK) and Gemini AI to automatically generate trending LinkedIn posts from topics. The system uses a multi-agent approach to brainstorm ideas, write drafts, and format content into engaging LinkedIn posts.

## Features

- **Idea Generation**: Brainstorms creative LinkedIn post ideas based on any topic
- **Content Writing**: Expands ideas into full LinkedIn post drafts
- **Post Formatting**: Formats drafts into trending LinkedIn post style
- **Sequential Agent Pipeline**: Uses Google ADK's SequentialAgent to orchestrate the content creation workflow

## Architecture

The application consists of three specialized agents that work together in sequence:

1. **IdeaAgent**: Generates creative LinkedIn post ideas from topics
2. **WriteAgent**: Expands ideas into detailed post drafts
3. **FormatAgent**: Formats drafts into trending LinkedIn posts

All agents are orchestrated by a `SequentialAgent` called `ContentAssistant`.

## Prerequisites

- Python 3.7+
- Google API Key with access to Gemini AI
- Google Agent Development Kit (ADK)

## Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd adk-demo
```

2. Create and activate a virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install required dependencies:
```bash
pip install google-generativeai python-dotenv google-adk-agents
```

## Configuration

1. Create a `.env` file in the `adk-example` directory:
```bash
cp adk-example/.env.example adk-example/.env
```

2. Add your Google API key to the `.env` file:
```
GOOGLE_API_KEY=your-actual-api-key-here
```

## Usage

```python
from adk_example.agent import root_agent

# Generate a LinkedIn post from a topic
topic = "artificial intelligence in healthcare"
result = root_agent.run(topic)

print(result["formatted"])  # The final LinkedIn post
```

## Project Structure

```
adk-demo/
├── adk-example/
│   ├── __init__.py          # Package initialization
│   ├── agent.py             # Main agent definitions and logic
│   └── .env                 # Environment variables (API keys)
├── venv/                    # Virtual environment
├── .gitignore              # Git ignore rules
└── README.md               # This file
```

## How It Works

1. **Input**: You provide a topic string
2. **Idea Generation**: The `IdeaAgent` uses Gemini to brainstorm creative LinkedIn post ideas
3. **Content Writing**: The `WriteAgent` expands the idea into a full post draft
4. **Formatting**: The `FormatAgent` formats the draft into a trending LinkedIn post style
5. **Output**: Returns a polished, ready-to-post LinkedIn content

## Tools Used

- **Google Generative AI (Gemini)**: Powers the content generation
- **Google Agent Development Kit**: Provides the multi-agent framework
- **Python-dotenv**: Manages environment variables

## Environment Variables

| Variable | Description | Required |
|----------|-------------|----------|
| `GOOGLE_API_KEY` | Your Google API key for Gemini access | Yes |

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Support

If you encounter any issues or have questions, please open an issue on the GitHub repository.

## Acknowledgments

- Google Agent Development Kit team
- Google Gemini AI for content generation capabilities
