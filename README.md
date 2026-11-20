<div align="center">

# 🤖 AI Task Manager

### Intelligent task management with AI-powered prioritization and smart scheduling

![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)
![FastAPI](https://img.shields.io/badge/FastAPI-0.100+-green.svg)
![OpenAI](https://img.shields.io/badge/OpenAI-GPT--4-purple.svg)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-15-blue.svg)
![Docker](https://img.shields.io/badge/Docker-Ready-blue.svg)
![License](https://img.shields.io/badge/license-MIT-blue.svg)

[Features](#-features) • [Tech Stack](#-tech-stack) • [Installation](#-installation) • [API Docs](#-api-documentation) • [Screenshots](#-screenshots)

</div>

---

## ✨ Features

- 🧠 **AI-Powered Prioritization** - Automatically prioritizes tasks based on urgency, importance, and deadlines
- 📝 **Natural Language Input** - Add tasks using natural language ("Meeting with John tomorrow at 3pm")
- 📅 **Smart Scheduling** - AI optimizes your schedule for maximum productivity
- 🔔 **Intelligent Reminders** - Context-aware notifications
- 📊 **Productivity Analytics** - Track and improve your efficiency
- 🏷️ **Auto-Tagging** - AI categorizes tasks automatically
- 👥 **Team Collaboration** - Share and delegate tasks
- 🔒 **Privacy-First** - Your data stays secure

---

## 🛠️ Tech Stack

### Backend
- **Framework:** FastAPI (Python 3.9+)
- **AI/ML:** OpenAI GPT-4, LangChain
- **Database:** PostgreSQL with SQLAlchemy
- **Authentication:** JWT + OAuth2
- **Task Queue:** Celery + Redis
- **API Documentation:** Swagger/OpenAPI

### DevOps
- **Containerization:** Docker + Docker Compose
- **CI/CD:** GitHub Actions
- **Testing:** pytest, pytest-asyncio
- **Code Quality:** Black, isort, mypy, flake8

---

## 🚀 Installation

### Prerequisites
- Python 3.9+
- PostgreSQL 15+
- Redis 7+
- Docker (optional)

### Using Docker (Recommended)

```bash
# Clone the repository
git clone https://github.com/bag864471-ux/ai-task-manager.git
cd ai-task-manager

# Copy environment variables
cp .env.example .env
# Edit .env with your API keys

# Start with Docker Compose
docker-compose up -d

# Access the API
open http://localhost:8000/docs
```

### Manual Installation

```bash
# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Setup database
alembic upgrade head

# Run the application
uvicorn app.main:app --reload
```

---

## 📚 API Documentation

### Authentication

```bash
# Register
POST /api/v1/auth/register
{
  "email": "user@example.com",
  "password": "securepassword",
  "full_name": "John Doe"
}

# Login
POST /api/v1/auth/login
{
  "email": "user@example.com",
  "password": "securepassword"
}
```

### Tasks

```bash
# Create task (with AI processing)
POST /api/v1/tasks
{
  "title": "Prepare presentation for Monday meeting",
  "description": "Need to create slides about Q4 results",
  "due_date": "2024-12-25T09:00:00Z",
  "priority": "high"
}

# Get AI-prioritized tasks
GET /api/v1/tasks/prioritized

# Natural language task creation
POST /api/v1/tasks/natural
{
  "input": "Schedule dentist appointment next Friday at 2pm"
}
```

---

## 🧪 Testing

```bash
# Run all tests
pytest

# Run with coverage
pytest --cov=app --cov-report=html

# Run specific test file
pytest tests/test_tasks.py -v
```

---

## 📊 Project Structure

```
ai-task-manager/
├── app/
│   ├── __init__.py
│   ├── main.py                 # FastAPI application
│   ├── config.py              # Configuration
│   ├── database.py            # Database setup
│   ├── models/                # SQLAlchemy models
│   │   ├── user.py
│   │   ├── task.py
│   │   └── tag.py
│   ├── schemas/               # Pydantic schemas
│   │   ├── user.py
│   │   └── task.py
│   ├── api/                   # API routes
│   │   ├── v1/
│   │   │   ├── auth.py
│   │   │   ├── tasks.py
│   │   │   └── analytics.py
│   ├── services/              # Business logic
│   │   ├── ai_service.py      # OpenAI integration
│   │   ├── task_service.py
│   │   └── notification_service.py
│   ├── core/                  # Core functionality
│   │   ├── security.py        # JWT handling
│   │   └── dependencies.py
│   └── utils/
│       ├── helpers.py
│       └── validators.py
├── tests/
│   ├── conftest.py
│   ├── test_auth.py
│   ├── test_tasks.py
│   └── test_ai_service.py
├── alembic/                   # Database migrations
├── .github/
│   └── workflows/
│       └── ci.yml
├── docker-compose.yml
├── Dockerfile
├── requirements.txt
├── .env.example
└── README.md
```

---

## 🔧 Configuration

Create a `.env` file:

```env
# Database
DATABASE_URL=postgresql://user:password@localhost:5432/aitasks

# Redis
REDIS_URL=redis://localhost:6379/0

# OpenAI
OPENAI_API_KEY=your-openai-api-key

# JWT
SECRET_KEY=your-secret-key-here
ALGORITHM=HS256
ACCESS_TOKEN_EXPIRE_MINUTES=30

# Application
DEBUG=True
API_V1_PREFIX=/api/v1
```

---

## 🤝 Contributing

Contributions are welcome! Please read [CONTRIBUTING.md](./CONTRIBUTING.md) for details.

---

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details.

---

<div align="center">

**Built with ❤️ by [bag864471-ux](https://github.com/bag864471-ux)**

⭐ Star this repo if you find it helpful!

</div>
