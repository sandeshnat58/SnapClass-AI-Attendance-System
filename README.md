# 🎓 SnapClass — AI-Powered Attendance Management System

**An intelligent attendance management system powered by Face Recognition, Voice Recognition, and AI-driven automation.**

SnapClass is an AI-powered attendance management system designed to simplify and modernize the traditional attendance process. It provides a digital platform where students can register, log in using facial recognition, enroll in subjects, and monitor their attendance records.

Built using Python and Streamlit, SnapClass integrates AI-based face recognition and optional voice-based enrollment to make attendance management more convenient and efficient. The application also includes student and teacher workflows, subject management, attendance tracking, and database integration.

🌐 **Live Demo:** [Open SnapClass](https://snapclass-ai-attendance-system.streamlit.app/)

💻 **GitHub Repository:** [SnapClass AI Attendance System](https://github.com/sandeshnat58/SnapClass-AI-Attendance-System)

---

## 📌 Table of Contents

- [Project Overview](#-project-overview)
- [Problem Statement](#-problem-statement)
- [Project Objectives](#-project-objectives)
- [Key Features](#-key-features)
- [Technology Stack](#-technology-stack)
- [How SnapClass Works](#-how-snapclass-works)
- [Project Structure](#-project-structure)
- [Installation and Setup](#-installation-and-setup)
- [Environment Variables and Secrets](#-environment-variables-and-secrets)
- [Deployment](#-deployment)
- [Advantages](#-advantages)
- [Future Enhancements](#-future-enhancements)
- [Learning Outcomes](#-learning-outcomes)
- [Author](#-author)

---

## 🚀 Project Overview

Traditional attendance management systems often rely on manual roll calls, paper registers, or basic digital entry systems. These approaches can be time-consuming, difficult to maintain, and prone to human error.

SnapClass aims to improve this process by introducing AI-based identification and centralized attendance tracking.

The application provides a platform for students to access their profiles, enroll in subjects, and view attendance statistics. Teachers can use the system's subject and attendance management capabilities.

The project combines machine learning concepts, computer vision, audio processing, database integration, and interactive web development in a single application.

## 🎯 Problem Statement

Traditional attendance systems face several challenges:

- Manual attendance takes valuable classroom time.
- Paper-based records can be difficult to organize and maintain.
- Maintaining attendance records across multiple subjects can be inconvenient.
- Manual calculations make attendance tracking more complicated.
- Conventional systems may not provide a convenient way for students to review their attendance.

**Solution:** SnapClass introduces an AI-assisted digital attendance platform that combines facial recognition, optional voice enrollment, subject management, and attendance statistics to streamline the attendance workflow.

## 🎯 Project Objectives

The primary objectives of SnapClass are to:

1. Automate student identification using face recognition.
2. Provide a convenient student login experience.
3. Support optional voice enrollment for voice-based attendance workflows.
4. Simplify subject enrollment and unenrollment.
5. Maintain digital student and attendance records.
6. Display attendance statistics through an interactive dashboard.
7. Provide database-backed access to application data.
8. Deploy the application online so users can access it through a web browser.

## ✨ Key Features

### 1. 🤖 AI-Based Face Recognition

- Uses a camera input to capture a student's face.
- Processes the captured image through the face recognition pipeline.
- Attempts to identify a registered student.
- Handles scenarios where no face or multiple faces are detected.
- Supports registration when a face is not recognized.

### 2. 🎙️ Optional Voice Enrollment

- Allows users to record a short audio phrase during profile registration.
- Generates a voice embedding through the voice processing pipeline.
- Supports integration with voice-based attendance functionality.

*Note: Voice enrollment and voice-based attendance are related but separate workflows. Their availability depends on the corresponding pipeline and configuration.*

### 3. 👨‍🎓 Student Dashboard

Students can access a personalized dashboard that supports:

- Student profile information.
- Enrolled subject listings.
- Attendance statistics.
- Total recorded classes and attended classes.
- Subject enrollment and unenrollment options.

### 4. 📚 Subject Management

- Displays subjects associated with a student's enrollment.
- Organizes subject information such as name, subject code, and section.
- Provides an option to enroll in available subjects.
- Supports unenrollment from a subject.

### 5. 📊 Attendance Tracking

- Retrieves attendance records from the database.
- Organizes attendance statistics by subject.
- Calculates the total number of recorded attendance entries and attended entries.
- Displays the results in the student dashboard.

The attendance totals depend on the records returned by the database and the application's attendance data model.

### 6. 🗄️ Database Integration

SnapClass uses Supabase for database operations, including student information, subject enrollment, and attendance records.

The database layer is separated from the user interface to help keep data access and application logic organized.

### 7. 🌐 Interactive Web Application

- Built with Streamlit.
- Provides an interactive browser-based interface.
- Supports camera and audio inputs where available.
- Organizes application functionality into reusable components and screens.

### 8. ☁️ Cloud Deployment

The application is deployed using Streamlit Community Cloud, making the web application accessible online without requiring users to run the interface locally.

---

## 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| Python | Core programming language |
| Streamlit | Interactive web application |
| NumPy | Numerical and image-array operations |
| Pillow (PIL) | Image loading and processing |
| Face Recognition Pipeline | Facial feature extraction and student identification |
| Voice Processing Pipeline | Audio-based feature extraction |
| Supabase | Database and backend data operations |
| Git | Version control |
| GitHub | Source code hosting |
| Streamlit Community Cloud | Application deployment |

**Additional implementation details:** The exact face recognition algorithm, classifier configuration, voice embedding model, and database schema depend on the project's implementation.

---

## ⚙️ How SnapClass Works

The general student workflow is as follows:

1. **Open the application:** Access SnapClass through its deployed web URL.
2. **Select the student workflow:** Navigate to the student login screen.
3. **Capture a face:** Use the camera input to capture an image.
4. **Process the image:** The face recognition pipeline attempts to identify the registered student.
5. **Authenticate or register:** A recognized student can access their profile. An unrecognized face may trigger the new-profile registration flow.
6. **Optional voice enrollment:** During registration, the student can record an audio phrase if voice enrollment is available.
7. **Access the dashboard:** View enrolled subjects and attendance statistics.
8. **Manage subjects:** Enroll in or unenroll from subjects as supported by the application.
9. **Retrieve attendance data:** The application fetches relevant records from the database and calculates the displayed statistics.

### High-Level Architecture

```text
                    Student / Teacher
                           |
                           v
                  Streamlit Web Interface
                           |
             +-------------+-------------+
             |                           |
             v                           v
       Student Screens              Teacher Screens
             |                           |
             +-------------+-------------+
                           |
                           v
                    Application Logic
                           |
             +-------------+-------------+
             |                           |
             v                           v
      Face Recognition              Voice Processing
          Pipeline                     Pipeline
             |                           |
             +-------------+-------------+
                           |
                           v
                     Database Layer
                           |
                           v
                        Supabase
```

*This diagram represents the high-level architecture. Exact module responsibilities may differ depending on the implementation.*

---

## 📂 Project Structure

The project follows a modular structure that separates screens, components, database operations, and AI pipelines.

```text
SnapClass-AI-Attendance-System/
│
├── app.py
├── requirements.txt
├── .gitignore
│
└── src/
    ├── components/
    │   ├── header.py
    │   ├── footer.py
    │   ├── subject_card.py
    │   ├── dialog_enroll.py
    │   └── ...
    │
    ├── screens/
    │   ├── student_screen.py
    │   └── ...
    │
    ├── pipelines/
    │   ├── face_pipeline.py
    │   ├── voice_pipeline.py
    │   └── ...
    │
    ├── database/
    │   └── db.py
    │
    └── ui/
        ├── base_layout.py
        └── ...
```

**Folder responsibilities:**

- `app.py` — Application entry point.
- `src/components/` — Reusable UI components and dialogs.
- `src/screens/` — Application screens and dashboard workflows.
- `src/pipelines/` — Face and voice processing functionality.
- `src/database/` — Database access and data management.
- `src/ui/` — Shared layout and styling utilities.
- `requirements.txt` — Python dependencies.
- `.gitignore` — Files and folders excluded from Git tracking.

*The structure above is representative. Keep it synchronized with the actual files in your repository.*

---

## 💻 Installation and Setup

Follow these steps to run SnapClass locally.

### Prerequisites

Make sure you have:

- Python installed.
- Git installed.
- A GitHub account if you want to clone the repository.
- Access to the required Supabase project and credentials.
- A working camera and microphone if you want to test the corresponding features.

### Step 1: Clone the Repository

```bash
git clone https://github.com/sandeshnat58/SnapClass-AI-Attendance-System.git
```

### Step 2: Navigate to the Project Directory

```bash
cd SnapClass-AI-Attendance-System
```

### Step 3: Create a Virtual Environment

**Windows:**

```bash
python -m venv venv
```

Activate it:

```bash
venv\Scripts\activate
```

**macOS / Linux:**

```bash
python3 -m venv venv
source venv/bin/activate
```

### Step 4: Install Dependencies

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

### Step 5: Configure Supabase Credentials

Configure the environment variables or Streamlit secrets required by the project's database module.

Do not commit actual credentials to GitHub.

### Step 6: Run the Application

```bash
streamlit run app.py
```

Once the application starts, open the local URL shown in your terminal.

---

## 🔐 Environment Variables and Secrets

SnapClass requires the Supabase configuration expected by its database module.

For local development, you can use a `.env` file if your code is configured to load environment variables, or use Streamlit's secrets configuration if that is what your application expects.

For Streamlit Community Cloud:

1. Open your application in Streamlit Community Cloud.
2. Open **Manage app**.
3. Open the app's settings and locate **Secrets**.
4. Add the required Supabase credentials using the exact names expected by your code.

Example format only:

```toml
SUPABASE_URL = "YOUR_SUPABASE_PROJECT_URL"
SUPABASE_KEY = "YOUR_SUPABASE_KEY"
```

Replace these example names with the actual variable names used in your project.

**Security best practices:**

- Never commit real API keys, passwords, or database secrets.
- Keep `.env` and other sensitive configuration files out of version control.
- Use the least-privileged database access available for the intended workflow.
- Do not expose service-role credentials in client-facing code.
- If a secret is accidentally committed, rotate it rather than relying only on deleting the file.

---

## ☁️ Deployment

SnapClass is deployed using Streamlit Community Cloud.

### Deployment Steps

1. Push the project code to GitHub.
2. Sign in to Streamlit Community Cloud using an authorized GitHub account.
3. Create a new application.
4. Select the repository `sandeshnat58/SnapClass-AI-Attendance-System`.
5. Select the `main` branch.
6. Set the main file path to `app.py`.
7. Configure the required secrets and environment settings.
8. Deploy the application and check the deployment logs if any errors occur.

### Live Application

**[Launch SnapClass](https://snapclass-ai-attendance-system.streamlit.app/)**

If the live URL changes, update the link above with the current deployed URL.

---

## 🌟 Advantages

- Reduces dependence on manual attendance entry.
- Provides a digital alternative to paper-based records.
- Demonstrates the practical use of computer vision and audio processing.
- Helps organize attendance data by subject.
- Provides students with a convenient way to review attendance statistics.
- Uses a modular code structure for easier maintenance.
- Demonstrates end-to-end development, from application logic to cloud deployment.

---

## 🔮 Future Enhancements

Potential improvements for future versions include:

- **Teacher Dashboard Enhancements:** Improve class management and attendance review workflows.
- **Attendance Reports:** Export attendance summaries to CSV or PDF.
- **Analytics Dashboard:** Add charts showing subject-wise attendance trends.
- **Low Attendance Alerts:** Notify students when their attendance falls below a configurable threshold.
- **Improved Recognition:** Evaluate recognition accuracy under different lighting and environmental conditions.
- **Liveness Detection:** Add safeguards against printed photographs or replayed media.
- **Role-Based Access Control:** Strengthen student and teacher permissions.
- **Audit Logs:** Track important changes to attendance records.
- **Automated Testing:** Add unit and integration tests for database operations and recognition workflows.
- **Responsive UI Improvements:** Enhance usability across different screen sizes.

These are proposed enhancements, not claims that every feature is already implemented.

---

## 📚 Learning Outcomes

Developing SnapClass provides practical experience with:

- Python application development.
- Streamlit-based UI development.
- Computer vision and face recognition workflows.
- Audio processing and voice embeddings.
- Database integration with Supabase.
- Modular project architecture.
- Git and GitHub version control.
- Cloud deployment and debugging.
- Managing application configuration and secrets.
- Troubleshooting real-world deployment issues.

---

## 👨‍💻 Author

**Sandesh Nat**

AI/ML & Data Science Enthusiast

- **GitHub:** [@sandeshnat58](https://github.com/sandeshnat58)
- **Project Repository:** [SnapClass AI Attendance System](https://github.com/sandeshnat58/SnapClass-AI-Attendance-System)
- **Live Demo:** [SnapClass on Streamlit](https://snapclass-ai-attendance-system.streamlit.app/)

---

## ⭐ Support the Project

If you find SnapClass interesting, consider giving the repository a ⭐ on GitHub.

Feedback, suggestions, and contributions that improve the project's functionality, reliability, and usability are welcome.

**Built with Python, AI, and a passion for solving real-world problems.**

