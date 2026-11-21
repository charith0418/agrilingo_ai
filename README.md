
agrilingo_ai/
│
├── frontend/                         # React Native + Expo
│   ├── assets/
│   │   ├── images/
│   │   ├── icons/
│   │   └── fonts/
│   │
│   ├── src/
│   │   ├── screens/
│   │   │   ├── HomeScreen.tsx
│   │   │   ├── DetectionScreen.tsx
│   │   │   ├── ResultScreen.tsx
│   │   │   ├── DiseaseInfoScreen.tsx
│   │   │   ├── LoginScreen.tsx
│   │   │   ├── RegisterScreen.tsx
│   │   │   ├── FarmerDashboardScreen.tsx
│   │   │   ├── HistoryScreen.tsx
│   │   │   ├── ReportsScreen.tsx
│   │   │   ├── VolunteerDashboardScreen.tsx
│   │   │   ├── VolunteerChatScreen.tsx
│   │   │   ├── FertilizerCalculatorScreen.tsx
│   │   │   ├── FertilizerShopsScreen.tsx
│   │   │   ├── OrderRequestScreen.tsx
│   │   │   ├── WeatherScreen.tsx
│   │   │   └── ProfileScreen.tsx
│   │   │
│   │   ├── components/
│   │   │   ├── PrimaryButton.tsx
│   │   │   ├── DiseaseCard.tsx
│   │   │   ├── LoadingSpinner.tsx
│   │   │   └── ImageUploader.tsx
│   │   │
│   │   ├── navigation/
│   │   │   ├── RootNavigator.tsx
│   │   │   ├── FarmerNavigator.tsx
│   │   │   └── VolunteerNavigator.tsx
│   │   │
│   │   ├── services/
│   │   │   ├── api.ts
│   │   │   ├── authService.ts
│   │   │   ├── detectionService.ts
│   │   │   ├── volunteerService.ts
│   │   │   ├── fertilizerService.ts
│   │   │   └── weatherService.ts
│   │   │
│   │   ├── contexts/
│   │   │   └── AuthContext.tsx
│   │   │
│   │   ├── types/
│   │   │   ├── disease.ts
│   │   │   ├── user.ts
│   │   │   └── advisory.ts
│   │   │
│   │   ├── constants/
│   │   │   ├── colors.ts
│   │   │   └── config.ts
│   │   │
│   │   └── utils/
│   │       └── formatDate.ts
│   │
│   ├── App.tsx
│   ├── app.json
│   ├── package.json
│   ├── package-lock.json
│   └── tsconfig.json
│
├── backend/                          # Python + FastAPI
│   ├── app/
│   │   ├── main.py
│   │   │
│   │   ├── api/
│   │   │   ├── detection.py
│   │   │   ├── farmers.py
│   │   │   ├── volunteers.py
│   │   │   ├── consultations.py
│   │   │   ├── fertilizer.py
│   │   │   └── weather.py
│   │   │
│   │   ├── services/
│   │   │   ├── prediction_service.py
│   │   │   ├── severity_service.py
│   │   │   ├── report_service.py
│   │   │   └── fertilizer_service.py
│   │   │
│   │   ├── schemas/
│   │   │   ├── prediction.py
│   │   │   ├── consultation.py
│   │   │   └── fertilizer.py
│   │   │
│   │   ├── core/
│   │   │   ├── config.py
│   │   │   └── security.py
│   │   │
│   │   └── db/
│   │       └── client.py
│   │
│   ├── tests/
│   │   ├── test_detection.py
│   │   └── test_consultations.py
│   │
│   ├── requirements.txt
│   └── .env.example
│
├── ai-model/                         # AI research and development
│   ├── notebooks/
│   │   ├── data_preparation.ipynb
│   │   ├── model_training.ipynb
│   │   └── model_evaluation.ipynb
│   │
│   ├── datasets/                    # Local, not tracked in Git
│   │   ├── train/
│   │   ├── val/
│   │   └── test/
│   │
│   ├── saved_models/                # Usually stored outside Git
│   │   ├── paddy_v2_best.keras
│   │   └── classes.json
│   │
│   └── evaluation/
│       ├── classification_report.csv
│       └── confusion_matrix.png
│
├── database/
│   ├── migrations/
│   ├── seed/
│   └── policies/
│
├── docs/
│   ├── architecture/
│   ├── api/
│   ├── diagrams/
│   └── testing/
│
├── .gitignore
└── README.md
