# CloudLab — Flask Application

A small Flask starter application with an HTML homepage and a working form.

## Project structure

```
CloudLab/
├── app.py
├── requirements.txt
├── Procfile
├── .gitignore
├── README.md
└── templates/
    └── index.html
```

## Run locally

1. Create and activate a virtual environment.
2. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

3. Start the development server:

   ```bash
   python app.py
   ```

4. Open http://127.0.0.1:5000 in your browser.

## Deploy on Render

- Runtime: Python
- Build command: `pip install -r requirements.txt`
- Start command: `gunicorn app:app`

The `/health` endpoint returns a simple JSON status response.
