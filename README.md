# Flask Quiz App

A small full-stack web application built with Flask and SQLAlchemy: users take short
multiple-choice quizzes, scores are tracked per user, and a global high score / ranking
is maintained. Includes a minimal admin view for managing questions.

> This is a learning / portfolio project that demonstrates a clean Flask app structure
> (models, templates with inheritance, error handling and configuration via environment
> variables). It is **not** intended for production use as-is.

## Features

- **Quiz flow** – random questions per attempt, scoring, results page.
- **Per-user scores** – last score, high score and attempt count.
- **Global ranking** – tracks the global high score and a user's rank.
- **Admin view** – list and review questions (`/admin/questions`).
- **Stats endpoint** – `GET /api/stats` returns user/attempt/average-score totals.
- **Proper error pages** – custom 404 / 500 / quiz-error templates.

## Tech stack

- Python 3.11+
- Flask + Flask-SQLAlchemy (SQLite by default)
- Jinja2 templates with a shared `base.html`
- `python-dotenv` for configuration

## Project structure

```
flask-exam-app2/
├── app.py              # application, models and routes
├── dbcreate.py         # helper to (re)create the database / seed questions
├── models.py           # SQLAlchemy models
├── requirements.txt
├── static/             # CSS
└── templates/          # pages + admin/ + errors/
```

## Setup

```bash
git clone https://github.com/Ayberk-Irmak/flask-exam-app2.git
cd flask-exam-app2
python -m venv .venv && . .venv/Scripts/activate   # Windows
pip install -r requirements.txt
```

Copy the example environment file and adjust values:

```bash
cp .env.example .env
```

| Variable        | Purpose                                   | Default                 |
|-----------------|-------------------------------------------|-------------------------|
| `SECRET_KEY`    | Flask session signing key                 | insecure placeholder    |
| `DATABASE_URL`  | SQLAlchemy database URI                    | `sqlite:///quiz.db`     |
| `FLASK_DEBUG`   | Enable debug mode (`1`/`0`)               | off                     |

## Run

```bash
python app.py
```

The database and sample questions are created automatically on first run.
A default admin account is seeded (`admin` / `admin123`) — **change this before
exposing the app anywhere**.

Then open http://localhost:5000

## License

Released under the MIT License — see [LICENSE](LICENSE).

## Author

**Ayberk Irmak** — [@Ayberk-Irmak](https://github.com/Ayberk-Irmak) · ayberk.sec@proton.me
