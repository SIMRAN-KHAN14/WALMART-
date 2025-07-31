🛒 AutoCart – Mood-Based Product Recommendation Engine

AutoCart is an AI-powered, personalized shopping assistant that recommends products based on the user's current emotional state. By analyzing natural language input, AutoCart detects the user's mood using a trained machine learning model and suggests suitable product categories through mapped business rules, retrieving real-time product listings via the Walmart API.

---

Project Objective

The main goal of AutoCart is to enhance e-commerce personalization through **emotion-aware product recommendations**. Instead of traditional filters like category or price, this system dynamically adapts suggestions based on how the user feels—bringing emotional intelligence to online shopping.

---

Use Cases

- Personalized e-commerce recommendations based on emotion
- Emotionally supportive product suggestions during stress, anxiety, or excitement
- Retail applications for targeting mood-influenced buying behavior
- Health-aware commerce platforms promoting mindful consumption

---

Key Functionalities

- ✅ NLP-based mood prediction using custom ML model
- ✅ Mapping of mood categories to relevant product types
- ✅ Real-time product fetching using the Walmart API
- ✅ Visualization of user mood trends over time
- ✅ Refill reminders based on product usage patterns
- ✅ User data logging for personalization and insights

---

Core Technologies & Tools

| Category        | Tools / Frameworks Used                                 |
|----------------|----------------------------------------------------------|
| **Frontend**    | Streamlit, Plotly Express                               |
| **Backend**     | Python, JSON, MySQL Connector                           |
| **ML/NLP**       | Scikit-learn, Custom-trained mood classifier (text-based) |
| **API**         | Walmart Open API                                        |
| **Dev Tools**   | VS Code, Git, GitHub, Python Virtual Environments       |
| **Environment** | `.env` file for secure key management                   |

---

Project Structure

```

FINAL/
├── AUTOCART/
│   ├── app.py                  → Streamlit UI for recommendations
│   ├── api.py                  → Custom API handlers
│   ├── autcart\_engine.py       → Main recommendation engine
│   ├── autcart\_rules.py        → Rule-based mood-category logic
│   ├── walmart\_api.py          → Wrapper for Walmart product search
│   ├── user\_history.json       → JSON storage of user sessions
│
├── MOODCART/
│   ├── app.py                  → Optional ML interface
│   ├── api.py                  → Inference API for mood model
│   ├── moodcart\_model.py       → ML model for mood classification
│   ├── mood\_map.json           → Mood-to-category mapping
│   ├── mood\_history.json       → JSON storage of past moods
│
├── main\_app.py                 → Combined Streamlit launcher
├── .env                        → API keys and DB credentials (not pushed)
├── requirements.txt            → Python package dependencies
├── mood\_history.json           → (Duplicate in root for quick access)
└── README.md                   → This file

````

---

How It Works

1. **User Input**
User types a short message like:  
`"I'm feeling really stressed and exhausted lately."`

2. **Mood Detection**
`moodcart_model.py` uses a trained NLP classifier to categorize the input as:  
**Detected Mood:** `Stressed`

3. **Category Mapping**
`autcart_rules.py` maps `Stressed` to:
**Product Category:** `Wellness & Self-care Products`

4. **Product Retrieval**
`walmart_api.py` uses the Walmart API to fetch relevant live product listings like:
- Herbal teas  
- Aromatherapy oils  
- Relaxation kits  

5. **Result Display**
- Products shown on UI via Streamlit
- Mood and results logged in `user_history.json`
- Mood history visualized using Plotly graphs

---

Installation & Setup

1. **Clone the Repository**
```bash
git clone https://github.com/yourusername/autocart-mood-recommender.git
cd autocart-mood-recommender
````

2. **Install Dependencies**

```bash
pip install -r requirements.txt
```

3. **Configure Environment Variables**
   Create a `.env` file in the root folder:

```
WALMART_API_KEY=your_api_key_here
DB_USER=your_db_username
DB_PASSWORD=your_db_password
DB_NAME=autocart
```

4. **Run the App**

```bash
streamlit run main_app.py
```

---

Sample Output

```
Input Mood Text: "I feel tired, mentally and physically."
→ Detected Mood: Fatigued
→ Product Category: Health Supplements, Energy Drinks
→ Walmart Recommendations: [Vitamin C Tablets, Gatorade Energy Pack, ...]
```

---

Mood Analytics (Dashboard)

* **Line graphs** of mood patterns using `mood_history.json`
* **Bar charts** showing top categories per mood
* **User-specific product usage logs**
* Integrated via Plotly in Streamlit for real-time visualization

---

Future Enhancements

Integrate with other retailers like Amazon or Flipkart
Use large language models (e.g., OpenAI, HuggingFace) for deeper sentiment detection
Multi-language mood prediction
User authentication for storing long-term mood history
Inventory-based recommendation tuning

---

 Role & Contributions

 ✅ Designed system architecture and recommendation pipeline
 ✅ Trained and fine-tuned the mood classification model using labeled text data
 ✅ Developed UI/UX in Streamlit with data visualization via Plotly
 ✅ Integrated Walmart API for real-time product retrieval
 ✅ Created rules-based logic for mood-to-category mapping
 ✅ Managed environment configuration and deployment locally



Requirements

If you're running manually, create a `requirements.txt` using:

```bash
pip freeze > requirements.txt


Example of key dependencies:

txt
streamlit
pandas
scikit-learn
plotly
requests
mysql-connector-python
python-dotenv

Deployment Options

Local: via Streamlit
Cloud (optional):Streamlit Cloud / AWS / Render
Database: Can be migrated to MySQL/PostgreSQL from JSON
