# 📄 PDF AI Analyzer - Project Documentation

**TEAM NAME:** team VICTUS 
**Project Type:** Frontend Development with AI Integration  
**Technology Stack:** React.js, Tailwind CSS, Claude AI API  

PDF AI Analyzer - Full Stack Application
A powerful PDF analysis application with real AI-powered insights using Claude API.
🚀 Features

Real PDF Text Extraction - Extract text from any PDF document
AI-Powered Analysis - Get intelligent insights using Claude AI
Multiple Analysis Modes - Brief, Detailed, and Keywords extraction
Batch Processing - Analyze multiple PDFs at once
Analysis History - Save and revisit past analyses
Statistics Dashboard - Track your usage
Dark Mode - Easy on the eyes
Export & Copy - Download or copy results instantly

📋 Prerequisites

Node.js (v16 or higher)
npm or yarn
Anthropic API Key (Get one here)

🛠️ Backend Setup
1. Create Backend Directory
bashmkdir pdf-analyzer-backend
cd pdf-analyzer-backend
2. Initialize Project
bashnpm init -y
3. Install Dependencies
bashnpm install express cors dotenv multer pdf-parse @anthropic-ai/sdk
npm install --save-dev nodemon
4. Create Files
Create the following files in your backend directory:

server.js - Main server file (copy from artifact)
package.json - Already created, update scripts section
.env - Environment variables

5. Configure Environment Variables
Create a .env file:
bashANTHROPIC_API_KEY=your_actual_api_key_here
PORT=3001
NODE_ENV=development
Important: Replace your_actual_api_key_here with your actual Anthropic API key.
6. Update package.json Scripts
Add these scripts to your package.json:
json{
  "scripts": {
    "start": "node server.js",
    "dev": "nodemon server.js"
  }
}
7. Start the Backend Server
bashnpm run dev
The server will start on http://localhost:3001
🎨 Frontend Setup
Option A: Using the React Component in Your Existing Project

Copy the updated React component code
Make sure you have the required dependencies:

bashnpm install lucide-react

Update the API_URL if your backend is on a different port

Option B: Create React App from Scratch
bashnpx create-react-app pdf-analyzer-frontend
cd pdf-analyzer-frontend
npm install lucide-react
Replace the contents of src/App.js with the updated frontend component.
Start Frontend
bashnpm start
The app will open at http://localhost:3000
🔧 API Endpoints
Health Check
GET /health
Analyze Single PDF
POST /api/analyze
Content-Type: multipart/form-data

Body:
- pdf: PDF file
- mode: "brief" | "detailed" | "keywords"
Analyze Multiple PDFs
POST /api/analyze-batch
Content-Type: multipart/form-data

Body:
- pdfs: Array of PDF files (max 10)
- mode: "brief" | "detailed" | "keywords"
Extract Text Only
POST /api/extract-text
Content-Type: multipart/form-data

Body:
- pdf: PDF file
📝 Usage

Upload PDFs - Click the upload area and select one or multiple PDF files
Select Mode - Choose between Brief, Detailed, or Keywords analysis
Analyze - Click "Analyze with AI" to get insights
Review Results - Read the AI-generated analysis
Export - Download as text or copy to clipboard
History - Access previous analyses anytime

🔒 Security Notes

Never commit your .env file to version control
Add .env to your .gitignore file
Keep your API keys secure
Consider implementing rate limiting for production
Add authentication for production deployments

📦 Project Structure
pdf-analyzer/
├── backend/
│   ├── server.js
│   ├── package.json
│   ├── .env
│   └── .gitignore
└── frontend/
    ├── src/
    │   ├── App.js
    │   └── ...
    ├── package.json
    └── public/
🐛 Troubleshooting
Backend won't start

Check if port 3001 is available
Verify your Anthropic API key is correct
Ensure all dependencies are installed

CORS errors

Make sure backend is running on port 3001
Check CORS configuration in server.js

PDF parsing fails

Ensure PDFs are not password-protected
Check file size (max 10MB by default)
Verify PDF is not corrupted

API calls fail

Verify backend URL in frontend (API_URL constant)
Check browser console for errors
Ensure backend server is running

🚀 Deployment
Backend (Heroku, Railway, etc.)

Set environment variables in your hosting platform
Update CORS origins for your frontend domain
Deploy backend code

Frontend (Vercel, Netlify, etc.)

Update API_URL to your backend URL
Build the frontend: npm run build
Deploy the build folder

📄 License
MIT License - Feel free to use this project for personal or commercial purposes.
🤝 Contributing
Contributions are welcome! Please feel free to submit a Pull Request.
💡 Tips

Use the "Brief" mode for quick summaries
Use "Detailed" for comprehensive analysis
Use "Keywords" for quick topic identification
Enable dark mode for comfortable viewing
Check history to compare analyses
