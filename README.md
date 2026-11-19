# LangChain + Groq Fundamentals

Hands-on notes and runnable examples for learning LangChain with Groq-hosted models (`openai/gpt-oss-20b` and `openai/gpt-oss-120b`).

## What's covered

| Topic | Where |
|---|---|
| Calling an LLM, token usage, `finish_reason` | `examples/01_basics.py` |
| Model size, temperature, `max_tokens`, `timeout`, `max_retries` | `examples/01_basics.py` |
| System / Human / AI messages and conversation memory | `examples/01_basics.py` |
| Prompt templates (`ChatPromptTemplate`) | `examples/02_prompts_and_chains.py` |
| Chains with `\|`, `StrOutputParser`, `.batch()`, `.stream()`, `RunnableLambda` | `examples/02_prompts_and_chains.py` |
| Structured output with Pydantic (`with_structured_output`) | `examples/03_structured_output.py` |
| Full original Colab notebook, exported as a script | `colab/Langchain_DS_Feb.py` |

## Project structure

```
langchain-groq-fundamentals/
├── README.md
├── requirements.txt
├── .env.example
├── .gitignore
├── colab/
│   └── Langchain_DS_Feb.py      # original Colab export (uses google.colab secrets)
└── examples/
    ├── 01_basics.py
    ├── 02_prompts_and_chains.py
    └── 03_structured_output.py
```

## Setup

```bash
python -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate
pip install -r requirements.txt

cp .env.example .env             # then put your real Groq key in .env
```

Get a free API key from the [Groq console](https://console.groq.com/keys).

## Run the examples

```bash
python examples/01_basics.py
python examples/02_prompts_and_chains.py
python examples/03_structured_output.py
```

## Notes on the Colab script

`colab/Langchain_DS_Feb.py` is the untouched export of the notebook. It uses `google.colab.userdata` and `!pip` commands, so it only runs inside Google Colab (add a secret named `groq_api`). The cells at the end are practice exercises (invoice extractor, event registration schema, two-step Hindi review pipeline) left open on purpose. The `examples/` scripts are the same ideas rewritten to run locally.

## Security

Never commit your API key. `.env` is listed in `.gitignore`; only `.env.example` (with a placeholder) is tracked.
