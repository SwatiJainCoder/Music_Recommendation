# Musicly

This is a music recommendation app system.

## Introduction

This simple system was finished through the Flask and Vue3 frameworks

Here is a **clean, professional README.md** you can use for your project.
It explains folder structure, setup steps, how to run backend + Vue frontend, environment variables, and database setup.

---

# **NEXI Project — Fullstack Application (FastAPI + Vue 3 + SQL Server)**

This project is a full-stack application built with:

* **Backend:** Python (FastAPI), SQLAlchemy
* **Frontend:** Vue 3
* **Database:** SQL Server
* **Architecture:** REST API backend + SPA frontend

---

## **📁 Project Structure**

```
/app
│── /routes/           # API route handlers
│── /static/           # Static assets served by backend
│── __init__.py        # Creates FastAPI app instance
│── models.py          # SQLAlchemy models mapped to database schema
│
/web                   # Vue 3 frontend
│── /public/           # Public static files (favicon, index.html assets)
│── /src/
│     ├── /components/ # Vue components/pages
│     ├── /router/     # Vue Router configuration (index.js)
│     └── App.vue      # Main Vue entry component
│
app.py                 # Backend entry point (run FastAPI)
config.py              # Database configuration (SQLAlchemy + SQL Server)
sql/                   # SQL scripts to create database tables
```

---

# **🚀 Getting Started**

## **1. Clone the Project**

```bash
git clone <your-repo-url>
cd <project-folder>
```

---

# **🖥 Backend Setup (FastAPI + SQL Server)**

## **2. Create a Virtual Environment**

```bash
python3 -m venv venv
source venv/bin/activate   # Linux / macOS
venv\Scripts\activate      # Windows
```

## **3. Install Dependencies**

```bash
pip install -r requirements.txt
```

---

## **4. Configure Database Connection**

Edit **config.py**:

```python
SQLALCHEMY_DATABASE_URL = "mssql+pyodbc://username:password@localhost/dbname?driver=ODBC+Driver+17+for+SQL+Server"
```

Ensure SQL Server driver is installed:

### **➡ Windows**

```bash
pip install pyodbc
```

### **➡ Linux**

Install driver first:

```bash
sudo apt install msodbcsql17
```

---

## **5. Initialize Database**

Run SQL scripts:

```bash
sqlcmd -S localhost -d master -i sql/create_tables.sql
```

Or manually create tables using SQL Server Management Studio.

---

## **6. Run Backend Server**

```bash
uvicorn app:app --reload
```

Backend runs at:

```
http://localhost:8000
```

Swagger Docs:

```
http://localhost:8000/docs
```

---

# **🌐 Frontend Setup (Vue 3)**

## **7. Install Node Modules**

```
cd web
npm install
```

## **8. Run Development Server**

```
npm run dev
```

Frontend runs at:

```
http://localhost:5173
```

---

# **🔗 Connecting Frontend & Backend**

In **web/src/config.js** or inside API service calls:

```javascript
export const API_BASE_URL = "http://localhost:8000";
```

Make sure CORS is enabled in FastAPI (**app/**init**.py**):

```python
from fastapi.middleware.cors import CORSMiddleware

app.add_middleware(
    CORSMiddleware,
    allow_origins=["*"],
    allow_credentials=True,
    allow_methods=["*"],
    allow_headers=["*"],
)
```

---

# **📦 Build for Production**

## **Frontend Build**

```
cd web
npm run build
```

Output found in:

```
web/dist/
```

## **Serve Static Frontend (optional)**

Copy build files into FastAPI static folder:

```
/app/static/
```

---

# **🧪 Testing**

Run backend tests:

```
pytest
```

Run linting:

```
npm run lint
```

---

# **🧱 Tech Stack Summary**

| Layer          | Tech                        |
| -------------- | --------------------------- |
| Backend        | FastAPI, SQLAlchemy, Python |
| Frontend       | Vue 3, Vue Router, Vite     |
| Database       | SQL Server                  |
| API Docs       | Swagger UI                  |
| Static Serving | FastAPI StaticFiles         |

---

# **📄 License**

MIT or your preferred license.

---

If you want, I can also generate:

✅ `.env.example`
✅ Dockerfile + docker-compose
✅ Full architecture diagram
✅ API documentation template

Just tell me!
