# Problem Statement: Smart Vehicle Data Validation & Error Detection by BJAK  
## Industry Collaboration (Track 3)

## 📌 Overview
This prototype demonstrates a **digital insurance quoting system** designed for both **car** and **motorcycle** insurance. The flow guides users from selecting their insurance type, entering details, validating vehicle information, and finally receiving an estimated insurance price with optional add-ons.  

The system was created to improve **user experience**, reduce **human errors in vehicle data entry**, and streamline the process of obtaining an insurance quote online.

---

## 🎯 Key Features
- **Insurance Type Selection**  
  Users can choose between **Car** or **Motor** insurance.  

- **Owner Details Input**  
  Simple form to capture owner name, address, postcode, state, and country.  

- **Vehicle Details & Validation**  
  - Plate number entry with validation checks.  
  - Model, make, engine, and year inputs.  
  - **Auto-fill vehicle details** if found in a mock JPJ database.  
  - Real-time error detection for incorrect or missing information.  
  - Smart validation that auto-detects and confirms the vehicle type.  
  - Engine number, chassis number, and usage details captured.  

- **Error Handling**  
  - Red error messages for incorrect entries (e.g., invalid plate number, missing fields).  
  - Green confirmation when the system successfully validates the vehicle details.  

- **Insurance Quote**  
  - Displays an **estimated insurance price** clearly.  
  - Allows users to review their quote before purchase.  
  - Optional add-ons such as **Personal Accident** and **Roadside Assistance**.  

- **Call-to-Action**  
  - **Buy Now** button for direct purchase.  
  - **Talk to Agent** button for customer support.  

---

## 🖼️ Prototype Flow
1. **Get Quote Page** – Choose between Car or Motor insurance.  
2. **Car Insurance Start** – Option to scan documents or enter details manually.  
3. **Owner Details** – Fill in personal information.  
4. **Vehicle Details** – Enter plate number, model, engine, year, and usage.  
5. **Validation & Error Handling** – Real-time system checks and corrections.  
6. **Review Quote** – Confirm details and view estimated insurance cost.  
7. **Estimated Price & Add-ons** – Choose additional coverage options.  
8. **Checkout Options** – Proceed with purchase or consult an agent.  

---

# 🛠️ Technology Stack

## 🔍 OCR (Optical Character Recognition) – *No Dataset Required*
💡 Enables **“scan once, auto-fill all”** for owner + vehicle forms.

- **Tesseract OCR** – extracts text from road tax and insurance documents.  
- **OpenCV** – preprocessing (cropping, noise removal, contrast, skew correction) ensures higher OCR accuracy.  

---

## ✨ Typo Detection & Auto-Correction (Car Dataset)
Dataset: [Cars Dataset 2025 (Kaggle)](https://www.kaggle.com/datasets/abdulmalik1518/cars-datasets-2025)  

💡 Real-time validation that feels like **“spellcheck for cars.”**

- **Python NLP (SpaCy / NLTK)** – tokenization + entity recognition.  
- **Fuzzy Matching Algorithms** – Levenshtein / Damerau-Levenshtein distance to catch and correct spelling mistakes (*Toyta → Toyota*).  

---

## 🚗 Auto Suggestions
💡 Guarantees every suggestion matches **real vehicles** — no invalid entries.  

- **Firebase Firestore Database** – stores official, verified vehicle data (make, model, trim, year, cc).  
- **APIs**:  
  - **JPJ API** – license plate number verification.  
  - **Global OEM datasets** – engine specs, trims, and variants cross-check.  

---

## 🎙️ Voice Input
- **Google Speech-to-Text API** – converts spoken model/year into structured fields, e.g.  
  *“Myvi 1.5 SE 2019”* → auto-filled form fields.  

---

## 📱 Frontend
- **Flutter** – cross-platform mobile app (iOS + Android) with smooth forms and real-time validation UI.  

---

## ⚙️ Backend
- **Python (FastAPI / Flask)** – REST APIs for validation, typo correction, OCR integration, and database lookups.  

---

## 🔗 Links
- **Pitching Video:** https://youtu.be/eM9kES2IBTU
- **Figma Prototype:** https://www.figma.com/design/aO6Q7QKgqZYyIEvbsYNqIE/Smart-Vehicle-Validation---Error-Detection-Prototype?node-id=0-1&t=ALrgbnwKEXWawVOU-1
