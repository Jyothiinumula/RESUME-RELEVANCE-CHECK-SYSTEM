# Automated Resume Relevance Check System  
*Hackathon Submission - Code4EdTech 2025*  

---

## 📌 Problem Statement  
Recruiters spend hours manually screening resumes against job descriptions. This is slow, inconsistent, and difficult to scale.  

Our solution automates this process by:  
- Generating a **Relevance Score (0–100)**  
- Giving a **Verdict** (High / Medium / Low fit)  
- Highlighting **Missing Skills**  
- Providing **Suggestions for Improvement**  

---

## 🚀 Approach  
1. **Text Extraction**  
   - Extracted from resumes (PDF/DOCX) using `pdfplumber` and `python-docx`.  

2. **Skill Matching**  
   - **Hard Match**: keyword/skill search.  
   - **Soft Match**: semantic similarity with embeddings (`sentence-transformers`).  

3. **Scoring System**  
   - Final Score = 60% Hard Match + 40% Semantic Match.  
   - Verdict Rules:  
     - **High Fit** ≥ 75  
     - **Medium Fit** 50–74  
     - **Low Fit** < 50  

4. **Output**  
   - Interactive Streamlit web app.  
   - Downloadable CSV with scores and feedback.  

---

## 🛠 Tech Stack  
- **Python** (backend logic)  
- **Streamlit** (web interface)  
- **pdfplumber** & **python-docx** (text extraction)  
- **Sentence-Transformers** (embeddings for semantic match)  
- **scikit-learn, pandas, numpy** (scoring & data handling)  
- **Deployment**: Hugging Face Spaces  

---

## ⚙️ How to Run Locally  
```bash
# Clone repo
git clone https://github.com/<your-username>/resume-relevance-check.git
cd resume-relevance-check

# Install dependencies
pip install -r requirements.txt

# Run the app
streamlit run app.py

