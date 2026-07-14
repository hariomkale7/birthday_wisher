# 🎂 Automated Birthday Wisher

An automated Python application that sends personalized birthday wishes via email. The application runs every day using **GitHub Actions**, checks if today matches a birthday in `birthdays.csv`, and automatically sends a personalized birthday email—even when your computer is turned off.

---

## ✨ Features

- 📅 Automatically checks birthdays every day
- 📧 Sends personalized birthday emails
- 🎲 Randomly selects one of three birthday letter templates
- ☁️ Runs automatically using GitHub Actions
- 🔒 Stores email credentials securely using GitHub Secrets
- 📴 No need to keep your computer running
- 📂 Easy-to-manage birthday list using a CSV file

---

## 🛠️ Tech Stack

- Python 3
- Pandas
- SMTP (Gmail)
- Git & GitHub
- GitHub Actions
- GitHub Secrets

---

## 📁 Project Structure

```
birthday_wisher/
│
├── .github/
│   └── workflows/
│       └── scheduled.yml
│
├── letter_templates/
│   ├── letter_1.txt
│   ├── letter_2.txt
│   └── letter_3.txt
│
├── birthdays.csv
├── main.py
├── requirements.txt
└── README.md
```

---

## ⚙️ How It Works

Every day GitHub Actions performs the following steps:

1. Starts a temporary Ubuntu virtual machine.
2. Downloads the latest version of this repository.
3. Installs Python and required dependencies.
4. Reads birthday data from `birthdays.csv`.
5. Compares today's month and day with the birthday list.
6. Randomly selects one of the birthday templates.
7. Replaces `[NAME]` with the recipient's name.
8. Sends the birthday email using Gmail SMTP.
9. Deletes the temporary virtual machine after execution.

---

## 🔒 Security

This project follows secure coding practices by keeping sensitive credentials out of the source code.

- Gmail credentials are **not hardcoded**.
- Email address and App Password are stored securely using **GitHub Secrets**.
- The application accesses credentials through environment variables.

Example:

```python
import os

MY_EMAIL = os.environ.get("MY_EMAIL")
MY_PASSWORD = os.environ.get("MY_PASSWORD")
```

---

## 📅 Birthday Data Format

The application expects a CSV file with the following structure:

```csv
name,email,year,month,day
John,john@example.com,1998,5,12
Jane,jane@example.com,2001,9,27
```

---

## 🚀 Running Locally

### 1. Clone the repository

```bash
git clone https://github.com/hariomkale7/birthday_wisher.git
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Configure your email credentials

Create environment variables:

```
MY_EMAIL=your_email@gmail.com
MY_PASSWORD=your_gmail_app_password
```

### 4. Update `birthdays.csv`

Add the birthdays you want to track.

### 5. Run the application

```bash
python main.py
```

---

## ☁️ GitHub Actions Automation

The application is scheduled to run automatically every day using **GitHub Actions**.

Each scheduled execution:

- Downloads the project
- Installs dependencies
- Runs the Python script
- Sends birthday emails if a matching birthday is found

No external server or personal computer is required.

---

## 💡 Future Improvements

- HTML email templates
- Birthday image attachments
- Multiple recipients sharing the same birthday
- Database integration
- Web dashboard for managing birthdays
- Email delivery logging
- Unit tests

---

## 👨‍💻 Author

**Hariom Kale**

- GitHub: https://github.com/hariomkale7
- LinkedIn: *(Add your LinkedIn profile URL here)*

---

## ⭐ If you found this project interesting, consider giving it a star!