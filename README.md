# 🌱 AgriLingo AI

### AI-Powered Crop Disease Detection and Farmer Advisory System

AgriLingo AI is a web-based agricultural platform designed to help farmers identify crop diseases using Artificial Intelligence.

Farmers can upload images of crop leaves, identify possible diseases, view AI confidence scores, receive disease-specific advice, and track previous detection results.

The system aims to support **Sinhala, Tamil, and English**.

---

## 1. Technology Stack

| Component | Technology |
|---|---|
| Frontend | Next.js (App Router) |
| Styling | Tailwind CSS |
| Backend | Python FastAPI |
| AI Model | Python, TensorFlow/Keras |
| Database | MySQL |
| API Communication | REST API |
| Version Control | Git & GitHub |

## 2. Team Members and Responsibilities

| Member | Responsibility | Initial Branch |
|---|---|---|
| Nadun | Landing Page, Login, Register, Navbar, Footer | `feature/landing-auth` |
| Dinethya | Dashboard, Disease Detection, Detection Results | `feature/detection-ui` |
| Dinithi | Advisory, Weather, Crop History, Languages, Reports | `feature/farmer-services` |
| Pethum | Backend APIs, MySQL, Authentication | `feature/backend-api` |
| Charith | AI Model Training, Disease Prediction, Model Integration | `feature/ai-model` |

## 3. GitHub Branch Structure

We use the following branches:

- `main` – Stable and tested version of the project.
- `develop` – Shared development branch where completed features are combined.
- `feature/...` – Branches for developing individual features.
- `fix/...` – Branches for fixing bugs.

**Important Rules:**

1. Do not directly push changes to `main`.
2. Do not directly push changes to `develop`.
3. Always create your feature branch from the latest `develop`.
4. Use meaningful commit messages.
5. Create a Pull Request (PR) to merge your work into `develop`.
6. Review and test changes before merging.
7. Do not commit passwords, API keys, `.env` files, or large datasets.

## 4. Clone the Project

Open VS Code and open the terminal.

**Step 1 – Clone the repository**

```bash
git clone https://github.com/charith0418/agrilingo_ai.git
```

**Step 2 – Open the project**

```bash
cd agrilingo_ai
```

**Step 3 – Switch to the development branch**

```bash
git switch develop
```

**Step 4 – Get the latest updates**

```bash
git pull origin develop
```

All members must clone the same repository. Do not create separate repositories for individual members.

## 5. Create Your Own Feature Branch

Before starting a new task, update your local `develop` branch.

```bash
git switch develop
git pull origin develop
```

Create a new branch:

```bash
git switch -c feature/your-feature-name
```

**Examples:**

Devindi:

```bash
git switch -c feature/landing-auth
```

Dinethya:

```bash
git switch -c feature/detection-ui
```

Nimsara:

```bash
git switch -c feature/farmer-services
```

Pethum:

```bash
git switch -c feature/backend-api
```

Charith:

```bash
git switch -c feature/ai-model
```

These commands are for creating branches for the first time. If your branch already exists, use `git switch branch-name` instead.

For later tasks, create smaller branches such as `feature/login-page` or `feature/severity-results`.

## 6. Project Folder Structure

```text
agrilingo_ai/
│
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── app/
│   │   │   ├── page.jsx
│   │   │   ├── layout.jsx
│   │   │   ├── globals.css
│   │   │   ├── login/
│   │   │   ├── register/
│   │   │   ├── dashboard/
│   │   │   ├── disease-detection/
│   │   │   ├── detection-result/
│   │   │   ├── advisory/
│   │   │   ├── crop-history/
│   │   │   ├── weather/
│   │   │   └── reports/
│   │   ├── components/
│   │   ├── services/
│   │   ├── i18n/
│   │   └── locales/
│   └── package.json
│
├── backend/
│   ├── app/
│   │   ├── main.py
│   │   ├── api/
│   │   ├── models/
│   │   ├── schemas/
│   │   ├── services/
│   │   └── database.py
│   ├── tests/
│   └── requirements.txt
│
├── ai-model/
│   ├── datasets/
│   ├── training/
│   ├── inference/
│   ├── evaluation/
│   └── saved_models/
│
├── database/
├── docs/
├── .gitignore
└── README.md
```

This is our planned structure. Some directories and files will be added as development progresses.

## 7. Frontend Setup – Next.js

All frontend developers should use the existing `frontend` project.

**Important:** Only the member responsible for initial project setup should create the Next.js project.

Initial setup, from the repository root:

```bash
npx create-next-app@latest frontend --js --tailwind --eslint --app --src-dir --use-npm
```

Once the frontend is committed and merged into `develop`, other members should not run `create-next-app` again.

Instead, run:

```bash
cd frontend
npm install
```

Start the frontend:

```bash
npm run dev
```

Open:

`http://localhost:3000`

Install additional packages when required:

```bash
npm install axios lucide-react recharts i18next react-i18next
```

When adding a package, commit the updated `package.json` and `package-lock.json`.

### Basic Next.js Page Example

File: `frontend/src/app/page.jsx`

```jsx
export default function Home() {
  return (
    <main className="min-h-screen bg-green-50 p-10">
      <h1 className="text-3xl font-bold text-green-900">
        Welcome to AgriLingo AI
      </h1>

      <p className="mt-4">
        Smart farming with Artificial Intelligence.
      </p>
    </main>
  );
}
```

### Basic Component Example

File: `frontend/src/components/Navbar.jsx`

```jsx
import Link from "next/link";

export default function Navbar() {
  return (
    <nav className="flex justify-between p-5 bg-green-800 text-white">
      <h1 className="font-bold">AgriLingo AI</h1>

      <div className="flex gap-4">
        <Link href="/">Home</Link>
        <Link href="/login">Login</Link>
      </div>
    </nav>
  );
}
```

In Next.js, create a `page.jsx` file inside the corresponding `app` folder to create a route.

For example:

`src/app/login/page.jsx` → `/login`

## 8. Backend Setup – FastAPI

Backend developers should work inside the `backend` directory.

From the repository root:

```bash
cd backend
```

Create a Python virtual environment:

```bash
python -m venv venv
```

Activate it.

Windows PowerShell:

```powershell
.\venv\Scripts\Activate.ps1
```

macOS/Linux:

```bash
source venv/bin/activate
```

Install dependencies from `requirements.txt`:

```bash
pip install -r requirements.txt
```

If the backend is being initialized for the first time, install the basic packages and add them to `requirements.txt`:

```bash
pip install fastapi "uvicorn[standard]"
pip freeze > requirements.txt
```

### Basic FastAPI Example

File: `backend/app/main.py`

```python
from fastapi import FastAPI
from fastapi.middleware.cors import CORSMiddleware

app = FastAPI(title="AgriLingo AI API")

app.add_middleware(
    CORSMiddleware,
    allow_origins=["http://localhost:3000"],
    allow_credentials=True,
    allow_methods=["*"],
    allow_headers=["*"],
)

@app.get("/")
def home():
    return {"message": "AgriLingo AI Backend Running"}

@app.get("/health")
def health():
    return {"status": "ok"}
```

Start the backend from the `backend` folder:

```bash
uvicorn app.main:app --reload
```

Backend URL:

`http://localhost:8000`

API documentation:

`http://localhost:8000/docs`

The CORS configuration above is intended for local development. Configure allowed origins separately for production.

## 9. Frontend and Backend API Connection

Create the following file:

`frontend/src/services/api.js`

```javascript
import axios from "axios";

const api = axios.create({
  baseURL:
    process.env.NEXT_PUBLIC_API_URL ||
    "http://localhost:8000",
});

export default api;
```

Create a local environment file:

`frontend/.env.local`

```env
NEXT_PUBLIC_API_URL=http://localhost:8000
```

**Do not commit `.env.local` to GitHub.**

Example of calling the backend from a client component:

```jsx
"use client";

import { useEffect, useState } from "react";
import api from "@/services/api";

export default function BackendStatus() {
  const [status, setStatus] = useState("Checking...");

  useEffect(() => {
    api.get("/health")
      .then((response) => setStatus(response.data.status))
      .catch(() => setStatus("Backend unavailable"));
  }, []);

  return <p>Backend: {status}</p>;
}
```

Both frontend and backend servers must be running to test this connection.

## 10. AI Model Development Rules

AI developers should work mainly in the `ai-model` directory.

Responsibilities:

1. Select appropriate crop disease datasets.
2. Clean and preprocess images.
3. Train a baseline classification model.
4. Evaluate performance using separate training, validation, and test datasets.
5. Save the trained model.
6. Create a prediction function.
7. Coordinate with the backend developer to integrate the model.

### Basic Prediction Function Structure

File: `ai-model/inference/predict.py`

```python
def predict_disease(image):
    """
    TODO: Load the trained model.
    TODO: Preprocess the input image.
    TODO: Run model inference.
    TODO: Return predicted disease and confidence.
    """
    raise NotImplementedError(
        "Disease prediction model is not integrated yet."
    )
```

This is only a starter function. It is not a working disease detection model.

### Important AI Rules

- Do not upload large datasets directly to GitHub.
- Do not commit large trained model files.
- Use the same image preprocessing steps during training and prediction.
- Document model accuracy and limitations.
- Do not assume that high confidence always means a correct prediction.
- Test real-world image performance where suitable evaluation data is available.
- Severity estimation and disease progress tracking must be evaluated separately.

## 11. Proposed API Endpoints

Frontend and backend developers should agree on these endpoints before integration.

| Method | Endpoint | Purpose |
|---|---|---|
| POST | `/auth/register` | Register farmer |
| POST | `/auth/login` | Login |
| POST | `/detections` | Upload image and predict |
| GET | `/detections/{id}` | Get detection result |
| GET | `/history` | Get previous detections |
| GET | `/advisory/{disease}` | Get disease advice |
| GET | `/reports/{id}` | Download report |

These are planned endpoints and may change during implementation.

Document the final request and response formats in `docs/api-contract.md`.

## 12. Git Commands Every Member Should Know

**Check your current branch**

```bash
git branch
```

**Check modified files**

```bash
git status
```

**Get the latest development code**

```bash
git switch develop
git pull origin develop
```

**Switch to your own branch**

```bash
git switch feature/your-feature-name
```

**Save changes locally**

```bash
git add .
git commit -m "Describe your changes"
```

**Push a new branch to GitHub**

```bash
git push -u origin feature/your-feature-name
```

**Push later commits**

```bash
git push
```

**Bring the latest development changes into your feature branch**

```bash
git fetch origin
git merge origin/develop
```

Always check your branch before running Git commands.

## 13. Pull Request Instructions

After completing your task:

1. Test your code locally.
2. Commit and push your branch.
3. Open the GitHub repository.
4. Go to **Pull requests**.
5. Select **New pull request**.
6. Select `develop` as the base branch.
7. Select your feature branch as the compare branch.
8. Write a short description of the changes.
9. Request another member to review.
10. Merge only after approval and successful checks.

### Example Pull Request Description

**Title:** Add Disease Detection Upload Page

**Changes:**
- Created image upload component.
- Added image preview.
- Added Analyze button.
- Implemented responsive layout.

**Testing:**
- Tested on desktop and mobile.
- Confirmed page loads without errors.

## 14. Coding Guidelines

To keep our project organized, all developers should follow these rules.

**Frontend:**
- Use functional React components.
- Use PascalCase for component names, such as `Navbar.jsx`.
- Use Next.js App Router for navigation.
- Use Tailwind CSS for styling.
- Reuse common buttons, cards, and navigation components.
- Use `"use client"` only when client-side interactivity is required.
- Keep API requests in service files where practical.
- Make every page responsive.

**Backend:**
- Keep API routes separate from business logic.
- Validate user input.
- Handle errors properly.
- Use environment variables for database credentials and secrets.
- Do not store passwords as plain text.
- Keep API responses consistent.

**AI:**
- Keep training code separate from inference code.
- Record model versions and evaluation results.
- Avoid making unsupported medical or agricultural treatment claims.
- Provide clear warnings for uncertain results.

## 15. Git Commit Message Examples

Use meaningful messages.

Good examples:

```text
feat: add landing page
feat: create disease upload component
feat: implement login API
fix: resolve navbar mobile issue
fix: correct image preview
docs: update README instructions
test: add authentication tests
```

Avoid messages such as:

```text
update
changes
done
final
test123
```

## 16. Files That Should Not Be Uploaded

Add appropriate rules to the root `.gitignore` file.

```gitignore
# Node.js
node_modules/
.next/
out/

# Python
venv/
.venv/
__pycache__/
*.pyc

# Secrets
.env
.env.*
!.env.example
!.env.*.example

# AI datasets and model files
ai-model/datasets/
ai-model/saved_models/
*.h5
*.keras
*.pt
*.pth

# System files
.DS_Store
Thumbs.db
```

Never commit real passwords, database credentials, or secret keys.

Small model metadata and documentation can still be committed separately.

## 17. Before Submitting a Pull Request

Every team member should confirm:

- [ ] I am working on the correct feature branch.
- [ ] My code follows the agreed folder structure.
- [ ] I have tested my changes.
- [ ] I have checked for errors.
- [ ] I have not committed passwords or secret files.
- [ ] I have used meaningful commit messages.
- [ ] I have pushed my latest changes.
- [ ] I have created a Pull Request targeting `develop`.
- [ ] I have described what I changed.

## 18. Development Workflow

Our standard development process:

**Get latest `develop` → Create feature branch → Write code → Test → Commit → Push → Pull Request → Review → Merge into `develop`**

The `main` branch will contain only stable and tested releases.

---

### Team Reminder

AgriLingo AI is a team project. Keep your code organized, communicate before editing shared files, and regularly update your branch with the latest development changes.

**One Repository. Separate Branches. Shared Development.**
