# Message_Rakshak_Andriod_App
# 📩 MessageRakshak – Smart SMS Scam Detection Android App

This project develops an Android-based SMS scam detection system that verifies suspicious messages and classifies them as **SAFE, PROMOTIONAL, or DANGEROUS**. The system accepts user-entered messages, processes them through a structured detection pipeline, and analyzes risky keywords and suspicious links using a **rule-based scoring engine combined with Google Safe Browsing API**.

The goal of the system is to **reduce the risk of phishing attacks, scam messages, and malicious links by providing a lightweight, explainable, and user-friendly mobile security assistant.**

---

# How the System Works (Step-by-Step)

The application follows a **hybrid detection pipeline**. Each module processes the message sequentially before producing the final classification result.

---

## Step 1: User Authentication

The process begins when the user logs into the application through the **local login/signup interface**.

The authentication system uses:

- SharedPreferences for credential storage
- Login verification
- Signup support
- Logout functionality

This ensures a personalized and secure user experience.

---

## Step 2: Message Input

The user enters a suspicious SMS or message inside the detection interface.

Example:

“Your account will be blocked immediately. Click here to verify now:
http://fakebank-alert.xyz”

The system then forwards the message to the detection engine.

---

## Step 3: Keyword-Based Risk Detection

The SmartDetector module scans the message using predefined scam-related keyword rules.

Detected risk indicators include:

- OTP requests
- Urgent action warnings
- Fake banking alerts
- Suspicious verification links
- Threat-based language

Example keywords:

- urgent
- verify now
- click here
- OTP
- account blocked
- limited time offer

Each keyword contributes to a **risk score** used during classification.

---

## Step 4: Suspicious Link Detection

If a URL is detected inside the message, the system validates it using:

Google Safe Browsing API

The API checks whether the URL belongs to:

- Malware sources
- Phishing domains
- Unsafe redirect links
- Harmful websites

If detected unsafe, the message classification becomes **DANGEROUS**.

---

## Step 5: Classification Engine

The decision engine combines:

- Keyword risk score
- URL safety status
- Message pattern indicators

Based on predefined thresholds, the system assigns the final label:

### 1️⃣ SAFE

The message does not contain suspicious keywords or harmful links.

Example:

“Your electricity bill payment was successful.”

---

### 2️⃣ PROMOTIONAL

The message contains marketing or advertisement content.

Example:

“Flat 50% discount on shoes today!”

---

### 3️⃣ DANGEROUS

The message contains phishing indicators or malicious links.

Example:

“Click here to reset your bank password immediately.”

---

## Step 6: Message History Storage

The system stores analyzed messages locally using **SharedPreferences**.

Stored information includes:

- Message content
- Classification result
- Timestamp

This allows users to revisit previously checked messages.

---

## Step 7: Dashboard Analytics

The dashboard module provides summary statistics such as:

- Number of Safe messages
- Number of Promotional messages
- Number of Dangerous messages

This helps users monitor their message safety trends over time.

---

# Final Workflow Summary

The complete pipeline is:

User Login
→ Enter Message
→ Keyword Pattern Detection
→ URL Extraction
→ Google Safe Browsing API Check
→ Risk Score Calculation
→ Classification Engine
→ Save History
→ Dashboard Visualization
→ Final Output


This architecture ensures **fast, lightweight, and explainable SMS scam detection on mobile devices.**

---

## 📂 Project Structure

```text
MessageRakshak/
│
├── MainActivity.java              # Message input and classification logic
├── LoginActivity.java             # Handles user login and signup
├── DashboardActivity.java         # Displays message statistics summary
├── HistoryActivity.java           # Shows previously analyzed messages
├── SmartDetector.java             # Rule-based scam detection engine
│
├── api/
│   ├── ApiService.java            # Defines Google Safe Browsing API endpoints
│   ├── ApiRequest.java            # Request body structure for API calls
│   ├── ApiResponse.java           # Response parsing model
│   └── RetrofitClient.java        # Retrofit configuration and setup
│
└── res/
    ├── layout/                    # XML layout files for UI screens
    ├── drawable/                  # Icons, shapes, and image resources
    └── values/                    # Colors, strings, themes, and styles
```

# Tech Stack

## System Components and Technologies

| Component | Technology Used |
|-----------|----------------|
| Mobile Platform | Android |
| Programming Language | Java |
| UI Design | XML |
| API Communication | Retrofit |
| Threat Detection | Google Safe Browsing API |
| Local Storage | SharedPreferences |
| Development Environment | Android Studio |

---

# Detection Methodology

The application uses a **hybrid rule-based detection framework**.

---

## Keyword Pattern Analysis

Detects suspicious content such as:

- OTP requests
- Fake banking alerts
- Urgent action instructions
- Suspicious verification prompts
- Threat messages

This improves phishing detection accuracy.

---

## URL Safety Verification

If a link exists inside the message:

The system queries:

Google Safe Browsing API

To detect:

- Malware URLs
- Phishing domains
- Unsafe redirects
- Harmful sources

---

# Features Summary

- Message classification into SAFE, PROMOTIONAL, and DANGEROUS
- Suspicious keyword detection
- Malicious URL verification
- Login and signup system
- Message history tracking
- Dashboard analytics visualization
- Lightweight offline-first architecture
- Clean and simple user interface

---

# Example Use Cases

The application can verify messages such as:

Example 1:

“Your ATM card is blocked. Verify immediately.”

Example 2:

“Buy 1 Get 1 Free today only!”

Example 3:

“Your electricity bill payment was successful.”

---

# Setup Instructions

## 1. Clone the Repository
git clone https://github.com/your-username/MessageRakshak.git


---

## 2. Open the Project

Open the project using:

Android Studio

Allow Gradle synchronization to complete.

---

## 3. Add Google Safe Browsing API Key

Inside:

MainActivity.java

Replace:
private static final String API_KEY = "YOUR_API_KEY_HERE";


with your actual API key.

---

## 4. Run the Application

Run the app using:

- Android Emulator

OR

- Physical Android Device (Android 6.0 and above)

---

# Future Improvements

Planned enhancements include:

- AI/ML-based scam classification
- Multi-language SMS detection support
- Real-time SMS monitoring
- Firebase cloud storage integration
- Advanced analytics dashboard
- Improved UI/UX experience

---

# Contributors
- Gurramkonda Sharun Prakash
---

# License

This project is an independent work developed by Gurramkonda Sharun Prakash to showcase technical expertise and is released under the MIT License.
