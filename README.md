# 👨‍💻 Medical QA Project

This project is a **Medical Question Answering System**, designed to provide users with informative and ethical responses to medical questions. It features a **FastAPI-based backend** and a **ReactJS-based frontend** for a seamless user experience.

---

## 💡 Features

### 👨‍🎓 Medical Expertise Simulation
- 🧬 **Classifies** medical questions into relevant specialties.
- 💡 **Generates grounded answers** based on symptoms, lifestyle, and suggested remedies.

### ⚠️ Ethical Compliance
- 🛡️ Does **not prescribe** medications or treatments.
- 🤞 Encourages consulting healthcare professionals for medical advice.

### 🛠️ Easy Deployment
- 🛠️ Backend API and frontend are **containerized** using Docker.
- 🏢 Fully orchestrated with **Docker Compose** for seamless deployment.

### 📡 Frontend Hosting
- 🛋 Frontend is hosted on **Netlify** for easy access to users.

### 🌍 Local Deployment
- 💡 Backend runs efficiently on **standard hardware**, no need for GPUs.

---

## 📂 Project Structure

```
Medical-SLM/
├── docker-compose.yml                 # Orchestrates backend and frontend services
├── Dockerfile.backend                 # Dockerfile for the backend
├── Dockerfile.frontend                # Dockerfile for the frontend
├── label_encoder.pkl                  # Pre-trained label encoder for specialties
├── LICENSE                            # Project license file
├── Medical - SLM.pdf                  # Project Documentation
├── Problem Statement 2 - Medical SLM.pdf  # Problem statement document
├── SECURITY.md                        # Security policy for the project
├── README.md                          # Project documentation (this file)
├── src/                               # Backend source folder
│   ├── app/                           # FastAPI application
│   ├── requirements.txt               # Backend dependencies
│   └── model/                         # Trained models and utilities
├── Medical-SLM-frontend/              # Frontend React app
│   ├── src/                           # React app source files
│   ├── public/                        # Static files for the React app
│   └── package.json                   # Frontend dependencies
├── model/                             # Model training and fine-tuning scripts
│   └── model.safetensors              # Trained model file (download separately)
├── data/                              # Dataset for training and testing
└── README.md                          # This documentation file
```

---

## 🛠️ Prerequisites

Before running this project, ensure you have the following installed:

- 🛠️ **Docker**: For containerizing and running the backend and frontend.
- 🌍 **Docker Compose**: To orchestrate multi-container applications.
- 🚀 **ngrok** (optional): For exposing local backend to the internet during testing.
- 💻 **Node.js (v16 or above)**: For frontend development.

---

## 📚 Setup and Installation

### 1. 🔄 Clone the Repository
```bash
git clone https://github.com/charvijain12/Medical-SLM.git
cd Medical-SLM
```

### 2. 📦 Download the Trained Model
The `model.safetensors` file is not included in this repository due to its size. Download it from Google Drive and save it in the `model/` folder:

```
Medical-SLM/
└── model/
    └── model.safetensors
```

---

## 🛠️ Dockerized Setup

### 1. 🛂 Build and Start the Project

Use Docker Compose to build and run both backend and frontend services:

```bash
docker-compose up --build
```

- 🔗 Backend: http://localhost:8000
- 🔗 Frontend: http://localhost:3000

### 2. 🌐 Expose Backend Locally (Optional)

To access the backend from a public device (like a mobile phone):

```bash
grok http 8000
```

Replace the backend URL in the frontend (`Medical-SLM-frontend/src/App.js`) with the public URL provided by ngrok.

---

## 🗓 Manual Setup

### 1. 🛠️ Backend Setup

Navigate to the `src/` folder:

```bash
cd src
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Start the FastAPI server:

```bash
uvicorn app.combined_api:app --host 0.0.0.0 --port 8000 --reload
```

### 2. 🛠️ Frontend Setup

Navigate to the frontend folder:

```bash
cd Medical-SLM-frontend
```

Install dependencies:

```bash
npm install
```

Start the frontend locally:

```bash
npm start
```

---

## 🌐 Deployment

### 🛋 Frontend Hosting on Netlify

Build the React app:

```bash
npm run build
```

Deploy using the Netlify CLI:

```bash
npm install -g netlify-cli
netlify deploy --prod
```

---

## 🏠 API Documentation

### 🌐 Base URL

The backend is served at: http://localhost:8000

### 📊 Endpoints

#### 1. **`/`**
- **Method**: GET
- **Response**:
  ```json
  {
    "message": "Welcome to Medical QA API"
  }
  ```

#### 2. **`/answer`**
- **Method**: POST
- **Request**:
  ```json
  {
    "question": "What should I do if I have a headache?"
  }
  ```
- **Response**:
  ```json
  {
    "specialty": "Neurology",
    "answer": "Based on your symptoms, you may be dealing with a tension headache. Some home remedies include resting and using a cold compress. Consider consulting a neurologist."
  }
  ```

---

## 🛡️ Ethical Compliance

- ⚠️ **No Prescriptions**: The model avoids prescribing medications or treatments.
- 🤞 **Professional Advice**: Encourages users to consult healthcare professionals.
- 🛡️ **Safe Responses**: Responses are ethical, grounded, and non-harmful.

---

## 🔒 Security Policy

See the [SECURITY.md](SECURITY.md) for:

- 🔒 Responsible disclosure guidelines for vulnerabilities.
- 📧 Contact information for reporting security concerns.

---

## ℹ️ License

📚 This project is licensed under the **MIT License**.

Happy coding! 🚀

