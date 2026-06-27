# AI Resume Analyzer

AI Resume Analyzer is a machine learning powered Streamlit web app that reviews a resume with ATS-style analysis. It extracts text from an uploaded PDF resume, predicts the most likely career domain, estimates an ATS score, compares the resume against a target job role, and suggests missing skills and improvement tips.

## Features

- Upload a resume in PDF format
- Analyze resume content with a trained ML model
- Predict the most suitable career domain
- Calculate an ATS-style score
- Compare resume skills against a target role
- Show skill gaps, job compatibility, and resume improvement tips

## Project Structure

- `app.py` - Streamlit app
- `train_model.py` - trains the resume classification model and saves artifacts
- `datasets/Resume/Resume.csv` - training dataset
- `datasets/job_dataset.csv` - job matching dataset
- `models/` - stores generated model files
- `assets/style.css` - custom styling

## Requirements

Install the Python dependencies listed in `requirements.txt`.

Main packages used by the project:

- streamlit
- pandas
- scikit-learn
- pdfplumber
- numpy

## Setup

1. Clone or open the project folder.
2. Create and activate a virtual environment.
3. Install dependencies:

```bash
pip install -r requirements.txt
```

## Train the Model

The app expects these files in the `models/` folder:

- `models/model.pkl`
- `models/tfidf.pkl`

If they are missing, generate them by running:

```bash
python train_model.py
```

This script trains a logistic regression model on `datasets/Resume/Resume.csv` and saves the trained model and TF-IDF vectorizer into `models/`.

## Run the App

Start the Streamlit app with:

```bash
streamlit run app.py
```

Then open the local URL shown in the terminal, usually `http://localhost:8501`.

## How To Use

1. Enter your desired job role.
2. Upload a resume in PDF format.
3. View the ATS score, detected career domain, skill gaps, and job match recommendations.

## Notes

- The app works with PDF resumes only.
- Job compatibility is based on the resume text and the job dataset included in the project.
- For best results, use a text-based PDF rather than a scanned image PDF.

## License

No license file is currently included in the repository.
