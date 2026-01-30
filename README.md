# GitHub Webhook Listener 🚀

This project listens to GitHub webhook events, stores them in MongoDB,
and displays them on a simple web dashboard.

---

## 🧠 How it works

1. GitHub sends webhook events (push events)
2. Flask server receives the webhook
3. Data is parsed and saved to MongoDB
4. Events are shown on a UI dashboard

---

## 🛠 Tech Stack

- Python (Flask)
- MongoDB
- Ngrok
- HTML / JavaScript

---

## 📂 Project Structure

webhook-repo/
│
├── app.py              # main app entry
│
├── db/
│   └── mongo.py        # Mongo connection
│
├── models/
│   └── event.py        # event schema builder
│
├── routes/
│   ├── webhook.py      # POST /webhook
│   └── events.py       # GET /events
│
├── templates/
│   └── index.html
│
├── static/
│   └── script.js
│
├── schema_helper.py    # (we'll merge logic)
└── requirements.txt

---

## ▶️ How to Run Locally

### 1️⃣ Install dependencies
```bash
pip install -r requirements.txt.