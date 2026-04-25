🚨 Safe Word Emergency Alert

A real-time emergency safety application that uses voice detection, GPS tracking, and automated alerts to notify emergency contacts instantly when a safe word is triggered.

📋 Table of Contents
Overview
Features
Tech Stack
Installation
Environment Setup
Database Setup (Supabase)
Running the Project
Deployment
Project Structure
API Overview
Security Notes
Roadmap
License
🎯 Overview

Safe Word Emergency Alert is a safety-first web application designed to help users in medical emergencies or unsafe situations.

When the user speaks a pre-set safe word, the system automatically:

📍 Captures live GPS location
🔋 Shares battery status
🏥 Sends medical information
📞 Alerts emergency contacts in order
🗺️ Continuously updates location during emergency
✨ Features
🧠 Core Features
🎤 Voice-activated safe word detection
⏱️ 10-second cancel countdown (prevents false alarms)
📍 Live location tracking (updates every 5s)
📞 Sequential emergency calling system
🔋 Battery level sharing
👤 User Features
Secure login (Supabase Auth)
Emergency contact management
Drag & drop priority ordering
Medical profile storage
🧑‍💼 Admin Features
User management dashboard
Role assignment system
Emergency event logs
🛠️ Tech Stack
Frontend
React 18
TypeScript
Vite
Tailwind CSS
shadcn/ui
React Router
Backend
Supabase (PostgreSQL + Auth + Edge Functions)
Browser APIs
Web Speech API (voice recognition)
Geolocation API
Battery API
📦 Installation
git clone https://github.com/muffinneedstochill/safetyzone.git
cd safetyzone
npm install
⚙️ Environment Setup

Create a .env file:

VITE_SUPABASE_URL=your_supabase_url
VITE_SUPABASE_ANON_KEY=your_supabase_anon_key
🗄️ Database Setup (Supabase)
Create project on Supabase
Go to SQL Editor
Run migration files from:
/supabase/migrations/
Enable Auth in Supabase dashboard
🚀 Running the Project
npm run dev

App runs on:

http://localhost:5173
🔐 Supabase Edge Function Setup
Install CLI
npm install -g supabase
Login
supabase login
Link project
supabase link --project-ref YOUR_PROJECT_REF
Deploy functions
supabase functions deploy send-alert
🌐 Deployment
⚡ Deploy to GitHub Pages
1. Install dependency
npm install --save-dev gh-pages
2. Update package.json
"homepage": "https://muffinneedstochill.github.io/safetyzone",
"scripts": {
  "predeploy": "npm run build",
  "deploy": "gh-pages -d dist"
}
3. Update Vite config
base: "/safetyzone/"
4. Deploy
npm run deploy
5. Enable GitHub Pages
Settings → Pages
Source: gh-pages branch
⚡ Deploy to Netlify
npm run build
netlify deploy --prod
📁 Project Structure
src/
 ├── components/
 ├── contexts/
 ├── db/
 ├── pages/
 ├── services/
 ├── types/
 ├── App.tsx
 ├── main.tsx

supabase/
 ├── functions/
 ├── migrations/
🔌 API Overview
profiles

Stores user info + medical data

emergency_contacts

Stores emergency contacts + priority

emergency_events

Logs emergency triggers

location_updates

Tracks live movement

📡 Edge Function: send-alert

Sends emergency notifications to contacts including:

location
battery level
medical info
timestamp
⚠️ Security Notes (IMPORTANT)
First admin should NOT be auto-assigned in production
Use HTTPS always (required for voice + GPS APIs)
Do NOT expose Supabase service role key
Validate all user input
🧠 Browser Compatibility
Feature	Chrome	Edge	Firefox	Safari
Voice API	✅	✅	❌	❌
GPS	✅	✅	✅	✅
Battery API	✅	⚠️	❌	❌

👉 Recommended: Chrome / Edge

🧭 Roadmap
SMS alerts via Twilio
Mobile app (React Native)
Offline emergency fallback mode
Wearable integration
Emergency services API integration
Geo-fencing alerts
📄 License

MIT License

❤️ Final Note

This is a life-critical safety tool, not a demo app. Always test carefully before real-world use.
