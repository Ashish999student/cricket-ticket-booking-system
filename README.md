# 🏏 Cricket Ticket Booking System

A Flask-based web application for booking cricket match tickets online.
Developed as a Final Year MCA Project.

---

## Features

- **Admin Panel** — Schedule matches, configure seat plans, toggle booking/verification
- **Audience Portal** — Browse matches, select seats visually, download e-tickets (PDF)
- **Verification Staff** — QR code scanner to validate tickets at the gate
- **E-Ticket Generation** — PDF tickets with embedded QR codes for entry
- **Client + Server Validation** — Full form validation on all inputs

---

## Project Structure

```
Cricket_Ticket_Booking_System/
├── app.py                # Flask app factory & blueprint registration
├── init_db.py            # Database initialisation script
├── models.py             # SQLAlchemy models
├── requirements.txt      # Python dependencies
├── README.md
├── .gitignore
├── routes/
│   ├── auth.py           # Login, logout, registration
│   ├── admin.py          # Match, seat plan management
│   ├── user.py           # Ticket booking, download, cancel
│   ├── verify.py         # QR ticket verification
│   └── __init__.py
├── static/
│   ├── css/style.css     # Cricket-themed custom CSS
│   ├── js/validation.js  # Client-side form validation
│   ├── pdfs/             # Generated PDF e-tickets
│   ├── qrcodes/          # Generated QR code images
│   └── images/
├── templates/
│   ├── base.html         # Bootstrap 5 base layout
│   ├── index.html        # Landing page
│   ├── login.html        # Login form
│   ├── makeUser.html     # Registration form
│   ├── dash_admin.html   # Admin dashboard
│   ├── matches.html      # Match management
│   ├── seat_plan.html    # Seat plan designer
│   ├── dash_user.html    # Audience dashboard
│   ├── book_tickets.html # Visual seat selection & booking
│   ├── my_tickets.html   # Ticket history
│   ├── dash_verify.html  # Verification staff dashboard
│   └── verify_ticket.html# QR scanner
└── utils/
    ├── pdf_gen.py        # PDF e-ticket generator (ReportLab)
    ├── qr_gen.py         # QR code generator
    └── __init__.py
```

---

## Setup & Run

```bash
# 1. Create virtual environment
python -m venv venv
venv\Scripts\activate        # Windows
# source venv/bin/activate   # Linux/Mac

# 2. Install dependencies
pip install -r requirements.txt

# 3. Initialise database
python init_db.py

# 4. Run the app
python app.py
```

Open `http://127.0.0.1:5000` in your browser.

---

## Default User Types

| Type          | Access                                     |
|---------------|--------------------------------------------|
| `audience`    | Browse matches, book/cancel/download tickets |
| `admin`       | Manage matches, seat plans, toggle states  |
| `verifystaff` | Scan QR codes at the gate                  |

---

## Tech Stack

- **Backend**: Python 3, Flask, Flask-Login, SQLAlchemy
- **Database**: SQLite (via SQLAlchemy)
- **Frontend**: Bootstrap 5.3, Bootstrap Icons, Google Fonts (Rajdhani + Inter)
- **PDF**: ReportLab
- **QR Code**: qrcode library
- **QR Scanner**: html5-qrcode (CDN)
