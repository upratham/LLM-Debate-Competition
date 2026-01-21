# Debate-competition

A lightweight **multi-agent debate simulator** built in Python. It runs a “debate competition” between two LLM competitors (two personas arguing opposite stances) and optionally uses a third “supervisor/judge” agent to evaluate and score the round.

> Primary interface: **Jupyter Notebook** (`Debate_Competittion.ipynb`)

---

## What it does

- **Two competitors** debate a topic (each with their own system prompt/persona).
- Responses are formatted in **clean Markdown** (headings, subheadings, concise arguments).
- A **supervisor/judge** can review the debate and output structured feedback (e.g., JSON scoring).

---

## Tech stack

- Python **3.11** :contentReference[oaicite:2]{index=2}  
- Key deps: `openai`, `requests`, `dotenv`, `ipython`, `ipykernel` :contentReference[oaicite:3]{index=3} :contentReference[oaicite:4]{index=4}  
- Designed to work with:
  - **Local LLMs via Ollama** (OpenAI-compatible API base URL)
  - Or **OpenAI API** (swap base URL + real API key)

---

## Project structure

```text
.
├── Debate_Competittion.ipynb   # Main demo / runner notebook
├── pyproject.toml              # Project metadata + dependency wiring
├── requirements.txt            # Runtime dependencies
└── README.md
````

---

## Prerequisites

* Python **3.11.x** 
* (Recommended) A virtual environment tool (`venv`, `conda`, etc.)
* If using **Ollama**:

  * Ollama installed and running
  * Models pulled (example from notebook: `llama3.2` / `llama3.1`)

---

## Setup

### 1) Clone the repo

```bash
git clone https://github.com/upratham/LLM-Debate-Competition.git
cd LLM-Debate-Competition
```

### 2) Create & activate a virtual environment

```bash
python -m venv .venv
# Windows:
# .venv\Scripts\activate
# macOS/Linux:
source .venv/bin/activate
```

### 3) Install dependencies

Option A (simple):

```bash
pip install -r requirements.txt
```

Option B (editable install):

```bash
pip install -e .
```

---

## Configuration

### Using Ollama (local)

The notebook is set up to use an OpenAI-compatible base URL like:

* `http://localhost:11434/v1`

Make sure Ollama is running and the model is available, for example:

```bash
ollama pull llama3.2
ollama pull llama3.1
```

> If your environment requires an API key field, you can set a dummy value for Ollama.

### Using OpenAI

1. Create a `.env` file (or export env vars) and set:

```bash
OPENAI_API_KEY="your_api_key_here"
```

2. Update the notebook to use the default OpenAI base URL (or remove the custom `base_url`).

---

## How to run

### Run via Jupyter Notebook (recommended)

```bash
jupyter notebook
```

Open `Debate_Competittion.ipynb` and run cells from top to bottom.

---

## Customization

You can tweak the debate by editing:

* The **topic** (e.g., “Science is a blessing vs science is a curse”)
* The two **competitor system prompts** (tone, style, constraints)
* The **supervisor/judge prompt** (scoring rubric, JSON schema, feedback detail)

---

## Roadmap ideas

* [ ] Turn notebook into a CLI app (`python -m debate_competition ...`)
* [ ] Add deterministic scoring schema + validation
* [ ] Store transcripts and scores under `/runs/`
* [ ] Add unit tests for formatting + evaluation parsing
* [ ] Support more competitors / tournament brackets

---

## Contributing

PRs welcome. If you’re making changes:

1. Keep prompts readable and safe for general audiences.
2. Prefer small, focused commits.
3. Add a short note to the README if behavior changes.

---

## License

Add a license file (MIT/Apache-2.0 recommended) before publishing publicly.

---

## Author

Maintained by **Prathamesh Uravane**  
Email: [upratham2002@gmail.com](mailto:upratham2002@gmail.com)

