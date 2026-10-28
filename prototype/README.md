# Prototype — AI Proposal Triage

A working demonstration of the extraction → mandatory check → scoring → ranking pipeline.

## How to run

**1. Install dependencies:**

```bash
pip install google-genai python-dotenv
```

- `google-genai` — the Python SDK for calling the Gemini API (the new official package)
- `python-dotenv` — loads your API key from `.env.local`

**2. Add your API key:**

Open `prototype/.env.local` and replace the placeholder with your key:

```
API_KEY=your-gemini-api-key-here
```

Get a free key from https://aistudio.google.com/apikey

**3. Run the script:**

```bash
cd prototype
python triage.py
```

The script will process all 5 proposals through the pipeline and save results to `output_ranking.json`.

## What it does

1. Sanitizes each proposal text (flags prompt-injection attempts)
2. Sends each proposal to Gemini for structured data extraction (with source quotes)
3. Runs rule-based mandatory pass/fail checks on extracted data
4. Sends eligible proposals to Gemini for qualitative scoring against rubrics
5. Computes weighted totals (rule-based math) and sorts by score
6. Outputs `output_ranking.json` with ranked, flagged, and ineligible proposals
