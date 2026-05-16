# Eluma
Eluma | An AI-powered mobile app for dyslexia screening, personalized learning, and progress tracking using NLP, Machine Learning, Deep learning and Gamified exercises.
<div align="center">

#  Eluma — AI-Powered Dyslexia Companion

**An intelligent mobile application for dyslexia screening, personalized learning, and progress tracking**

</div>

---

## 📖 About

Eluma is a comprehensive AI-powered mobile application designed to transform the learning experience for individuals with dyslexia. It provides personalized, multi-modal, and interactive support by integrating **Artificial Intelligence (AI)**, **Natural Language Processing (NLP)**, **Deep learning (DL)**, and **Machine Learning (ML)** within a single accessible platform.

Unlike fragmented existing tools, Eluma combines **screening**, **intervention**, and **progress tracking** in one unified solution — reducing reliance on expensive specialist interventions and making dyslexia support accessible to all.

---

## Key Features

| Module | Description |
|--------|-------------|
|  **Dyslexia Screening** | AI-driven gamified assessments for phonological, surface, and rapid naming dyslexia subtypes |
|  **Reading Assistant** | Real-time text-to-speech with synchronized word highlighting and dyslexia-friendly fonts |
|  **Writing Assistant** | NLP + Computer Vision analysis of typed, voice, or handwritten inputs |
|  **Gamified Learning** | 9 adaptive literacy games with dynamic difficulty adjustment |
|  **Recommendation Engine** | Personalized activity suggestions based on error patterns and performance |
|  **Parent Dashboard** | Visual progress tracking with daily/weekly/monthly analytics and milestone alerts |

---

## 🛠️ Tech Stack

### Frontend (Mobile App)
- **Flutter** (Dart) — Cross-platform mobile UI
- **Firebase Auth** — User authentication (Google Sign-In)
- **Firebase Realtime Database** — Real-time data sync
- **Firebase Cloud Storage** — Audio and handwriting uploads
- **Firebase Cloud Messaging** — Push notifications
- **Flutter TTS / Google STT** — Text-to-speech and speech-to-text
- **Google Gemini API** — Writing analysis, NLP, and vision processing

### Backend
- **Node.js + Express** — REST API gateway
- **Tesseract OCR** — Text extraction from images
- **FastAPI (Python)** — AI microservices (hosted on Hugging Face Spaces)

### AI / ML Models
- **MobileNetV3** — Surface dyslexia handwriting classification (90% macro F1)
- **Random Forest + SMOTE** — Rapid naming dyslexia risk prediction (70.1% recall)
- **Google Gemini Vision** — Handwriting error detection
- **Rule-Based ML** — Personalized recommendation engine

---

## 📁 Project Structure

```
eluma/
│
├── lib/                          # Flutter app source code
│   ├── main.dart                 # App entry point
│   ├── firebase_options.dart     # Firebase configuration
│   ├── firebase_backup_service.dart
│   │
│   ├── screens/
│   │   ├── home_screen.dart      # Main home screen
│   │   └── splash_screen.dart    # Splash / onboarding screen
│   │
│   ├── modules/
│   │   ├── auth/                 # Login, registration, Google Sign-In
│   │   ├── dyslexia_assesment/   # Screening modules (phonological, surface, RAN)
│   │   ├── reading_assistant/    # TTS reading with word highlighting
│   │   ├── writing_assistant/    # NLP + CV writing analysis
│   │   ├── gamified_learning/    # Adaptive literacy games
│   │   ├── recommendations/      # Personalized activity engine
│   │   └── dashboard/            # Parent/child progress dashboard
│   │
│   └── utils/                    # Shared helpers and utilities
│
├── eluma-backened/               # Node.js backend
│   ├── server.js                 # Express server entry point
│   ├── routes/
│   │   └── textAnalysis.js       # Text analysis API routes
│   ├── controllers/
│   │   └── analysisController.js # Writing analysis controller
│   ├── middleware/               # Auth and request middleware
│   ├── models_cache/             # Cached AI model data
│   ├── utils/                    # Backend utility functions
│   ├── uploads/                  # Uploaded files (images, audio)
│   ├── eng.traineddata           # Tesseract OCR language data
│   ├── package.json
│   └── server.js
│
├── android/                      # Android build files
├── ios/                          # iOS build files
├── assets/                       # Images, fonts, audio
└── pubspec.yaml                  # Flutter dependencies
```

---

##  Getting Started

### Prerequisites

- [Flutter SDK](https://flutter.dev/docs/get-started/install) (3.x or above)
- [Node.js](https://nodejs.org/) (v18 or above)
- [Android Studio](https://developer.android.com/studio) or a physical Android device (API Level 30+)
- A Firebase project with Realtime Database, Auth, and Storage enabled
- Google Gemini API key

---

### 1. Clone the Repository

```bash
git clone https://github.com/zaneb111/eluma.git
cd eluma
```

---

### 2. Flutter App Setup

```bash
# Install Flutter dependencies
flutter pub get

# Run the app
flutter run
```

> ⚠️ You will need to add your own `google-services.json` (Android) inside `android/app/` and configure `firebase_options.dart` with your Firebase project credentials.

---

### 3. Backend Setup

```bash
cd eluma-backened

# Install dependencies
npm install

# Create a .env file with the following:
# PORT=3000
# GEMINI_API_KEY=your_gemini_api_key
# FIREBASE_CREDENTIALS_PATH=./credentials.json

# Start the server
node server.js
```

>  Add your own `credentials.json` (Firebase service account) and `.env` file. These are excluded from the repo for security.

---

##  Environment Variables

The following files are **not included** in this repository for security reasons. You must create them yourself:

| File | Location | Purpose |
|------|----------|---------|
| `.env` | `eluma-backened/` | API keys and config |
| `credentials.json` | `eluma-backened/` | Firebase service account |
| `google-services.json` | `android/app/` | Firebase Android config |
| `firebase_options.dart` | `lib/` | Firebase Flutter config |

---

## AI Models

The AI models used in Eluma are deployed on **Hugging Face Spaces** and served via FastAPI endpoints:

| Model | Task | Architecture |
|-------|------|-------------|
| Surface Dyslexia Classifier | Letter reversal detection | MobileNetV3 (ONNX) |
| RAN Dyslexia Classifier | Rapid naming risk prediction | Random Forest + SMOTE |
| Writing Error Detector | Grammar, spelling, reversal analysis | Google Gemini Vision API |

---

##  Screenshots

<img width="323" height="726" alt="Screenshot 2026-04-30 000010" src="https://github.com/user-attachments/assets/cec4aea5-7bda-4b48-9a73-c028464f5946" />
<img width="318" height="697" alt="Screenshot 2026-04-30 000044" src="https://github.com/user-attachments/assets/31c12d16-725a-4aee-a226-02a6e143fbfc" />
<img width="382" height="843" alt="Screenshot 2026-04-30 001534" src="https://github.com/user-attachments/assets/5315949e-145c-46ac-afcd-197577055b1f" />
<img width="398" height="908" alt="Screenshot 2026-04-30 132737" src="https://github.com/user-attachments/assets/b14ef02b-c619-479d-9197-6f1a04035222" />

<img width="318" height="726" alt="Screenshot 2026-04-30 205132" src="https://github.com/user-attachments/assets/17ddb65f-d5e7-49c9-a4bf-e579ab08e0f9" />



## 📄 License

This project was developed as a Final Year Project at COMSATS University Islamabad. All rights reserved by the authors.

---

<div align="center">
Made with ❤️ for dyslexic learners everywhere
</div>
