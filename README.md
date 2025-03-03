# **Deep Learning Note-Taking Web Application With CNN and NLP for Handwritten & Voice Notes**

### **Overview**
The **Unified AI Platform** is a **Streamlit-based AI-powered web application** that enables:
- **Text Extraction** from documents.
- **Handwriting Recognition** using AI.
- **Speech-to-Text Conversion** from audio files.
- **AI-Powered Q&A** using Google Gemini AI.

It integrates **NLP and CNN models** for processing documents, handwritten text, and audio files, making it an efficient tool for digital note-taking and AI-driven analysis.

Current note-taking apps lack these integrated features, as they are usually scattered across different tools rather than unified in a single platform.

---

## **Key Features**
✅ **Text Extraction:** Extracts text from **PDFs, DOCX, and TXT** into an editable format.  
✅ **Handwriting Recognition:** Converts handwritten text images into editable text using the **Google Gemini API**.  
✅ **Speech-to-Text:** Converts **MP3 and WAV** files into text using **SpeechRecognition & Pydub**.  
✅ **AI Chatbot:** Answers queries based on extracted text using **Google Gemini AI**.  
✅ **User Authentication:** Secure login and registration using **MySQL & SHA-256 password hashing**.  
✅ **Interactive UI:** Built with **Streamlit** for real-time user interaction.

---

## **Tech Stack**
- **Programming Language:** Python 3.8+
- **Framework:** Streamlit
- **Database:** MySQL Server
- **Libraries:** PyPDF2, SpeechRecognition, Pydub, PIL, docx, google.generativeai
- **AI Model:** Google Gemini API
- **Authentication:** SHA-256 password hashing

---

## **Installation & Setup**

### **1. Clone the Repository**
```sh
git clone <repository_url>
cd <repository_folder>
```

### **2. Open VS Code and Set Up Terminal**
- Open **VS Code**
- Open **Terminal** → **Run `cmd`** (to change from PowerShell to cmd)

### **3. Install Dependencies**
```sh
pip install streamlit 
pip install mysql-connector-python
pip install PyPDF2
pip install python-docx
pip install google-generativeai
pip install python-dotenv
pip install pydub
pip install SpeechRecognition
```

### **4. Install & Configure FFMPEG (for audio processing)**
1. Download **FFMPEG v7.1** from [here](https://github.com/GyanD/codexffmpeg/releases/download/7.1/ffmpeg-7.1-essentials_build.zip)
2. Create a folder named `FFMPEG` and extract the files inside your project directory.
3. Set **Environment Variables**:

   - Copy and add the following paths to System **Environment Variables**:
   ```
   C:\Users\<......>\Path\to\ffmpeg
   C:\Users\<......>\Path\to\ffmpeg\bin
   ```

### **5. Set Up API Key for Google Gemini AI**
1. Visit [Google AI Studio](https://aistudio.google.com/prompts/new_chat) and log in.
2. Generate an **API Key** (Get API key -> Create API key -> Copy and paste in "env" file).
3. In the `.env` file in the project directory add:
   ```sh
   GOOGLE_API_KEY="your_google_api_key"
   ```

### **6. Set Up MySQL Database**
#### **a. Install MySQL & SQLyog Community**
- Reference Video **MYSQL WorkBench**: [YouTube](https://youtu.be/xvUW3kF2GzI?si=p17FCXGKb2wtUEp3)
- Download **MySQL WorkBench**: [Download Link](https://dev.mysql.com/downloads/file/?id=536787)

**b. Configure MySQL User By Executing The Query**
    
    ```sh
        ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY '123456';
        FLUSH PRIVILEGES;  -- (Ignore if it gives an error)
    ```
    
 **c. Install & Set Up SQLyog Community**
  
  - Install **SQLyog Community**: [Setup Guide](https://youtu.be/M-Dlly5v5lo)
  - Copy the SQL script from `db.sql` and execute it in **SQLyog Community** to create the database and users table.
  - If you set a password while installing the MYSQL, then use the same password in connecting and modify the password in the project code. 

### **7. Run the Application**
```sh
python -m streamlit run app2.py
```

---

## **Output & Usage**
1. **Login/Register** to access the platform.
2. Verify user registration in **SQLyog Community** using:
   ```sql
   USE chatbot;
   SELECT * FROM Users;
   ```
3. **Upload Files** (PDF, DOCX, TXT, Images, or Audio) from the **Home Menu**.
4. **Interact with AI Chatbot** using extracted text.

---

## **Benefits**
✔ **Saves Time** – Eliminates manual transcription and human effort.  
✔ **Accurate & Context-Aware** – AI ensures high precision.  
✔ **Boosts Productivity** – Quick and efficient for meetings, lectures, and reports.  

---

## **Contributors**  
**Team B10, Shri Vishnu Engineering College for Women (SVECW)**  
👩‍💻 **P. Saranya**     - 21B01A05C8  
👩‍💻 **R. Sravani**     - 22B05A0511  
👩‍💻 **K. Charmy Rose** - 21B01A0580  
👩‍💻 **K. Sathvika**    - 21B01A0567  
👩‍💻 **R. Satya**       - 22B05A0512  

