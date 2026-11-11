# CloudLab — Python Flask Application

CloudLab is a simple Python Flask web application with a responsive HTML homepage, a form submission route, and a health-check endpoint. The application is hosted on **Microsoft Azure App Service** and its source code is maintained in **GitHub**.

## Live deployment

The application is deployed to Azure App Service. Open the **Default Domain** shown on the Azure App Service **Overview** page to access the live website.

## Technology stack

- Python 3.15 (runtime selected for the Azure Web App)
- Flask
- HTML and CSS
- Gunicorn
- GitHub
- GitHub Actions
- Microsoft Azure App Service (Linux)

## Repository structure

```text
CloudLab/
├── app.py
├── requirements.txt
├── Procfile
├── .gitignore
├── README.md
└── templates/
    └── index.html
```

## Application endpoints

| Endpoint | Method | Description |
|---|---|---|
| `/` | GET | Displays the Flask homepage. |
| `/submit` | POST | Handles the homepage form submission. |
| `/health` | GET | Returns a JSON health-check response. |

Expected response from `/health`:

```json
{
  "status": "ok"
}
```

## Run locally

1. Install Python.
2. Clone this repository:

   ```bash
   git clone https://github.com/SamRepository25/CloudLab.git
   cd CloudLab
   ```

3. (Recommended) Create and activate a virtual environment:

   **Windows**
   ```bash
   python -m venv .venv
   .venv\\Scripts\\activate
   ```

   **macOS / Linux**
   ```bash
   python3 -m venv .venv
   source .venv/bin/activate
   ```

4. Install the dependencies:

   ```bash
   pip install -r requirements.txt
   ```

5. Start the Flask development server:

   ```bash
   python app.py
   ```

6. Open http://127.0.0.1:5000 in your browser.

## Dependencies

The dependencies are listed in `requirements.txt`:

```text
Flask>=3.1,<4.0
gunicorn>=23.0,<24.0
```

## Deployment on Microsoft Azure

The application was deployed using **Azure App Service** with **GitHub Actions**.

1. Create or open an Azure App Service Web App using the Linux operating system and Python runtime.
2. In the Web App, open **Deployment Center**.
3. Select **GitHub** as the source and authorize the GitHub account when prompted.
4. Select the repository `SamRepository25/CloudLab` and the `main` branch.
5. Configure GitHub Actions as the build provider and save the deployment settings.
6. Azure configures the GitHub Actions workflow for building and deploying the application.
7. Open the repository's **Actions** tab and monitor the workflow.
8. Confirm that both the build and deployment jobs complete successfully.
9. In Azure App Service, open **Overview** and select **Browse** (or open the Default Domain) to view the deployed application.
10. Test the health endpoint by appending `/health` to the Web App URL.

## Continuous deployment

When the GitHub Actions workflow is configured to deploy from the `main` branch, new commits pushed to that branch can trigger another build and deployment. Check the **Actions** tab to confirm each workflow run succeeds.

## Deployment verification

- [x] Flask homepage opened from the Azure Web App.
- [x] GitHub Actions build completed successfully.
- [x] GitHub Actions deployment completed successfully.
- [x] The `/health` endpoint returned the expected JSON status.

## Result

The CloudLab Python Flask application was successfully committed to GitHub and deployed to Microsoft Azure App Service using GitHub Actions. The live homepage and health-check endpoint were tested successfully.
