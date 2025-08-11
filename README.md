# IS601 Python Web Calculator, v.0.15.0
![Coverage Badge](https://github.com/lcphutchinson/is601_final/actions/workflows/ci-cd.yml/badge.svg) ![Docker Automated build](https://img.shields.io/docker/automated/lcphutchinson/is601_final?logo=docker&label=Docker&color=blue)

This program concludes a series of iterative modules for the course IS601 Web Systems Development, by Keith Williams.

Making use of the scaffolding of a simple calculator, this program implements the full suite of standard web application features including a JWT-backed Auth flow for user registration and login, RESTful BREAD endpoints to user-managed records, and a Tailwind-fronted web interface. Tailwind, FastAPI, SQLAlchemy, Pydantic, and PostreSQL are its tech stack. Find the Dockerhub Repo [[Here]](https://hub.docker.com/repository/docker/lcphutchinson/is601_final)

### Requirements

- Python 3.10+
- Git 2.43.0+ with SSH configured
- Docker 28.3.2+

## Setup (Linux)

No installation is required to launch the Web Calculator, simply retrieve the code using git clone,

```bash
git clone git@github.com:lcphutchinson/is601_final.git
```

then build and deploy the image.

```bash
docker compose up --build
```

## Using the Web Calculator

After deployment, the web endpoint will be accessible at http://localhost:8000
<img width="1000" height="680" alt="Landing Page" src="https://github.com/user-attachments/assets/a72d11b1-3e4e-4cf3-8f86-04214337acd8" />

Developers can access the API specifications directly at http://localhost:8000/docs

<img width="1000" height="580" alt="API Docs" src="https://github.com/user-attachments/assets/37419920-f279-4bb1-8ac3-495523d11083" />

### Registration and Login
<img width="380" height="575" alt="Screenshot 2025-08-11 025609" src="https://github.com/user-attachments/assets/bd796445-532b-42e3-9ee4-7df0b289ebdc" />
<img width="380" height="500" alt="Screenshot 2025-08-11 025633" src="https://github.com/user-attachments/assets/1e1f9073-3f49-4d9b-83dc-315e61d3f5fd" />

### The Dashboard
<img width="1000" height="675" alt="Screenshot 2025-08-11 030033" src="https://github.com/user-attachments/assets/3ef73072-29f3-45f5-bc99-b056a474834f" />

Execute new calculations by selecting an operation type from the dropdown menu and entering your operands in the right side text box as a comma separated list. Then, click 'Submit'.

Calculation records from this and previous sessions will be displayed below the calculator interface.

### The View Menu
<img width="1000" height="685" alt="Screenshot 2025-08-11 030524" src="https://github.com/user-attachments/assets/7aec0dd3-834a-4ef5-8d78-65b7f792d4a8" />

### The Edit Menu
<img width="1000" height="685" alt="Screenshot 2025-08-11 030800" src="https://github.com/user-attachments/assets/c3687f42-38cc-4170-b14d-9297a8259a52" />

Enter new operands for your calculation in the text box and click 'save changes' to commit.

<img width="1000" height="680" alt="Screenshot 2025-08-11 031012" src="https://github.com/user-attachments/assets/457b9e1f-97dc-475e-b28b-1e52f5ce43ab" />

To permanently delete a calculation record, select the 'Delete' button from either the dashboard or the view menu.

## Running the Test Suite

Running the Web Calculator's test suite will require a little additional setup. I recommend first deploying a Virtual Environment through Python3 venv.

```bash
python3 -m venv venv
source venv/bin/activate
```

Install system dependencies from the project root

```bash
pip install -r requirements.txt
playwright install
```

Playwright may prompt you to install additional dependencies.

Redeploy the image in daemon mode
```bash
docker compose up -d
```

Run the test suite
```bash
pytest
```
