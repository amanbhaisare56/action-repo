🚀 GitHub Webhook Dashboard

A clean and scalable GitHub Webhook Listener built using Flask, MongoDB, and vanilla JavaScript.
The application captures GitHub push events, stores structured data in MongoDB, and displays them on a live auto-refreshing dashboard.

✨ Features

🔔 Receives GitHub push events using Webhooks

🧠 Parses and normalizes webhook payloads

🗄 Stores events in MongoDB with a clean schema

🌐 REST API to fetch stored events

📊 Modern UI dashboard (card-based layout)

🔁 Auto-refresh every 15 seconds (polling)

🌍 Exposed locally using ngrok

🛠 Tech Stack
Layer	Technology
Backend	Python, Flask
Database	MongoDB
Frontend	HTML, CSS, JavaScript
Tooling	GitHub Webhooks, ngrok
📁 Project Structure
github-webhook-project/
│
├── action-repo/                 # Test repository to trigger GitHub events
│
├── webhook-repo/
│   ├── app.py                   # Flask application entry point
│   ├── requirements.txt
│   ├── .env
│   │
│   ├── db/
│   │   ├── __init__.py
│   │   └── mongo.py             # MongoDB connection layer
│   │
│   ├── models/
│   │   └── event.py             # Event schema builder
│   │
│   ├── routes/
│   │   ├── webhook.py           # POST /webhook endpoint
│   │   └── events.py            # GET /events endpoint
│   │
│   ├── templates/
│   │   └── index.html           # Dashboard UI
│   │
│   └── static/
│       └── script.js            # Auto-refresh & rendering logic

⚙️ Setup Instructions
1️⃣ Clone the repository
git clone <your-repo-url>
cd github-webhook-project/webhook-repo

2️⃣ Create & activate virtual environment
python -m venv venv
venv\Scripts\activate

3️⃣ Install dependencies
pip install -r requirements.txt

4️⃣ MongoDB Setup

Ensure MongoDB is running locally

Database: github_webhooks

Collection: webhook_events

.env file
MONGO_URL=mongodb://localhost:27017
DB_NAME=github_webhooks

▶️ Run the Application
python app.py


Server will start at:

http://127.0.0.1:5000

🌍 Expose Server using ngrok
ngrok http 5000


Copy the generated HTTPS URL.

🔔 GitHub Webhook Configuration

In your GitHub repository:

Payload URL

https://<ngrok-url>/webhook


Content type

application/json


Events

Push events


Status

Active ✅

📡 API Endpoints
POST /webhook

Receives GitHub webhook events and stores them in MongoDB.

GET /events

Fetches all stored webhook events for the UI dashboard.

🖥 Dashboard UI

Open in browser:

http://127.0.0.1:5000

UI Highlights:

Card-based layout

Shows repository, branch, owner, commits

Automatically refreshes every 15 seconds

No page reload required

🔁 Auto Refresh Strategy

The frontend uses polling with JavaScript:

Calls /events every 15 seconds

Fetches latest data from MongoDB

Dynamically updates the UI

Polling was chosen for simplicity and reliability.
WebSockets can be added as a future enhancement.

🧠 Architecture Overview
GitHub Push Event
        ↓
GitHub Webhook
        ↓
Flask (/webhook)
        ↓
MongoDB
        ↓
Flask (/events)
        ↓
Dashboard UI (polls every 15 sec)

🚀 Future Improvements

Support for pull request & merge events

WebSocket-based real-time updates

Authentication & webhook secret validation

Pagination & filtering

Cloud deployment

✅ Project Status

✔ Webhook integration
✔ MongoDB persistence
✔ Modular backend architecture
✔ Auto-refreshing UI
✔ Ready for submission

👨‍💻 Author

Aman Bhaisare
Backend Developer | Flask | MongoDB | GitHub Webhooks

🎤 Interview One-Liner

I built a Flask-based GitHub webhook listener that captures push events, normalizes the payload, stores it in MongoDB, and displays it on a live dashboard that auto-refreshes every 15 seconds.