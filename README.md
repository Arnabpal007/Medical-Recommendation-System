# 🩺 Medical Recommendation System

This is a multilingual medical recommendation system that takes symptoms in **any language**, detects possible diseases, suggests **generic medicines**, and matches them with **Indian pharmaceutical brands** using fuzzy matching. The app also provides precautions and general advice for the predicted disease.

<img width="803" height="857" alt="image" src="https://github.com/user-attachments/assets/f04bbf42-046f-4840-8796-199c02b3987f" />

---

## 🚀 Features

- 🗣️ Input symptoms in **any language** (auto-translated to English)
- 🧠 AI-powered **disease and medicine prediction**
- 💊 Fuzzy matched with **real Indian pharmaceutical data**
- 📋 Displays **strength, dosage form, price, manufacturer, and packaging**
- ⚠️ Includes **medicine-specific precautions**
- 🌐 Built with **FastAPI**, **LangChain**, and **OpenAI GPT models**

---

## 🛠️ Tech Stack

- **Frontend:** HTML + Tailwind CSS (or your preferred UI)
- **Backend:** FastAPI
- **LLM APIs:** OpenAI GPT-4o & GPT-3.5-turbo
- **AI Agents:** LangGraph + LangChain Tools
- **Data Processing:** FuzzyWuzzy for fuzzy matching
- **Indian Pharma Dataset:** Cleaned `.csv` file of branded medicines
- **Deployment:** Uvicorn (for local), optional cloud deployment

---

## 🧪 Installation & Setup

### 1. Clone the Repository

```bash
git clone https://github.com/<your-username>/medical-recommendation-system.git
cd medical-recommendation-system
```

### 2. Create & Activate Virtual Environment

```bash
python -m venv venv

# Activate (Windows)
venv\Scripts\activate

# Activate (Linux/Mac)
source venv/bin/activate
```

### 3. Install Requirements

```bash
pip install -r requirements.txt
```

### 4. Add OpenAI API Key

Create a `.env` file in the project root:

```env
OPENAI_API_KEY=your_openai_api_key
```

Alternatively, export it from the terminal:

```bash
export OPENAI_API_KEY=your_openai_api_key   # Linux/macOS
set OPENAI_API_KEY=your_openai_api_key      # Windows
```

### 5. Run the Application

```bash
uvicorn app.main:app --reload
```

Visit: [http://localhost:8000](http://localhost:8000)

---

## 📁 Project Structure

```
medical-recommendation-system/
│
├── app/
│   ├── main.py               # FastAPI entrypoint
│   ├── graph.py              # LangGraph logic
│   ├── tools.py              # Custom tools: medicine, fuzzy matching, etc.
│   └── pharma_data/          # Cleaned Indian pharma CSV
│
├── static/                   # Frontend assets (CSS, JS)
├── templates/                # Jinja2 HTML files
├── requirements.txt
├── .env
└── README.md
```

---

## 🧠 How It Works

1. User enters symptoms (in any language)
2. System translates and extracts key symptoms
3. LLM predicts possible diseases and medicines
4. Medicines are fuzzy-matched with Indian pharma brands
5. Precautions are added for each medicine
6. Final result is shown on the UI

---

## 📊 Sample Output

**Input:**  
```
Symptoms: stomach pain
```

**Output:**

```
Disease: Gastritis (K29.9)

Medicines:
- Pantoprazole
- Omeprazole

Advice: Avoid spicy and acidic foods to help alleviate symptoms of gastritis.

┌─────────────┬───────────┬────────┬──────────────┬────────────────────────────┬──────────────────────────────┐
│ Brand       │ Strength  │ Form   │ Price (₹)    │ Manufacturer               │ Packaging                    │
├─────────────┼───────────┼────────┼──────────────┼────────────────────────────┼──────────────────────────────┤
│ Pantoprazole│ 40mg      │ tablet │ 73.1         │ Cadila Pharmaceuticals Ltd │ strip of 10 tablets          │
│ Omeprazole  │ 20mg      │ capsule│ 33           │ Akme Biotec                │ strip of 15 capsules         │
└─────────────┴───────────┴────────┴──────────────┴────────────────────────────┴──────────────────────────────┘

Precaution: Consult your doctor before use.
```

---

## ⚠️ Disclaimer

> This project is for **educational purposes only**. It is **not a substitute for professional medical advice, diagnosis, or treatment**. Always consult a licensed medical practitioner.

---

## 🙌 Acknowledgments

- [OpenAI](https://platform.openai.com/)
- [LangChain](https://www.langchain.com/)
- [LangGraph](https://www.langgraph.dev/)
- [FuzzyWuzzy](https://github.com/seatgeek/fuzzywuzzy)
- Indian pharma data manually cleaned and used from publicly available sources

---


