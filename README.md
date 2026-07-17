# 🌐 Language Detection Web App

A FastAPI-powered web application that detects the language of input text using a pre-trained machine learning model.

## 🧠 Project Overview

This application leverages a trained **Logistic Regression** model with **Count Vectorizer** to identify the language of any given text input. The system can accurately classify text into multiple languages with confidence scores.

## ✨ Key Features

- **Real-time Language Detection**: Instant prediction via a RESTful API
- **Web Interface**: User-friendly HTML interface with Bootstrap styling
- **Confidence Scores**: Displays prediction confidence percentages
- **Input Validation**: Enforces reasonable input constraints (max 1000 chars, requires alphabetic characters)
- **Responsive Design**: Works on desktop and mobile devices
- **Professional Dashboard**: Footer section displaying model metrics and development credits

## 📊 Model Details

| Component | Specification |
|-----------|---------------|
| **Model Type** | Logistic Regression |
| **Vectorizer** | Count Vectorizer |
| **Features** | 3,500 |
| **N-gram Range** | (1, 1) |
| **Accuracy** | 83.10% |
| **Training Status** | Pre-trained artifacts |

## 🚀 Quick Start

### Prerequisites
- Python 3.7+
- pip package manager

### Installation
```bash
pip install -r requirements.txt
```

### Running the Application
```bash
uvicorn app:app --host 0.0.0.0 --port 8000
```

The application will be available at:
- **API Endpoint**: `http://localhost:8000/predict` (POST)
- **Web Interface**: `http://localhost:8000/`

### API Usage
**POST** `/predict`
```json
{
  "text": "Hello, how are you? This is a test sentence in English."
}
```

**Success Response**:
```json
{
  "prediction": "english",
  "confidence": 95.23
}
```

**Error Response**:
```json
{
  "error": "Empty input"
}
```

## 📁 Project Structure

```
.
├── app.py                    # FastAPI application
├── requirements.txt         # Dependencies
├── saved/                   # Trained model artifacts
│   ├── best_model.h5
│   ├── label_encoder.pkl
│   └── vectorizer.pkl
└── templates/
    └── index.html           # Web interface
```

## 🛠️ Technology Stack

| Layer | Technology |
|-------|------------|
| **Framework** | FastAPI |
| **Template Engine** | Jinja2 |
| **Model** | Scikit-learn (Logistic Regression) |
| **Vectorization** | Scikit-learn (CountVectorizer) |
| **Web Interface** | HTML/CSS (Bootstrap 5) |
| **Runtime** | Uvicorn |
| **Input Validation** | Pydantic |

## 🎯 Use Cases

- **Content Classification**: Determine the language of user-generated content
- **Multilingual Support**: Identify languages for adaptive UI/UX
- **Integration**: REST API endpoint for other applications
- **Educational**: Language learning and analysis tool

## 📈 Performance Metrics

The model demonstrates:
- **Accuracy**: 83.10% on test dataset
- **Input Handling**: Processes up to 1000 characters efficiently
- **Response Time**: Sub-second prediction for typical input
- **Confidence Display**: Confidence scores for prediction reliability

## 📝 Notes

- The model and vectorizer are pre-trained and included as artifacts
- Input validation ensures robust error handling
- Production-ready with proper error responses and logging
- Designed for scalability with FastAPI

## 👥 Credits & Acknowledgments

**Developed by:**
- Muhammad Hamza Tahir
- Instructor: Dr Rao Adeel Nawab
- Course: A3

**Acknowledgments:**
- Bootstrap 5 CSS framework for responsive design
- FastAPI for high-performance API development
- Scikit-learn for machine learning capabilities

## 🔒 Deployment Considerations

For production deployment:
- Use HTTPS with SSL certificates
- Implement rate limiting
- Configure proper logging and monitoring
- Set appropriate timeouts
- Consider model caching for performance
