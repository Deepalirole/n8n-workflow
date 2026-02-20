# n8n-workflow
🤖 AI-Powered Job Search & Resume Tailoring Automation
An autonomous end-to-end pipeline built with n8n and Google Gemini AI that scrapes job leads, manages them in a database, and generates ATS-optimized professional summaries and skill sets for every role automatically.

🚀 Overview
Applying for jobs manually is time-consuming and often leads to "generic" applications that fail ATS filters. This project automates the entire "top-of-funnel" job search process. It doesn't just find jobs; it uses Generative AI to ensure your profile matches the specific requirements of every single listing.

Key Features
Automated Web Scraping: Extracts real-time job data (Role, Company, Link) from major job boards.

Centralized Tracking: Syncs all leads into a Google Sheets dashboard for status management.

AI Agent Integration: Utilizes an AI Agent with Gemini 1.5 Flash to perform deep analysis of job descriptions.

ATS Optimization: Automatically generates tailored 'Professional Summaries' and 'Key Skills' based on the specific job requirements.

Rate-Limit Management: Includes custom "Wait" logic to handle API quotas and ensure stable long-running executions.

🛠️ Tech Stack
Automation Engine: n8n

AI Model: Google Gemini 1.5 Flash (via Google AI Studio)

Database/Tracker: Google Sheets API

Logic: JavaScript (within n8n nodes)

📐 Workflow Architecture
The system consists of two primary interconnected workflows:

The Scraper: Periodically checks job boards and appends new, unique listings to the Google Sheet with a status of Pending.

The AI Processor:

Fetches rows marked as Pending.

Passes the Job Role and Company context to the Gemini AI Agent.

The AI generates a customized resume summary optimized for keywords found in the job link.

Updates the spreadsheet with the generated text and moves the status to Resume Ready.

⚙️ Setup & Installation
n8n Setup: Import the provided .json workflow files into your n8n instance.
<img width="1836" height="831" alt="Screenshot 2026-02-19 102100" src="https://github.com/user-attachments/assets/b4fd9978-2983-41da-baa7-d958c3a2e02c" />

Credentials:

Add your Google Gemini API Key to the Gemini Chat Model node.

Connect your Google Account via OAuth2 for Google Sheets access.

Spreadsheet: Create a Google Sheet with headers: Role, Company, Link, Status, and Tailored Text.

Environment Variables: Ensure your Wait nodes are set (10s recommended) to stay within free-tier API limits.

📈 Impact
Time Saved: Reduced time spent on job searching and resume tailoring by ~90%.

Efficiency: Able to process and tailor 20+ applications in minutes.

Technical Growth: Deepened experience in Agentic Workflows, API Rate Limiting, and Data Transformation.
