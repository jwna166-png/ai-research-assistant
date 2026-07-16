# AI Research Assistant Agent

An autonomous research assistant agent built with **LangChain + Claude (Anthropic)**. Given a research question, the agent decides on its own whether to search the web or query Wikipedia, compiles the findings into a structured research report, and can automatically save the results to a local file.

## ✨ Features

- 🔍 **Autonomous tool calling** — Built on LangChain's Tool-Calling Agent; the model decides on its own when to invoke the search or Wikipedia tool
- 📚 **Multi-source retrieval** — Integrates DuckDuckGo web search and Wikipedia lookup
- 📋 **Structured output** — Uses Pydantic to define and validate the output schema (topic / summary / sources / tools used)
- 💾 **Automatic persistence** — Research results can be automatically appended to a local text file

## 🛠 Tech Stack

- [LangChain](https://www.langchain.com/) — Agent framework
- [Claude (Anthropic API)](https://www.anthropic.com/) — LLM reasoning engine
- [Pydantic](https://docs.pydantic.dev/) — Data schema definition and output validation
- [DuckDuckGo Search](https://pypi.org/project/duckduckgo-search/) — Web search tool
- Wikipedia API — Encyclopedia lookup tool

## 📁 Project Structure

```
.
├── main.py            # Main program: builds the prompt, creates the agent, runs the query
├── tool.py             # Custom tools: web search, Wikipedia lookup, file saving
├── requirement.txt    # Project dependencies
└── .env                # Environment variables (create this yourself; not committed to git)
```

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
```

### 2. Create a virtual environment (recommended)

```bash
python -m venv venv
source venv/bin/activate   # Windows: venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirement.txt
```

### 4. Configure environment variables

Create a `.env` file in the project root with your Anthropic API key:

```
ANTHROPIC_API_KEY=your_key_here
```

> You can get an API key from the [Anthropic Console](https://console.anthropic.com/).

### 5. Run

```bash
python main.py
```

You'll be prompted:

```
What can I help you research?
```

Enter your research topic, and the agent will automatically retrieve information and return a structured result, e.g.:

```
topic='...' summary='...' sources=[...] tools_used=[...]
```

## ⚠️ Notes

- Never commit your `.env` file to GitHub (already excluded via `.gitignore`)
- Update the model name in `main.py` to match whatever model is currently supported per the [Anthropic docs](https://docs.claude.com)

## 📄 License

MIT
