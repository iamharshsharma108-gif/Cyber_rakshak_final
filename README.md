# CYBER RAKSHAK FINAL

AI-assisted cyber investigation and evidence-analysis platform built with Streamlit.

## Included

- Login / registration
- Google OIDC login support
- Session-based investigation workspace
- Server-side SQLite account/case/evidence layer
- Evidence intake and analysis
- Risk assessment
- Financial/cyber/relationship network analysis
- Graph, cluster, centrality, bridge and path analysis
- Timeline and AI correlation views
- Evidence chain / ledger
- Report generation and email delivery
- Feedback and contact storage
- English, Hindi, Tamil and Bengali UI support
- Responsive light-mode styling for desktop, tablet and mobile layouts

## Project structure

```text
CYBER_RAKSHAK_FINAL/
├── cyber_rakshak_final.py
├── requirements.txt
├── README.md
├── .gitignore
└── .streamlit/
    ├── config.toml
    └── secrets.toml.example
```

## Local setup

```bash
python -m venv .venv
```

Windows:

```bash
.venv\Scripts\activate
```

Linux/macOS:

```bash
source .venv/bin/activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Run:

```bash
streamlit run cyber_rakshak_final.py
```

## Google login

Copy:

```text
.streamlit/secrets.toml.example
```

to:

```text
.streamlit/secrets.toml
```

Then fill in the Google OIDC values.

For local development, the redirect URI is normally:

```text
http://localhost:8501/oauth2callback
```

For deployment, use the deployed application's HTTPS callback URL and register the same URL in the Google OAuth client.

## Email

The application includes SMTP-based email delivery. Configure the `[smtp]` section in `secrets.toml` with your SMTP provider's settings.

Do not put SMTP passwords or Google client secrets directly into Python source code or GitHub.

## Data storage

The application creates a local `server_data/` directory at runtime and uses SQLite databases for server-side account/case/evidence and feedback/contact persistence.

`server_data/` is intentionally ignored by Git so investigation data and local databases are not accidentally committed to GitHub.

Session state is separate from persistent server-side storage.

## Important deployment note

For a real deployment, use persistent server/database storage rather than relying only on a temporary filesystem. Some cloud hosting environments can recreate the application container, which can remove local files.

This project is an academic/prototype investigation-support platform. Analytical signals should be reviewed by authorized human investigators; correlations or risk scores should not be treated as proof that a person committed a crime.

## License

Add the license required by your team, institution, or competition before public release.
