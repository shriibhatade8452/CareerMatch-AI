# CareerMatch AI – AI-Powered Resume Screening & Job Recommendation System

CareerMatch AI is a web-based application designed to help job seekers analyze their resumes, identify their skills, discover suitable job opportunities, and understand which skills they need to improve.

The system extracts text from uploaded resumes, identifies skills, calculates job match scores, performs skill gap analysis, recommends learning resources, and evaluates resume quality.

## ✨ Features

* **User Authentication:** Register and log in to access personalized features.
* **Resume Upload:** Upload resumes in PDF and DOCX formats.
* **Resume Parsing:** Extract text from uploaded resumes.
* **Skill Extraction:** Identify technical and soft skills using a predefined skill list and regular expressions.
* **Job Recommendations:** Compare resume skills with job requirements and display matching opportunities.
* **Job Match Score:** Calculate a percentage based on matched required skills.
* **Skill Gap Analysis:** Identify skills that are missing for a selected job.
* **Course Recommendations:** Suggest learning resources related to missing skills.
* **Resume Quality Analysis:** Evaluate resume sections and provide improvement suggestions.
* **Career Development:** Help users understand their strengths and areas for improvement.
* **Database Integration:** Store user information, resumes, jobs, recommendations, and courses in MySQL.

## 🛠️ Technologies Used

| Technology          | Purpose                                                       |
| ------------------- | ------------------------------------------------------------- |
| Python              | Backend logic and resume analysis                             |
| Flask               | Web application framework                                     |
| HTML5               | Webpage structure                                             |
| CSS3                | Website styling                                               |
| MySQL               | Database management                                           |
| SQL                 | Database queries                                              |
| PyPDF2              | Extract text from PDF resumes                                 |
| python-docx         | Extract text from DOCX resumes                                |
| Regular Expressions | Identify predefined skills in resume text                     |
| scikit-learn        | Available for machine learning and text-processing extensions |

## 🧠 How It Works

1. The user registers or logs in.
2. The user uploads a resume in PDF or DOCX format.
3. The application extracts text from the resume.
4. The system identifies skills using a predefined skill list.
5. Extracted skills are compared with the required skills for available jobs.
6. A job match percentage is calculated.
7. Missing skills are displayed through skill gap analysis.
8. Relevant courses are retrieved from the database.
9. Resume quality analysis provides a score and improvement suggestions.

## 🏗️ Project Structure

```text
AI_Resume_Job_Recommendation/
│
├── ai/
│   ├── __init__.py
│   ├── resume_parser.py
│   ├── skill_extractor.py
│   ├── job_matcher.py
│   └── resume_quality.py
│
├── database/
│   └── database.sql
│
├── static/
│   ├── css/
│   │   └── style.css
│   └── uploads/
│
├── templates/
│   ├── index.html
│   ├── login.html
│   ├── register.html
│   ├── dashboard.html
│   ├── upload_resume.html
│   ├── jobs.html
│   ├── job_recommendations.html
│   ├── job_match.html
│   ├── skill_gap.html
│   ├── courses.html
│   ├── resume_quality.html
│   ├── career_development.html
│   └── job_selection.html
│
├── app.py
├── config.py
├── requirements.txt
└── README.md
```

*Note: The structure above reflects the intended organization. Adjust filenames to match the files actually present in your repository.*

## ⚙️ Installation and Setup

### Prerequisites

Install the following before running the project:

* Python 3.10 or later
* MySQL Server
* pip
* Git (optional, for cloning the repository)

### 1. Clone the Repository

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
cd AI_Resume_Job_Recommendation
```

Replace `YOUR_GITHUB_REPOSITORY_URL` with your repository's actual URL.

### 2. Create a Virtual Environment

```bash
python -m venv venv
```

Activate it on Windows:

```powershell
.\venv\Scripts\Activate.ps1
```

If PowerShell blocks activation, you can use Command Prompt:

```bat
venv\Scripts\activate.bat
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

If a requirements file is not available or incomplete, install the packages used by the project:

```bash
pip install Flask mysql-connector-python PyPDF2 python-docx scikit-learn nltk
```

### 4. Configure the Database

1. Start your MySQL server.
2. Open MySQL Workbench or your MySQL command-line client.
3. Create the project database:

```sql
CREATE DATABASE ai_resume_system;
```

4. Select the database and execute the SQL statements in `database/database.sql`, if that file contains the required schema and seed data.

The database stores user accounts, uploaded resume text, job listings, recommendations, and learning resources.

### 5. Configure Database Credentials

Open `config.py` and configure your local MySQL credentials:

```python
MYSQL_HOST = "localhost"
MYSQL_USER = "root"
MYSQL_PASSWORD = "YOUR_MYSQL_PASSWORD"
MYSQL_DB = "ai_resume_system"
```

Replace `YOUR_MYSQL_PASSWORD` with your local MySQL password.

**Security:** Never publish your real database password or other secrets to GitHub. For a public repository, use environment variables and keep `.env` files out of version control.

### 6. Run the Application

From the project root directory, run:

```bash
python app.py
```

Open the local address shown in the terminal, usually:

http://127.0.0.1:5000

Register an account, log in, and upload a sample resume to explore the features.

## 📊 Job Match Score

The current skill-based matching approach calculates the match score as follows:

**Match Score = (Number of Matched Required Skills / Total Required Skills) × 100**

For example, if a job requires five skills and the resume contains three of them:

```text
Match Score = (3 / 5) × 100 = 60%
```

The score reflects required-skill overlap. It should not be interpreted as a guaranteed probability of getting hired.

## 🔬 AI and Matching Approach

The current implementation primarily uses rule-based text processing:

* Predefined skill matching
* Regular-expression-based skill extraction
* Skill comparison and percentage-based scoring
* Rule-based resume quality checks
* Database-driven course recommendations

The current version does not train a machine learning model. TF-IDF, cosine similarity, semantic matching, and trained models can be explored as future enhancements if they are not yet implemented.

## 🔮 Future Enhancements

* Integrate TF-IDF and cosine similarity for resume-to-job text comparison.
* Explore advanced NLP models for contextual skill and job-description matching.
* Add more job listings and learning resources.
* Support scanned resumes through OCR.
* Improve resume parsing for tables and multi-column layouts.
* Add secure cloud deployment and external job portal integration.
* Provide more detailed career development insights.

## ⚠️ Limitations

* Skill extraction depends on a predefined list of skills.
* Resume matching may not fully understand context or equivalent skills.
* Text extraction quality depends on the uploaded document.
* Job and course recommendations depend on the available database records.
* The application is an academic prototype and should not be used as the sole basis for hiring decisions.

## 🎓 Project Information

**Project Name:** CareerMatch AI

**Project Type:** Final-Year Academic Project

**Domain:** Artificial Intelligence, Natural Language Processing, and Web Development

**Primary Language:** Python

## 👩‍💻 Author

Developed as a final-year academic project to explore resume analysis, skill matching, job recommendations, and career development using Python, Flask, and MySQL.

## 📄 License

Choose a license before distributing this project publicly. If you intend to make the code open source, you can consider the MIT License after confirming that it suits your requirements.

---

⭐ If you find this project useful, consider giving the repository a star on GitHub.
