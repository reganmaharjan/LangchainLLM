# Agentic Profile Analysis

A LinkedIn profile analysis tool that helps you gather information about people and create engaging conversation starters.

## 🚀 Features

- **LinkedIn Profile Lookup**: Find LinkedIn profiles using names
- **Profile Scraping**: Extract detailed information from LinkedIn profiles
- **AI-Powered Summaries**: Generate concise summaries and interesting facts about people
- **Conversation Starters**: Create engaging ice breakers based on profile data

## 📁 Project Structure

```
ice_breaker/
├── agents/
│   └── linkedin_lookup_agent.py    # LinkedIn profile lookup using AI agents
├── tools/
│   └── tools.py                     # Tavily search tools for profile discovery
├── third_parties/
│   └── linkedin.py                  # LinkedIn profile scraping functionality
├── ice_breaker.py                   # Main application entry point
├── Pipfile                          # Python dependencies
└── README.md                        # This file
```

## 🛠️ Setup

### Prerequisites

- Python 3.10+
- pipenv (for dependency management)

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd ice_breaker
   ```

2. **Install dependencies**
   ```bash
   pipenv install
   ```

3. **Set up environment variables**
   
   Create a `.env` file in the project root with the following variables:
   ```
   OPENAI_API_KEY=your_openai_api_key_here
   TAVILY_API_KEY=your_tavily_api_key_here
   SCRAPIN_API_KEY=your_scrapin_api_key_here  # Optional, for profile scraping
   ```

### API Keys Required

- **OpenAI API Key**: For AI-powered summaries and agent functionality
- **Tavily API Key**: For web search functionality to find LinkedIn profiles
- **Scrapin API Key** (Optional): For enhanced LinkedIn profile scraping

## 🎯 Usage

### Basic Usage

Run the main application:
```bash
python ice_breaker.py
```

### LinkedIn Profile Lookup

Find someone's LinkedIn profile:
```python
from agents.linkedin_lookup_agent import lookup

# Find a LinkedIn profile by name
linkedin_url = lookup("John Doe")
print(linkedin_url)
```

### Profile Scraping

Extract information from a LinkedIn profile:
```python
from third_parties.linkedin import scrape_linkedin_profile

# Scrape profile data
profile_data = scrape_linkedin_profile("https://www.linkedin.com/in/username/")
print(profile_data)
```

### Generate AI Summaries

Create summaries and conversation starters:
```python
from ice_breaker import generate_summary

# Generate summary from profile data
summary = generate_summary(profile_data)
print(summary)
```

## 🔧 Configuration

### Environment Variables

| Variable | Description | Required |
|----------|-------------|----------|
| `OPENAI_API_KEY` | OpenAI API key for AI functionality | Yes |
| `TAVILY_API_KEY` | Tavily API key for web search | Yes |
| `SCRAPIN_API_KEY` | Scrapin API key for profile scraping | No |

### Model Configuration

The application uses:
- **GPT-4o-mini** for LinkedIn lookup agent
- **GPT-3.5-turbo** for summary generation
- **Tavily Search** for web search functionality

## 🚨 Troubleshooting

### Common Issues

1. **Import errors**: Make sure all dependencies are installed with `pipenv install`
2. **API key errors**: Verify all required API keys are set in your `.env` file
3. **LinkedIn profile not found**: Try using more specific search terms or full names

### Dependencies

Key dependencies include:
- `langchain` - AI framework
- `langchain-openai` - OpenAI integration
- `langchain-tavily` - Web search functionality
- `python-dotenv` - Environment variable management

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## ⚠️ Disclaimer

This tool is for educational and networking purposes only. Please respect LinkedIn's terms of service and use the tool responsibly. Always obtain consent before scraping personal information.
