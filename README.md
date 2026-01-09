# AI Wikipedia Quiz Generator

**Developed by: Greeshmanth Reddy Bommireddy**

A full-stack application that generates interactive quizzes from any Wikipedia article using **Google’s Gemini AI**.  
This project strictly follows the assignment requirement of **React JS for frontend** and **Python (FastAPI) for backend**.

---

## 🚀 Features

- 🧠 **AI-Powered Quiz Generation**  
  Automatically generates questions, answers, and explanations from Wikipedia articles using Gemini AI.

- 🎮 **Interactive Quiz Experience**  
  Answer questions one by one with instant feedback.

- 📊 **Score Evaluation**  
  Displays final score and detailed answer review.

- 📜 **Quiz History**  
  Saves previously generated quizzes for later access.

- 🌓 **Responsive UI**  
  Clean, modern dark-mode interface built with Tailwind CSS.

---

## 🛠 Tech Stack

### Backend (Python)
- FastAPI
- SQLAlchemy
- SQLite
- Google Generative AI (Gemini)

### Frontend (React)
- React JS (Vite)
- Tailwind CSS
- Axios
- Lucide Icons

---

## 📌 Assignment Compliance

This project strictly follows the assignment requirements:

- **Frontend**: React JS  
- **Backend**: Python (FastAPI)

⚠️ **Node.js is used only for frontend tooling** (npm, Vite) required to run the React application.  
No Node.js, Express.js, or JavaScript-based backend is used in this project.

All APIs and backend logic are implemented exclusively using Python (FastAPI).

---

## 📋 Prerequisites

- Python v3.9+
- Google Gemini API Key

---

## ⚙️ Setup & Installation

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/yourusername/ai-wikipedia-quiz-generator.git
cd ai-wikipedia-quiz


### 2. Backend Setup
```bash
cd ai-wikipedia-quiz-generator
python -m venv venv
# Windows
.\venv\Scripts\activate
# Mac/Linux
source venv/bin/activate

pip install -r backend/requirements.txt
```

**Environment Variables:**
Create a `.env` file in `ai-wikipedia-quiz-generator/backend/.env`:
```env
GEMINI_API_KEY=your_api_key_here
DATABASE_URL=sqlite:///./ai-wikipedia-quiz-generator.db
```

### 3. Frontend Setup
```bash
cd frontend
npm install
```

## Running the Application

You need to run two terminals concurrently.

**Terminal 1 (Backend):**
```bash
# From root directory
.\venv\Scripts\activate
python -m uvicorn backend.main:app --reload --port 8000
```

**Terminal 2 (Frontend):**
```bash
# From frontend directory
cd frontend
npm run dev
```

Open [http://localhost:5173](http://localhost:5173) to view the app.

## Resetting primary key IDs (if they start unexpectedly high)

If you find that newly generated quiz IDs start from a number greater than 1 (for example, 6), it's usually because the database has previous inserts/deletes which advanced the auto-increment counter. To reset the counters to start from 1 you can use the included management script:

```bash
# From repo root
python backend/reset_ids.py
```

By default the script is conservative: it will only reset tables that are empty. Use `--force` to reset sequences even when tables contain rows (only do this if you know what you're doing — it can cause primary key collisions if you reuse IDs):

```bash
python backend/reset_ids.py --force
```

The script supports SQLite, MySQL and PostgreSQL. It will detect your `DATABASE_URL` automatically from `backend/.env` (or your environment).

## Wikipedia Quiz AI Generator Images
<img width="1200" height="600" alt="image" src="https://github.com/user-attachments/assets/7f2b305e-acc6-4f82-8a2a-c62a6e9b5e53" />
<img width="1200" height="600" alt="image" src="https://github.com/user-attachments/assets/6179c534-0a57-45a3-9138-34f88e51f5d7" />
<img width="1200" height="600" alt="image" src="https://github.com/user-attachments/assets/9657f67e-1752-40ac-9fed-30f4689c3fe2" />
<img width="1200" height="600" alt="image" src="https://github.com/user-attachments/assets/8d28231d-1d87-4362-8540-917021f2a3f3" />
<img width="1200" height="600" alt="image" src="https://github.com/user-attachments/assets/1a7ddc7b-f628-4a92-a154-2c54515acc60" />
<img width="1200" height="600" alt="image" src="https://github.com/user-attachments/assets/4e2c9104-7be1-4b51-9c5d-7b7f013715a7" />





## Project Structure
```
ai-wiki-quiz/
├── backend/            # FastAPI server
│   ├── routers/       # API endpoints
│   ├── services/      # AI & Scraper logic
│   ├── main.py        # Entry point
│   └── database.py    # DB connection
├── frontend/           # React application
│   ├── src/
│   │   ├── components/
│   │   └── services/
│   └── index.css      # Tailwind setup
└── README.md
```
