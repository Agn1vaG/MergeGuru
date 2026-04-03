# MergeGuru – AI-Powered Code Review & Analysis Platform

AI-powered code analysis platform that reviews pull requests, detects issues, and provides structured improvements across code quality, bugs, and performance.

---

## Overview

MergeGuru is an AI-driven code review system designed to analyze code changes from GitHub pull requests. It identifies bugs, suggests fixes, improves code structure, evaluates documentation, and provides optimization insights.

The platform is built to automate and enhance the code review process, making it faster and more consistent.

---

## Features

### Code Review Automation

* Analyzes GitHub Pull Requests
* Detects bugs and potential issues
* Suggests fixes with code snippets

### Code Quality Improvements

* Refactoring suggestions
* Documentation evaluation
* Code readability enhancements

### Performance Optimization

* Identifies inefficient logic
* Suggests optimized alternatives

### Multi-File Analysis

* File-wise structured results
* Section-based insights (bugs, fixes, optimization, etc.)
* Interactive navigation (carousel-based UI)

### Interactive Dashboard

* Tab-based UI for different analysis types
* Expandable result cards
* Modal-based deep insights

---

## Tech Stack

* Backend: Python, Flask
* Frontend: HTML, CSS, JavaScript
* AI Integration: LLM-based analysis
* Environment: python-dotenv

---

## Project Structure

```id="h2ks9p"
project/
│
├── start.py
├── app/
│   ├── controller/
│   │   ├── home_controller.py
│   │   ├── submit_controller.py
│   │   ├── polling_controller.py
│   │   ├── reload_controller.py
│   │   └── coder_controller.py
│
├── templates/
│   └── index.html
│
├── static/
│
└── .env
```

---

## Requirements

* Python 3.8+
* pip

---

## Installation

```id="3c5fvp"
git clone <your-repo-link>
cd <project-folder>
pip install -r requirements.txt
```

---

## Environment Variables

Create a `.env` file:

```id="u2izj3"
OPENAI_API_KEY=your_key_here
```

---

## Run the Application

```id="8jph0h"
python start.py
```

Access at:

```id="5ryhdt"
http://127.0.0.1:8000
```

---

## API Endpoints

| Endpoint             | Method | Description               |
| -------------------- | ------ | ------------------------- |
| `/`                  | GET    | Load dashboard            |
| `/flask-api/submit`  | POST   | Submit PR for analysis    |
| `/flask-api/polling` | POST   | Fetch analysis results    |
| `/flask-api/reload`  | POST   | Reload previous analysis  |
| `/flask-api/code`    | POST   | Generate code suggestions |
| `/flask-api/health`  | GET    | Health check              |

---

## How It Works

1. User submits a GitHub Pull Request link
2. System extracts changed files
3. AI analyzes code across multiple dimensions
4. Results are structured into sections
5. UI displays insights interactively
6. Polling updates results until completion

---

## Limitations

* Currently optimized for PR-based workflows only
* Uses polling instead of real-time streaming
* No persistent storage for past analyses

---

## Future Improvements

* Support for full repository analysis
* Real-time updates using WebSockets
* Integration with GitHub Actions
* User authentication and history tracking

---

## License

This project is for educational and demonstration purposes.
