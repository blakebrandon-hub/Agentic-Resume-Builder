# Agentic Resume Builder

The **Agentic Resume Builder** is a high-performance, AI-driven application designed to transform raw career data and job descriptions into polished, ATS-optimized professional resumes. Powered by **Google Gemini 2.5 Flash**, the system employs a multi-agent orchestration strategy to analyze, draft, and critique resumes in an iterative loop to ensure the highest quality output.

## 🤖 The Multi-Agent Pipeline
Unlike standard AI prompts, this tool utilizes three specialized agents to produce superior results:

*   **Resume Analyzer**: Examines the target job description to extract key technical skills, soft skills, and specific experience requirements that need to be prioritized.
*   **Resume Writer**: An elite professional writing agent that tailors the candidate's background to the job description using strong action verbs and ATS-friendly formatting.
*   **Resume Critic**: Acts as a final reviewer, evaluating the draft for ATS compatibility and alignment with the job goals; it can send the resume back for revisions if it fails to meet college-standard quality.

## ✨ Key Features
*   **Iterative Refinement**: The system runs up to **three iterations** between the Writer and Critic to polish the final draft based on automated feedback.
*   **Multiformat Support**: Seamlessly extracts text from **PDF, DOCX, and TXT** files to build a comprehensive candidate profile.
*   **Professional Word Export**: Generates a clean, formatted `.docx` file featuring **narrow margins (0.5")**, bolded headers, and structured bullet points ready for submission.
*   **Real-time Activity Tracking**: The modern web interface provides a live activity log and phase-based progress bar so users can watch the agents work.

## 🛠️ Technical Stack
*   **LLM**: Google Gemini 2.5 Flash (`gemini-2.5-flash`).
*   **Backend**: Flask (Python) with **threading** for asynchronous background processing.
*   **Libraries**: 
    *   `google-genai` for model interaction.
    *   `python-docx` for document generation.
    *   `PyPDF2` for PDF text extraction.
*   **Frontend**: Responsive HTML5, CSS3, and Vanilla JavaScript.

## 🚀 Setup & Installation

### 1. Prerequisites
*   Python 3.9+
*   A Google Gemini API Key

### 2. Environment Configuration
Set your Gemini API key as an environment variable:
```bash
export GEMINI_API_KEY="your_api_key_here"
```
*(Note: The app is configured to look for this specific environment variable to authenticate with Google GenAI)*.

### 3. Installation
```bash
pip install flask flask-cors python-docx PyPDF2 google-genai
```

### 4. Running the App
```bash
python app.py
```
The server will start on `http://localhost:5000`. All generated resumes are automatically saved to an `outputs/` directory created at the project root.

## 📁 Project Structure
*   `app.py`: Contains the Flask server, multi-agent logic, and file extraction utilities.
*   `templates/index.html`: A single-page dashboard for uploading files and tracking generation progress.
*   `outputs/`: Stores the final generated `.docx` resume files.
