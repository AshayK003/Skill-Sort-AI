# SkillSort AI

SkillSort AI is a web application that automates resume parsing and job recommendation. It leverages machine learning models to classify resumes into categories and recommend the most suitable jobs based on the extracted skills and education.

## Features

- **Resume Parsing**: Extracts relevant information such as name, contact details, skills, education, and other pertinent data from resumes.
- **Resume Categorization**: Classifies resumes into specific categories using a trained Random Forest classifier.
- **Job Recommendation**: Provides job recommendations tailored to the extracted skills and education from the resume.
- **PDF and TXT Support**: Accepts resumes in PDF and TXT formats.

## Project Structure

- **app.py**: The main application file containing routes, helper functions, and the integration of machine learning models for categorization and job recommendation.
- **models/**: Directory containing pre-trained models:
  - `model.pkl`: Random Forest classifier model for resume categorization.
  - `vectorizer.pkl`: TF-IDF vectorizer for transforming resume text for categorization.
  - `rf_classifier_job_recommendation.pkl`: Random Forest classifier model for job recommendation.
  - `tfidf_vectorizer_job_recommendation.pkl`: TF-IDF vectorizer for transforming resume text for job recommendation.
- **templates/**: Contains the HTML template(s) used in rendering the web pages.
- **static/**: Directory for static files like CSS, images, or JavaScript (if applicable).

## Installation

1. **Clone the Repository**
   ```bash
   git clone https://github.com/yourusername/SkillSort-AI.git
   cd SkillSort-AI
   ```

2. **Install Dependencies**
   Ensure you have Python 3.7+ installed. Install the required Python packages using:
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the Application**
   ```bash
   python app.py
   ```
   The application will be available at `http://127.0.0.1:5000/`.

## Usage

1. **Home Page**: Upload a resume in PDF or TXT format.
2. **Prediction**: After submission, the application will display:
   - The predicted category of the resume.
   - Recommended jobs based on the skills and education extracted from the resume.
   - Contact information, name, skills, and education details extracted from the resume.

## How It Works

- **PDF/TXT Parsing**: The uploaded resume is parsed using PyPDF2 (for PDFs) or directly read as text (for TXT files).
- **Text Cleaning**: The extracted text undergoes cleaning to remove unwanted characters and normalize the data.
- **Feature Extraction**: Skills, education, and other details are extracted using predefined lists and regex patterns.
- **Model Prediction**: The cleaned resume text is transformed using TF-IDF vectorizers and then fed into the respective Random Forest classifiers to predict the resume category and recommend jobs.

## Dependencies

- Flask
- scikit-learn
- PyPDF2
- re (Regular Expressions)


## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
