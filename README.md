# tn-scheme-rag-assistant

Bilingual (English/Tamil) RAG assistant for Tamil Nadu government schemes, built with FAISS, multilingual-e5 and Groq LLMs.

Ask a question in English or Tamil and get a short answer in **both languages**, with the scheme name and source link.

## Schemes covered

- Kalaignar Magalir Urimai Thogai (now Madhippumigu Magalir Thittam)
- Pudhumai Penn and Tamil Pudhalvan
- Vidiyal Payanam (Vettri Payanam), free bus travel for women
- Chief Minister's Breakfast Scheme
- CMCHIS health insurance
- Naan Mudhalvan skill development

## How it works

1. Scheme documents are split into chunks (120 words, 20 overlap), each with its Tamil scheme name.
2. Chunks are embedded with `intfloat/multilingual-e5-base` and stored in a FAISS index.
3. The top 4 chunks for a question are retrieved.
4. A Groq LLM (default `llama-3.3-70b-versatile`) answers only from those chunks, in English and Tamil.

## Run it

1. Open `TN_Scheme_RAG_fixed.ipynb` in Google Colab.
2. Add your Groq API key to Colab Secrets as `GROQ_API_KEY`.
3. Run all cells from top to bottom. The last cell is an interactive Q&A loop.

Optional: upload your own PDFs to `/content` and run the PDF cell.

## Example questions

- Who is eligible for Kalaignar Magalir Urimai Thogai?
- How can I get free bus travel?
- மகளிர் உரிமைத் தொகை எவ்வளவு?

## Disclaimer

Scheme details were compiled from official portals and news reports (last checked 11 Oct 2026) and can change. Always confirm on the official portal at tn.gov.in or with the concerned department.

## License

MIT
