This project is an AI-powered Python tool that automatically extracts structured information from unstructured resume PDFs. It uses Natural Language Processing (NLP) and regular expressions to identify and extract key candidate details like name, email, phone, skills, education, experience, certifications, and LinkedIn profile.

 Features
 Parses resumes in PDF format
 Named Entity Recognition (NER) with spaCy for name extraction
 Extracts contact info (email & phone)
 Identifies education background
 Extracts work experience
 Detects relevant technical and soft skills
 Finds certifications
 Extracts LinkedIn profile URLs
 Returns results in structured JSON format

 Tech Stack
Python 3.7+
spaCy (NLP)
pdfplumber (PDF text extraction)
Regular Expressions (re)
JSON

 Project Structure
│ ├── resume_parser.py # Main Python script ├── sample_resume.pdf # Sample resume for testing ├── requirements.txt # Python dependencies └── README.md # Project documentation


Install required packages:
pip install -r requirements.txt
requirements.txt: pdfplumber spacy
Download spaCy English model:
python -m spacy download en_core_web_sm

Usage
Place your PDF resume (e.g., my_resume.pdf) in the project folder.
Run the parser script:
python resume_parser.py

Output:
JSON output will be printed in the terminal showing extracted fields.

Example:
{ "name": "John Doe", "email": "john.doe@example.com", "phone": "+1 123-456-7890", "skills": ["Python", "Machine Learning", "Excel"], "education": ["Bachelor of Technology in Computer Science, XYZ University"], "experience": ["Worked as a Data Scientist at ABC Corp"], "certificates": ["Google Data Analytics Professional Certificate"], "linkedin": "https://www.linkedin.com/in/johndoe" }

Supported Fields
Name (via spaCy NER)
Email & Phone (via regex)
Skills (keyword match from a customizable list)
Education (degree/institute matching)
Experience (role-based keyword search)
Certifications (keyword search for “certificate” etc.)
LinkedIn URL (regex)

 Notes
This is a basic parser that works well on clean, text-based resumes.
Does not support scanned (image-based) PDFs unless OCR is added.
You can expand the skill, education, and experience keyword lists for better accuracy.

 Future Enhancements
Use of advanced NER models (e.g., spaCy transformers or BERT)
Export to CSV or database
Web-based interface using Streamlit or Gradio
OCR support with Tesseract for image-based PDFs

