# mind_pet

Smart chatbot companion for saving and organizing your thoughts, ideas, and journal entries.

## Description

mind_pet is a personal AI assistant that helps you:
- 💭 Save ideas and thoughts in a convenient format
- 📝 Keep a digital journal
- 🔍 Quickly find needed information by request
- 🔗 Establish connections between different entries
- 📊 Analyze your entries and discover patterns

## Features

- **Intelligent Storage**: Automatic categorization and tagging of entries
- **Smart Search**: Finds not only exact matches but also related information
- **Contextual Connections**: Shows relationships between different thoughts and ideas
- **Personalization**: Adapts to your thinking style and preferences
- **Security**: All data is stored locally and protected

## Technologies

### Core Stack
- **Python 3.13+** - Modern Python with latest features
- **UV** - Fast package manager and virtual environment management
- **Rich** - Beautiful CLI interface with enhanced terminal output
- **Pydantic** - Data validation and serialization

### Storage & Search
- **PostgreSQL** - Primary database with JSONB support
- **pgvector** - Vector extension for semantic search capabilities
- **Storage Abstraction** - Interface layer supporting multiple backends
- **InMemory Storage** - Development and testing backend

### AI & LLM Integration
- **LangChain** - LLM application framework and document processing
- **LangGraph** - Multi-agent coordination and workflow management
- **Anthropic Claude** - Primary AI model integration
- **LangSmith** - Observability and debugging for AI workflows

### Development Tools
- **Ruff** - Lightning-fast linting and formatting
- **MyPy** - Static type checking
- **pytest** - Testing framework

### Architecture Phases
1. **Phase 1 (MVP)**: InMemory storage + Rich CLI
2. **Phase 2 (Production)**: PostgreSQL + full-text search
3. **Phase 3 (Advanced)**: Semantic search with pgvector

## Installation

### Prerequisites

- Python 3.13 or higher
- UV package manager
- PostgreSQL (for Phase 2+, optional for Phase 1 MVP)

### Installation Steps

1. Clone the repository:
```bash
git clone https://github.com/VyacheslavKazakov/mind_pet.git
cd mind_pet
```

2. Install UV (if not installed):
```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

3. Create virtual environment and install dependencies:
```bash
uv sync
```

4. Activate virtual environment:
```bash
source .venv/bin/activate  # Linux/macOS
# or
.venv\Scripts\activate     # Windows
```

### Configuration

Create a `.env` file for development:
```bash
# Development settings
MIND_PET_ENV=development
LOG_LEVEL=DEBUG
ENABLE_RICH_LOGGING=true

# Database (Phase 2+)
# DATABASE_URL=postgresql://user:pass@localhost/mind_pet

# AI Integration
 ANTHROPIC_API_KEY=your_api_key
 LANGSMITH_API_KEY=your_key
 LANGSMITH_PROJECT=mind_pet
```

## Usage

### Running the Application

```bash
uv run python -m mind_pet
```

This starts an interactive chat interface where you can naturally communicate with your AI assistant.

### Natural Language Interface

mind_pet understands natural language commands. You can interact conversationally:

- **Save ideas**: "I have an idea for a mobile app that helps people learn languages"
- **Save journal entries**: "Today I realized that..."
- **Search**: "Find my notes about AI" or "Show me ideas from last week"
- **Explore**: "What are my thoughts related to productivity?"
- **Analyze**: "Show me my writing patterns" or "What topics do I think about most?"

### Usage Examples

```
🧠 mind_pet > I want to save an idea about using AI for language learning

✅ Great! I've saved your idea: "Using AI for language learning"
   📝 Type: idea
   🏷️  Auto-tags: ai, language, learning, education
   📅 Created: 2024-09-22 14:30:15

🧠 mind_pet > Find all my ideas about AI

🔍 Found 3 entries about AI:

1. 💡 Using AI for language learning (just now)
   "AI could personalize learning paths based on individual progress..."

2. 💡 AI-powered task management (yesterday)
   "An assistant that learns your priorities and suggests optimal scheduling..."

3. 📝 Thoughts on AI ethics (2 days ago)
   "We need to consider the implications of AI in daily life..."

🧠 mind_pet > What topics do I think about most?

📊 Your top interests:
   🏷️  ai (5 entries)
   🏷️  productivity (3 entries)
   🏷️  learning (3 entries)
   🏷️  technology (2 entries)

🧠 mind_pet > Show me connections to my language learning idea

🔗 Related thoughts:
   • "Mobile app development challenges" (shared: mobile, app)
   • "Personalized learning systems" (shared: learning, personalization)
   • "AI in education trends" (shared: ai, education)
```


## Development

### Setting up Development Environment

```bash
# Install development dependencies
uv sync --dev

# Run linter
uv run ruff check .

# Format code
uv run ruff format .

# Type checking
uv run mypy .

# Run tests
uv run pytest
```

## License

MIT License - see [LICENSE](LICENSE) file for details
