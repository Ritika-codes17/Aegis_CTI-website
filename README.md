# 🛡️ Aegis CTI - Cyber Threat Intelligence Portal

**Aegis CTI** is an AI-powered Cyber Threat Intelligence (CTI) triage platform and Defense Sensor Asset Registry. It is engineered for real-time tactical prioritization, automated Natural Language Processing (NLP) indicator extraction, and interactive threat analytics to streamline incident response workflows.

## ⚡ Core Features

*   **Automated Priority Scoring (0–100):** A multi-factor, explainable risk formula combining severity, asset criticality, threat category, and recency decay into specific SLA tiers (**P1 Immediate** to **P4 Routine**).
*   **NLP & IoC Extraction:** Automated parsing of Indicators of Compromise (CVEs, IPv4, hashes, domain names) from raw threat bulletins using advanced text processing.
*   **Interactive Analytics Dashboard:** Sleek dark-mode visualizations featuring dynamic time-series scrubbers to track threat evolution over specific durations.
*   **Sensor Asset Registry:** Live registration and real-time alert feed for satellite, radar, UAV, and ground intelligence sensors.
*   **Offline Execution Environment:** Designed to run entirely offline with a localized database, ensuring zero external API dependencies for secure, air-gapped deployment.

## 🛠️ Technology Stack

*   **Frontend Interface:** Streamlit, HTML/CSS, Chart.js, Plotly
*   **Backend Architecture:** Python, Flask REST API
*   **Machine Learning & NLP:** Scikit-Learn, NLTK, spaCy, Pandas, NumPy
*   **Data Storage:** Persistent SQLite (`cti_database.db`)

## 🚀 Quick Start Guide

**1. Install Dependencies**
Ensure your Python environment is set up, then install the required packages:
`pip install -r requirements.txt`

**2. Launch the Application**
Since this project uses a split architecture, you need to start the backend and frontend separately. Open two different terminal windows:

*   **Terminal 1 (Backend):** Run the Flask server:
    `python server.py`
*   **Terminal 2 (Frontend):** Navigate to the Streamlit folder and run the dashboard:
    `cd streamlit`
    `streamlit run app.py`

Access the main portal at **`http://localhost:5001`** and the dashboard at **`http://localhost:8501`**.

---

## 📁 Repository Structure

```text
├── index.html              # Main Aegis CTI Portal UI
├── server.py               # Flask REST API Server
├── requirements.txt        # Project dependencies
├── cti_database.db         # Persistent SQLite database
└── streamlit/
    ├── app.py              # Aegis CTI Analytics Dashboard
    ├── db_manager.py       # SQLite CRUD Operations & Schema
    ├── nlp_processing.py   # Keyword & IoC Extraction Pipeline
    └── pipeline.py         # Priority Scoring & Risk Engine
