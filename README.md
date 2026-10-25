# MiniCraft Help
**Author: Novita Astari Sabrina**
Educational project for the Google-supported Hacktiv8 chatbot course.
A simple Indonesian shop FAQ chatbot built with Streamlit and Google Gemini.

## What it does
Answers shipping, payment, cancellation and return questions using a synthetic store guide; maintains recent chat context within a session; exposes the source guide; handles missing keys and common API failures.

## How it works, in plain language
The customer types a question. Python reads the store guide and combines it with instructions and recent conversation turns. Gemini generates an answer. Streamlit displays it.
This is full-context prompting, not model training or vector-database RAG. Temperature is 0.2 to encourage consistent answers. Outputs can still be wrong and need checking.

## Files
- app.py: chat interface and Gemini connection
- store_guide.md: complete synthetic knowledge source
- requirements.txt: Python libraries to install
- manual_checks.json: questions and expected behaviour for manual checking
- SUBMISSION_TEXT.txt: draft form answers
- START_HERE.txt: beginner deployment instructions

## Run locally (optional)
Requires Python 3.10 or newer. Open a terminal in this folder:

    python -m pip install -r requirements.txt
    python -m streamlit run app.py

Enter your own Gemini API key in the sidebar. Alternatively provide GEMINI_API_KEY through environment variables or Streamlit secrets. The default model is gemini-flash-latest; change it in the sidebar if unavailable for your account.

## Deploy without installing Python
See START_HERE.txt: upload files to GitHub and deploy through Streamlit Community Cloud. Never upload a real key. API access depends on account permissions and quotas. Deployment and live model replies require your accounts and credentials.

## Data and privacy
All shop policies are AI-assisted synthetic content authored for this educational demo. This is not Sakatsu policy or a real shop. No customer records are included. Messages are sent to Google's API. Do not enter personal or payment data. Conversation history is stored in the active Streamlit session, not intentionally written to disk. The bot cannot access or modify orders.

## Validation
Local verification covers application rendering and mocked API success/failure handling. manual_checks.json contains proposed evaluation cases, not claimed live Gemini results. A genuine Gemini response must be tested with a valid user key before submission. No accuracy percentages or live API test results are claimed.

## References
https://googleapis.github.io/python-genai/
https://docs.streamlit.io/deploy/streamlit-community-cloud
