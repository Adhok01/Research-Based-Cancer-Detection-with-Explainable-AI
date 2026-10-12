Thyroid Cancer Detection System
An AI-powered web application for detecting thyroid cancer from medical images using deep learning and Grad-CAM interpretability.

🌟 Features
AI-Powered Analysis: Uses a custom FibonacciNet deep learning model for accurate thyroid cancer detection
Grad-CAM Visualization: Provides interpretable heatmaps showing which regions the AI focused on
Dual Interface:
Modern web app (FastAPI + HTML/CSS)
Streamlit dashboard
Report Generation: Download detailed DOCX reports with analysis results
Professional UI: Clean, medical-themed interface with teal/white color scheme
🏗️ Project Structure
Thyroid new/
├── app.py                      # FastAPI entry point
├── app_streamlit.py            # Streamlit application
├── model_architecture.py       # Custom neural network layers
├── requirements.txt            # Python dependencies
├── backend/
│   └── routes.py              # API endpoints
├── frontend/
│   ├── static/
│   │   ├── style.css          # Styling
│   │   └── app.js             # Frontend logic
│   └── templates/
│       └── index.html         # Main page
├── utils/
│   ├── config.py              # Configuration
│   ├── processing.py          # Image preprocessing
│   ├── gradcam.py             # Grad-CAM implementation
│   ├── report_generator.py   # DOCX report generation
│   └── logger.py              # Logging configuration
└── logs/
    └── app.log                # Application logs
🚀 Installation
Prerequisites
Python 3.8+
pip
Setup
Clone the repository

git clone <repository-url>
cd "Thyroid new"
Create virtual environment

python -m venv venv
venv\Scripts\activate  # Windows
# source venv/bin/activate  # Linux/Mac
Install dependencies

pip install -r requirements.txt
Configure Hugging Face (if model is private)

huggingface-cli login
💻 Usage
Option 1: Web Application (FastAPI)
Start the server

python app.py
Open browser Navigate to: http://localhost:8000

Upload & Analyze

Click "Upload Image"
Select a thyroid ultrasound/pathology image
View AI analysis and Grad-CAM heatmap
Download DOCX report
Option 2: Streamlit Dashboard
Run Streamlit

streamlit run app_streamlit.py
Access dashboard Opens automatically in browser (usually http://localhost:8501)

🧠 Model Architecture
FibonacciNet - Custom CNN with:

SE (Squeeze-and-Excitation) blocks
Depthwise separable convolutions
Avg2Max pooling layers
Progressive channel expansion following Fibonacci sequence
Input: 224x224 RGB images
Output: Binary classification (Benign/Malignant)

📊 API Endpoints
POST /analyze
Analyzes uploaded image and returns prediction with Grad-CAM.

Request: Multipart form-data with image file

Response:

{
  "label": "Malignant (Cancerous)",
  "score": 0.9876,
  "percent": 98.76,
  "class_id": 1,
  "is_malignant": true,
  "original_image": "base64...",
  "gradcam_image": "base64..."
}
POST /report
Generates and downloads DOCX report.

Request: Multipart form-data with image file

Response: DOCX file download

🛠️ Technologies
Backend: FastAPI, Python
Frontend: HTML5, CSS3, Vanilla JavaScript
ML Framework: TensorFlow/Keras
Model Hosting: Hugging Face Hub
Visualization: Grad-CAM, Matplotlib
Reporting: python-docx
UI Framework: Streamlit (alternative interface)
📝 Configuration
Edit utils/config.py to change:

Hugging Face repository ID
Model filename
Other settings
🔍 Logging
Logs are stored in logs/app.log and include:

Model loading events
Prediction requests
Errors and warnings
Grad-CAM generation status
🤝 Contributing
Fork the repository
Create a feature branch
Commit your changes
Push to the branch
Open a Pull Request
📄 License
[Add your license here]

👥 Authors
Adhokshaja 

🙏 Acknowledgments
FibonacciNet architecture design
Grad-CAM implementation
Medical imaging community
