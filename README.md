# AI Powered Mock Test Platform for JEE and NEET

## Project Overview

This project aims to build an end-to-end **AI-Powered Assessment Platform** that simulates real **Computer-Based Test (CBT)** environments for **JEE and NEET** exams. The platform is designed with a focus on adaptability, scalability, and AI-driven personalization. It supports:

- **Dynamic and adaptive test generation**
- **Flexible test selection modules for chapter-wise, subject-wise, and full-syllabus exams**
- **Real-time analytics dashboard for subject-wise accuracy insights and performance tracking**
- **Detailed test review with answer explanations**
- **Retrieval-Augmented Generation (RAG) system for personalized remedial practice**
  

## High-Level Workflow

1. User logs in or signs up
2. Selects stream → subject → test type
3. Starts the test in a CBT-style interface
4. Completes the test and submits answers
5. Backend evaluates the test and stores results
6. Analytics dashboard displays performance insights
7. Weak areas are identified → RAG engine generates remedial questions
8. Next test includes personalized remedial items based on performance


### 1. Clone the repository
git clone https://github.com/your-repo/oelp-backend.git
cd oelp-backend

# 2. Create virtual environment
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Set up Environment Variables (.env)
# DATABASE_URL=postgresql+asyncpg://...
# GOOGLE_API_KEY=...
# SECRET_KEY=...

# 5. Run Database Migrations
alembic upgrade head

# 6. Seed Database
# Load Syllabus (Subjects/Chapters)
python -m app.scripts.load_syllabus
# Load Questions 
python -m app.scripts.load_questions

# 7. Start Server
uvicorn app.main:app --reload

cd oelp-frontend

# 1. Install dependencies
flutter pub get

# 2. Run the application
# Replace with your local or hosted backend URL
flutter run -d chrome --dart-define=API_BASE_URL=http://127.0.0.1:8000


