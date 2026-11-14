# agrilingo_ai
AI-Powered Crop Disease Detection and Smart Agricultural Advisory System

agrilingo_ai/
│
├── frontend/                    # Next.js
│   ├── public/
│   │   └── images/
│   │
│   ├── src/
│   │   ├── app/
│   │   │   ├── layout.jsx
│   │   │   ├── page.jsx         # Landing Page
│   │   │   ├── globals.css
│   │   │   │
│   │   │   ├── login/
│   │   │   │   └── page.jsx
│   │   │   ├── register/
│   │   │   │   └── page.jsx
│   │   │   ├── dashboard/
│   │   │   │   ├── layout.jsx
│   │   │   │   └── page.jsx
│   │   │   ├── disease-detection/
│   │   │   │   └── page.jsx
│   │   │   ├── detection-result/
│   │   │   │   └── page.jsx
│   │   │   ├── advisory/
│   │   │   │   └── page.jsx
│   │   │   ├── crop-history/
│   │   │   │   └── page.jsx
│   │   │   ├── weather/
│   │   │   │   └── page.jsx
│   │   │   └── reports/
│   │   │       └── page.jsx
│   │   │
│   │   ├── components/
│   │   │   ├── layout/
│   │   │   │   ├── Navbar.jsx
│   │   │   │   ├── Footer.jsx
│   │   │   │   └── Sidebar.jsx
│   │   │   ├── ui/
│   │   │   │   ├── Button.jsx
│   │   │   │   └── Card.jsx
│   │   │   └── detection/
│   │   │       ├── ImageUpload.jsx
│   │   │       └── SeverityCard.jsx
│   │   │
│   │   ├── services/
│   │   │   ├── api.js
│   │   │   ├── authService.js
│   │   │   └── detectionService.js
│   │   │
│   │   ├── i18n/
│   │   │   └── config.js
│   │   └── locales/
│   │       ├── en.json
│   │       ├── si.json
│   │       └── ta.json
│   │
│   ├── .env.local               # Do not commit
│   ├── .env.example             # Commit example keys
│   ├── package.json
│   └── next.config.mjs
│
├── backend/                     # Python FastAPI
│   ├── app/
│   │   ├── main.py
│   │   ├── api/
│   │   │   ├── auth.py
│   │   │   ├── detection.py
│   │   │   ├── history.py
│   │   │   └── reports.py
│   │   ├── models/
│   │   │   ├── user.py
│   │   │   └── prediction.py
│   │   ├── schemas/
│   │   ├── services/
│   │   │   ├── ai_service.py
│   │   │   └── advisory_service.py
│   │   ├── database.py
│   │   └── config.py
│   ├── tests/
│   ├── requirements.txt
│   └── .env.example
│
├── ai-model/
│   ├── datasets/                # Ignored data
│   ├── notebooks/
│   ├── training/
│   │   └── train.py
│   ├── inference/
│   │   └── predict.py
│   ├── evaluation/
│   ├── saved_models/
│   └── requirements.txt
│
├── database/
│   ├── schema.sql
│   └── migrations/
│
├── docs/
│   ├── api-contract.md
│   └── project-plan.md
│
├── .gitignore
└── README.md
